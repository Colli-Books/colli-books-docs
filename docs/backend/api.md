# API

Resumo das rotas para quem integra o app. Os campos detalhados e os exemplos ficam no
Swagger (`/docs`), que é gerado pelo próprio código e por isso está sempre atualizado.

Todas as rotas de negócio começam com **`/api/v1`**.

---

## Rotas

| Método | Rota | Quem usa | Para quê |
| --- | --- | --- | --- |
| `POST` | `/auth/login` | Todos | Entrar com e-mail e senha |
| `POST` | `/auth/refresh` | Todos | Renovar a sessão |
| `POST` | `/auth/logout` | Todos | Sair |
| `GET` | `/auth/me` | Logado | Dados de quem está logado (`role` decide se mostra o painel admin) |
| `POST` | `/auth/forgot-password` | Todos | Pedir link de redefinição |
| `POST` | `/auth/reset-password` | Todos | Definir a senha nova com o token do link |
| `POST` | `/invites/verify` | Convidado | Conferir o convite e obter o e-mail |
| `POST` | `/invites/accept` | Convidado | Completar o cadastro: `full_name`, `school` (opcional), `password` |
| `POST` | `/invites/resend` | Convidado | Pedir novo link quando o convite expirou |
| `POST` | `/admin/teachers` | Admin | Cadastrar professor pelo e-mail (envia o convite) |
| `POST` | `/admin/teachers/{id}/invite` | Admin | Gerar e enviar um convite novo |

Fora do `/api/v1`: `GET /` (a API está no ar) e `GET /health` (a API alcança o banco).

---

## Swagger (deploy de demonstração)

A documentação interativa da API publicada está em:

**<https://colli-books-backend-ixvf.vercel.app/docs>**

Ela é gerada pelo próprio código, então reflete exatamente as rotas, os schemas e os
exemplos da versão em produção. Pelo botão *Try it out* as requisições são executadas de
fato, contra o banco real do deploy.

### Obtendo o token com o usuário admin

As rotas autenticadas exigem um access token. O administrador já cadastrado no banco do
deploy é:

| Campo | Valor |
| --- | --- |
| E-mail | `admin@colli.com` |
| Senha | `12345678` |
| Papel | `admin` |

Para autorizar as chamadas no Swagger:

1. Abra <https://colli-books-backend-ixvf.vercel.app/docs>.
2. Em `POST /api/v1/auth/login`, clique em **Try it out** e envie as credenciais acima.
3. Copie o `access_token` da resposta (validade de 15 minutos).
4. Clique em **Authorize** (cadeado, no topo da página) e cole o token.
5. As rotas protegidas e de admin passam a funcionar no *Try it out*.

O mesmo token também serve para testar a API fora do Swagger, via
`Authorization: Bearer <access_token>`.

!!! warning "Ambiente de demonstração"
    O deploy é compartilhado: os dados cadastrados por *Try it out* (obras, temas,
    professores) ficam no banco real. Prefira o ambiente
    [local](desenvolvimento.md#rodar-localmente) para experimentos mais destrutivos.

---

## Autenticação

Rotas que exigem login recebem o header `Authorization: Bearer <access_token>`.

| Token | Validade | Onde o app guarda |
| --- | --- | --- |
| Access token (JWT) | 15 minutos | Memória |
| Refresh token | 30 dias, troca a cada uso | `flutter_secure_storage` |

Quando qualquer rota responder `401 TOKEN_EXPIRED`, o app chama `/auth/refresh`. Se o refresh
falhar, volta para o login.

---

## Formato de erro

Todo erro tem o mesmo formato. O app decide o que mostrar pelo **`code`**, que não muda; o
`message` é só um texto de apoio.

```json
{
  "code": "INVITE_EXPIRED",
  "message": "O convite expirou. Solicite um novo link.",
  "details": null
}
```

| `code` | HTTP | Quando |
| --- | --- | --- |
| `VALIDATION_ERROR` | 422 | Campo ausente ou inválido (`details` lista os campos) |
| `WEAK_PASSWORD` | 422 | Senha com menos de 8 caracteres |
| `UNAUTHENTICATED` | 401 | Faltou o token |
| `INVALID_CREDENTIALS` | 401 | E-mail ou senha errados (sem dizer qual) |
| `TOKEN_EXPIRED` / `TOKEN_INVALID` | 401 | Access ou refresh token vencido ou inválido |
| `FORBIDDEN` | 403 | Professor tentando usar rota de admin |
| `NOT_FOUND` | 404 | Recurso não existe |
| `EMAIL_ALREADY_REGISTERED` | 409 | E-mail já cadastrado |
| `ACCOUNT_ALREADY_ACTIVE` | 409 | Novo convite para quem já ativou a conta |
| `INVITE_INVALID` | 404 | Convite inexistente ou substituído |
| `INVITE_ALREADY_USED` | 409 | Convite já usado |
| `INVITE_EXPIRED` | 410 | Convite vencido |
| `RESET_TOKEN_INVALID` | 400 | Link de redefinição inválido, usado ou vencido |
| `RATE_LIMITED` | 429 | Muitas tentativas em pouco tempo |

---

## Links abertos pelo app

O e-mail traz um link e um código (o mesmo token):

- Convite: `collibooks://convite?token=...`
- Redefinição: `collibooks://redefinir-senha?token=...`

Alguns apps (WhatsApp, Gmail) não deixam clicar em `collibooks://`. Por isso o app precisa de
uma tela para **colar o código**. Quando houver domínio próprio, basta trocar a variável
`APP_LINK_BASE_URL` para `https://...` e os links passam a abrir direto.
