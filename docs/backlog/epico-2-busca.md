# Épico 2 — Busca e Seleção do Acervo

Núcleo funcional do produto: permitir que o professor encontre obras pelo nome, filtre por tema e escolaridade, veja detalhes, vincule-se aos temas que leciona e salve uma seleção pessoal.

---

## US07 — Busca de obras por nome `MUST` · 3 pts

**Como** Paulo, **posso** buscar obras digitando o nome em um campo de busca, **para que** eu localize um livro específico no acervo.

**Critérios de aceitação**

- DADO que estou logado, QUANDO digito um termo no campo de busca e confirmo, ENTÃO vejo as obras cujo título contenha o termo, ignorando acentuação e maiúsculas/minúsculas.
- QUANDO não há resultados, ENTÃO vejo mensagem de ausência de resultados.
- A listagem é paginada e o layout se adapta a telas de celular.

---

## US08 — Filtro por tema e escolaridade `MUST` · 5 pts

**Como** Paulo, **posso** filtrar o resultado da busca por tema e escolaridade, **para que** eu veja apenas as obras adequadas à área que leciono e à faixa etária da minha turma.

**Critérios de aceitação**

- DADO que estou vendo o resultado de uma busca, QUANDO seleciono um tema, ENTÃO a lista exibe apenas as obras daquele tema.
- QUANDO seleciono uma escolaridade (Educação Infantil, Fundamental I, Fundamental II, Ensino Médio), ENTÃO a lista exibe apenas as obras daquela escolaridade.
- QUANDO combino tema e escolaridade, ENTÃO ambos os filtros são aplicados simultaneamente.
- QUANDO uma obra está vinculada a mais de um tema, ENTÃO ela aparece na busca de todos eles.
- QUANDO limpo os filtros, ENTÃO volto ao resultado completo da busca.

---

## US09 — Detalhe da obra `MUST` · 5 pts

**Como** Paulo, **posso** abrir a página de uma obra e ver seus detalhes, **para que** eu avalie se o livro atende ao meu planejamento.

**Critérios de aceitação**

- DADO que clico em uma obra, ENTÃO vejo capa, título, autor, sinopse, ISBN, número de páginas, escolaridade e os temas vinculados.
- QUANDO clico em um dos temas exibidos, ENTÃO sou levado à busca filtrada daquele tema.
- ENTÃO vejo um botão "Comprar livro" que direciona para a página de compra na loja oficial, aberto em nova aba.

---

## US10 — Informações pessoais do professor `SHOULD` · 2 pts

**Como** Paulo, **posso** acessar uma tela de informações pessoais para ver meu e-mail e preencher meu nome e a escola associada, **para que** meu perfil esteja completo no sistema.

**Critérios de aceitação**

- DADO que estou logado como professor, QUANDO acesso "Minhas informações", ENTÃO vejo meu e-mail (preenchido pela editora no cadastro) em modo somente leitura.
- ENTÃO vejo campos editáveis para nome e escola associada.
- QUANDO preencho os campos e salvo, ENTÃO as informações são persistidas e exibidas no cabeçalho e no perfil.
- QUANDO o nome não foi preenchido, ENTÃO o cabeçalho exibe o e-mail como identificação provisória.
- ENTÃO vejo um botão "Sair" que encerra a sessão e me leva à tela de login.

---

## US11 — Vinculação do professor a temas e escolaridades `MUST` · 3 pts

**Como** Paulo, **posso** vincular-me aos temas e escolaridades que leciono, **para que** o sistema me apresente as obras da minha área.

**Critérios de aceitação**

- DADO que estou no meu perfil, ENTÃO vejo a lista de temas e escolaridades cadastrados pela editora e posso selecionar os que leciono.
- QUANDO salvo a alteração, ENTÃO o sistema passa a priorizar as obras dos meus temas e escolaridades.
- A vinculação persiste entre sessões e pode ser alterada a qualquer momento.

---

## US12 — Seleção e salvamento de obras `MUST` · 3 pts

**Como** Paulo, **posso** selecionar obras quando estiverem listadas e salvá-las, **para que** eu retome depois.

**Critérios de aceitação**

- QUANDO clico em "Salvar" numa obra listada, ENTÃO ela passa a constar em "Minha Seleção" e o botão indica o estado salvo.
- QUANDO acesso "Minha Seleção", ENTÃO vejo as obras salvas e posso remover qualquer uma.
- A seleção persiste entre sessões.
