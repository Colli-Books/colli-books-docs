# Épico 2 — Busca do Acervo por Disciplina

Núcleo funcional do produto: permitir que o professor encontre obras pela disciplina que leciona, com refinamento por etapa e por texto.

---

## US06 — Busca por disciplina `MUST` · 5 pts

**Como** Paulo, **posso** selecionar uma disciplina e ver todas as obras vinculadas a ela, **para que** eu descubra quais livros do acervo servem à área que leciono.

**Critérios de aceitação**

- DADO que estou logado, QUANDO acesso a busca, ENTÃO vejo a lista de disciplinas cadastradas pela editora.
- QUANDO seleciono uma disciplina (ex.: Matemática), ENTÃO vejo em grade as obras vinculadas a ela, com capa, título, autor e etapa de ensino.
- QUANDO uma obra está vinculada a mais de uma disciplina, ENTÃO ela aparece na busca de todas elas.
- QUANDO a disciplina não possui obras vinculadas, ENTÃO vejo mensagem indicando ausência de resultados.
- A listagem é paginada e o layout se adapta a telas de celular.

---

## US07 — Filtro por etapa de ensino `MUST` · 3 pts

**Como** Paulo, **posso** refinar o resultado pela etapa de ensino, **para que** eu veja apenas obras adequadas à faixa etária da minha turma.

**Critérios de aceitação**

- DADO que estou vendo o resultado de uma disciplina, QUANDO seleciono uma etapa (Educação Infantil, Fundamental I, Fundamental II, Ensino Médio), ENTÃO a lista exibe apenas as obras daquela etapa.
- QUANDO combino disciplina e etapa, ENTÃO ambos os filtros são aplicados simultaneamente.
- QUANDO limpo os filtros, ENTÃO volto ao resultado completo da disciplina.

---

## US08 — Busca por texto `MUST` · 3 pts

**Como** Paulo, **posso** buscar obras digitando título, autor ou tema, **para que** eu localize um livro específico sem navegar pelas disciplinas.

**Critérios de aceitação**

- QUANDO digito um termo e confirmo, ENTÃO vejo as obras cujo título, autor ou tema contenham o termo, ignorando acentuação e maiúsculas/minúsculas.
- QUANDO não há resultados, ENTÃO vejo mensagem de ausência de resultados e um atalho para a busca por disciplina.

---

## US09 — Detalhe da obra `MUST` · 5 pts

**Como** Paulo, **posso** abrir a página de uma obra e ver sinopse, ficha técnica, disciplinas atendidas e etapa de ensino, **para que** eu avalie se o livro atende ao meu planejamento.

**Critérios de aceitação**

- DADO que clico em uma obra, ENTÃO vejo capa, título, autor, sinopse, ISBN, número de páginas, etapa de ensino e as disciplinas vinculadas.
- QUANDO clico em uma das disciplinas exibidas, ENTÃO sou levado à busca daquela disciplina.
- ENTÃO vejo a seção de material pedagógico da obra ([US12](epico-3-material.md#us12-materiais-da-obra-must-3-pts)).
- ENTÃO vejo um link para a loja oficial, aberto em nova aba.

??? question "Dúvida levantada com o cliente"
    Revisar critérios de aceitação. Ver [Notas da reunião](../cliente/notas.md#epico-2-busca-do-acervo-por-disciplina).

---

## US10 — Minhas disciplinas `SHOULD` · 3 pts

**Como** Paulo, **posso** ajustar no meu perfil as disciplinas que leciono, **para que** o sistema me apresente as obras da minha área ao entrar.

**Critérios de aceitação**

- DADO que estou no meu perfil, ENTÃO vejo as disciplinas informadas pela editora no meu cadastro e posso ajustá-las.
- QUANDO salvo a alteração, ENTÃO a tela inicial passa a exibir obras dessas disciplinas.

??? question "Dúvida levantada com o cliente"
    Confirmar se as disciplinas são pré-cadastradas antes ou pelo professor e podem ser alteradas. Ver [Notas da reunião](../cliente/notas.md#epico-2-busca-do-acervo-por-disciplina).

---

## US11 — Minha Seleção `SHOULD` · 3 pts

**Como** Paulo, **posso** salvar obras em uma lista pessoal, **para que** eu retome depois as que pretendo indicar à coordenação.

**Critérios de aceitação**

- QUANDO clico em "Salvar" numa obra, ENTÃO ela passa a constar em "Minha Seleção" e o botão indica o estado salvo.
- QUANDO acesso "Minha Seleção", ENTÃO vejo as obras salvas e posso remover qualquer uma.
- A seleção persiste entre sessões.

??? tip "Descartável"
    Facilmente descartável se o escopo ficar grande. Ver [Notas da reunião](../cliente/notas.md#epico-2-busca-do-acervo-por-disciplina).
