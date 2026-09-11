# Visão do produto

**Cliente:** Diego — Colli Books Editora (Águas Claras, Brasília/DF)
**Produto:** Plataforma de consulta ao acervo por tema e escolaridade, voltada a professores
**Versão:** 3.0 — acesso controlado pela editora por convite

---

## O problema a resolver

O sistema resolve um problema único: **um professor precisa descobrir quais obras do acervo contém o tema que procura.** A editora cadastra o professor a partir de um e-mail, ele recebe um convite, define sua senha, busca obras pelo nome, filtra por tema e escolaridade, e encontra as obras daquela área — com um link direto para compra na loja oficial.

Os dois únicos perfis são:

- **Professor** — consome o acervo. Busca, filtra, consulta, seleciona e salva obras.
- **Administrador** — alimenta o acervo, cria temas e escolaridades, vincula-os aos livros e controla quem tem acesso.

Não há área de cliente final, carrinho, orçamento ou venda dentro do sistema. A venda continua na loja oficial existente.

---

## Decisão de acesso

!!! warning "Não existe auto-cadastro"
    Só entra no sistema quem a editora cadastrar — é isso que impede a plataforma de virar uma base indistinta de quem é ou não professor.

### Fluxo de convite

```mermaid
flowchart LR
    A[Administrador<br/>cadastra o professor<br/>a partir de um e-mail] --> B[Sistema gera<br/>link de convite]
    B --> C[Editora envia o link<br/>por e-mail ou WhatsApp]
    C --> D[Professor abre o link<br/>e define a própria senha]
    D --> E[Login com o e-mail<br/>do professor]
```

Esse desenho existe por dois motivos:

1. **Nenhuma senha trafega por mensagem** e fica registrada para sempre numa conversa de WhatsApp.
2. **O link de convite e a recuperação de senha usam o mesmo mecanismo de token** — uma implementação atende as duas estórias, o que reduz o esforço em vez de aumentá-lo.

---

## Decisão técnica central

A relação entre obra e tema é **muitos-para-muitos**: uma obra de literatura infantil pode atender Português, História e Ensino Religioso ao mesmo tempo. E a lista de temas **não é fixa no código** — a editora cria e ajusta conforme o acervo cresce.

!!! tip "Por que as US de cadastro de temas e escolaridades são `MUST`"
    Sem a gestão de temas e escolaridades e o vínculo obra–tema, a busca da [US07](../backlog/epico-2-busca.md#us07-busca-de-obras-por-nome-must-3-pts) e o filtro da [US08](../backlog/epico-2-busca.md#us08-filtro-por-tema-e-escolaridade-must-5-pts) não têm o que retornar.
