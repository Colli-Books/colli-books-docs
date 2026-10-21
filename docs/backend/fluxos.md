# Fluxos de acesso

Como funcionam, por dentro, as histórias do [Épico 1](../backlog/epico-1-acesso.md).

---

## Estados de uma conta

```mermaid
stateDiagram-v2
    [*] --> invite_pending: editora cadastra o e-mail
    invite_pending --> invite_pending: novo convite
    invite_pending --> active: professor completa o cadastro
    active --> inactive: desativada
    note right of invite_pending
        Login bloqueado:
        ainda não há senha
    end note
```

O estado `inactive` já existe no banco, mas ainda não há tela nem rota que desative uma conta.

---

## Cadastro do professor (US01 e US02)

A editora informa **só o e-mail**. O professor recebe o convite no e-mail dele e, pelo link,
preenche o que falta: **nome** (obrigatório), **escola** (opcional) e a **senha** que escolher.
Ninguém além dele conhece a senha.

```mermaid
sequenceDiagram
    actor Ed as Editora
    participant API
    participant Mail as E-mail
    actor Prof as Professor

    Ed->>API: POST /admin/teachers {email}
    API->>API: cria conta (invite_pending) + convite de 72 h
    API->>Mail: envia o link de convite
    API-->>Ed: 201 + link e código (para reenviar por WhatsApp, se preciso)
    Mail-->>Prof: "Complete seu cadastro"
    Prof->>API: POST /invites/verify {token}
    API-->>Prof: e-mail da conta (tela já preenchida)
    Prof->>API: POST /invites/accept {token, nome, escola, senha}
    API->>API: grava dados, ativa a conta, invalida o convite
    API-->>Prof: sessão aberta (já entra logado)
```

**Casos de erro do convite**

| Situação | Resposta | O que o app mostra |
| --- | --- | --- |
| Token não existe (ou foi substituído por um novo) | `404 INVITE_INVALID` | "Convite inválido" |
| Já foi usado | `409 INVITE_ALREADY_USED` | Orientar a fazer login ou usar "Esqueci minha senha" |
| Passou de 72 h | `410 INVITE_EXPIRED` | Botão "Pedir novo link" → `POST /invites/resend` |

O reenvio só funciona para convite **expirado** e o link novo vai **só para o e-mail**, nunca
na resposta. Assim, quem encontrar um link antigo não ganha acesso.

---

## Login, sessão e logout (US03 e US05)

Professor e administrador usam a mesma tela e a mesma rota. O campo `role` da resposta diz ao
app se ele deve mostrar o painel administrativo.

```mermaid
sequenceDiagram
    participant App
    participant API

    App->>API: POST /auth/login {email, senha}
    API-->>App: access token (15 min) + refresh token (30 dias)
    Note over App: guarda o refresh token<br/>no armazenamento seguro
    App->>API: GET /auth/me (Authorization: Bearer access)
    API-->>App: dados do usuário
    Note over App,API: 15 min depois...
    App->>API: GET /auth/me
    API-->>App: 401 TOKEN_EXPIRED
    App->>API: POST /auth/refresh {refresh}
    API-->>App: par novo (o refresh antigo deixa de valer)
    App->>API: POST /auth/logout {refresh}
    API-->>App: 204 (refresh revogado)
```

- **Credencial errada** sempre responde `401 INVALID_CREDENTIALS`, sem dizer se o e-mail existe.
- **Refresh reutilizado** (um token que já foi trocado) indica roubo: a API derruba **todas**
  as sessões daquele usuário.
- O **administrador** é criado direto no banco pelo comando `seed-admin`; não existe tela de
  cadastro de administrador (US05).

---

## Esqueci minha senha (US04 e US06)

```mermaid
sequenceDiagram
    actor U as Usuário
    participant API
    participant Mail as E-mail

    U->>API: POST /auth/forgot-password {email}
    API-->>U: 202 (sempre a mesma mensagem)
    API->>Mail: link de 30 min, só se a conta existir e estiver ativa
    Mail-->>U: "Redefinir senha"
    U->>API: POST /auth/reset-password {token, nova senha}
    API->>API: troca a senha, invalida o link, encerra todas as sessões
    API-->>U: 204
```

A resposta é **sempre igual**, exista o e-mail ou não. Assim ninguém consegue descobrir quem
tem conta.
