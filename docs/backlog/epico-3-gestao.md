# Épico 3 — Gestão do Acervo (Administrador)

Histórias que dão ao administrador o controle do catálogo, dos temas, das escolaridades e dos vínculos, além da página de início e do perfil do administrador.

!!! note "Diretriz de interface"
    A editora já opera diariamente o painel do WordPress. O painel administrativo deste sistema deve seguir o mesmo modelo mental — listagem com busca e filtro, botão de adicionar, formulário de campos, salvar — sem inventar padrões de interação novos. Familiaridade reduz o custo de adoção e pesa na avaliação do cliente na PC3.

---

## US13 — Página de início do administrador `SHOULD` · 3 pts

**Como** Diego, **posso** ver uma página de início com informações gerais do sistema e atalhos para as ações mais comuns, **para que** eu tenha uma visão rápida do estado do acervo e do acesso dos professores.

**Critérios de aceitação**

- DADO que faço login como administrador, ENTÃO sou levado à página de início do painel.
- ENTÃO vejo a quantidade de obras no catálogo, o número de professores cadastrados e o número de convites pendentes.
- ENTÃO vejo atalhos visíveis para "Convidar professor" e "Cadastrar nova obra", que direcionam às respectivas telas.

---

## US14 — Página pessoal do administrador `SHOULD` · 2 pts

**Como** Diego, **posso** acessar uma página pessoal onde vejo meu e-mail e posso sair do sistema, **para que** eu saiba qual conta estou usando e encerre a sessão quando necessário.

**Critérios de aceitação**

- DADO que estou logado como administrador, QUANDO acesso minha página pessoal, ENTÃO vejo meu e-mail em modo somente leitura.
- ENTÃO não há campos editáveis nesta página.
- ENTÃO vejo um botão "Sair" que encerra a sessão e me leva à tela de login.

---

## US15 — Cadastro e edição de obras `MUST` · 8 pts

**Como** Diego, **posso** cadastrar e editar obras do acervo, **para que** o que o professor busca reflita o catálogo real da editora.

**Critérios de aceitação**

- DADO que estou no painel, QUANDO cadastro uma obra (por exemplo: título, autor, sinopse, ISBN, número de páginas, capa e link da loja), ENTÃO ela passa a existir no acervo.
- QUANDO edito uma obra, ENTÃO as alterações refletem imediatamente na busca e na página da obra.
- Campos obrigatórios são validados antes de salvar, com erro sinalizado por campo.

---

## US16 — Cadastro de temas e escolaridades `MUST` · 5 pts

**Como** Diego, **posso** cadastrar temas e escolaridades no sistema, **para que** a busca do professor acompanhe a evolução do acervo sem depender de alteração no código.

**Critérios de aceitação**

- DADO que estou no painel, QUANDO cadastro um tema informando nome e descrição, ENTÃO ele passa a ser exibido na busca do professor.
- QUANDO cadastro uma escolaridade informando nome, ENTÃO ela passa a ser exibida nos filtros de busca.
- QUANDO renomeio um tema ou escolaridade, ENTÃO o novo nome aparece na busca e as obras vinculadas são preservadas.
- Não é permitido cadastrar dois temas ou duas escolaridades com o mesmo nome.

!!! tip "Por que esta US é `MUST`"
    Sem a gestão de temas e escolaridades, a busca da [US07](epico-2-busca.md#us07-busca-de-obras-por-nome-must-3-pts) e o filtro da [US08](epico-2-busca.md#us08-filtro-por-tema-e-escolaridade-must-5-pts) não têm o que retornar.

---

## US17 — Vínculo entre obra, temas e escolaridades `MUST` · 3 pts

**Como** Diego, **posso** vincular cada obra a um ou mais temas e a uma escolaridade, **para que** ela apareça na busca filtrada corretamente.

**Critérios de aceitação**

- DADO que estou editando uma obra, QUANDO seleciono múltiplos temas e uma escolaridade e salvo, ENTÃO a obra passa a constar na busca de cada um dos temas e daquela escolaridade.
- QUANDO removo um vínculo de tema, ENTÃO a obra deixa de aparecer naquele tema, mas permanece nos demais.
- Uma obra pode existir no acervo sem tema ou escolaridade vinculada; nesse caso, ela não aparece nos filtros de busca, mas permanece cadastrada.
