# Épico 4 — Gestão do Acervo (Administrador)

Histórias que dão ao administrador o controle do catálogo, das disciplinas, dos vínculos e dos materiais.

!!! note "Diretriz de interface"
    A editora já opera diariamente o painel do WordPress. O painel administrativo deste sistema deve seguir o mesmo modelo mental — listagem com busca e filtro, botão de adicionar, formulário de campos, salvar — sem inventar padrões de interação novos. Familiaridade reduz o custo de adoção e pesa na avaliação do cliente na PC3.

!!! warning "Importante — entender a origem dos dados"
    Entender como está sendo acessada as informações, se tem um banco de dados e como são adicionadas novas informações. Ver [Notas da reunião](../cliente/notas.md#epico-4-gestao-do-acervo-administrador).

---

## US14 — Cadastro e edição de obras `MUST` · 8 pts

**Como** Diego, **posso** cadastrar, editar e inativar obras do acervo, **para que** o que o professor busca reflita o catálogo real da editora.

**Critérios de aceitação**

- DADO que estou no painel, QUANDO cadastro uma obra com título, autor, sinopse, ISBN, número de páginas, etapa de ensino, capa e link da loja, ENTÃO ela passa a existir no acervo.
- QUANDO edito uma obra, ENTÃO as alterações refletem imediatamente na busca e na página da obra.
- QUANDO inativo uma obra, ENTÃO ela deixa de aparecer nas buscas sem ser excluída da base.
- Campos obrigatórios são validados antes de salvar, com erro sinalizado por campo.

---

## US15 — Gestão de disciplinas `MUST` · 5 pts

**Como** Diego, **posso** cadastrar, renomear e inativar as disciplinas do sistema, **para que** a busca do professor acompanhe a evolução do acervo sem depender de alteração no código.

**Critérios de aceitação**

- DADO que estou no painel, QUANDO cadastro uma disciplina informando nome e descrição, ENTÃO ela passa a ser exibida na busca do professor.
- QUANDO renomeio uma disciplina, ENTÃO o novo nome aparece na busca e as obras vinculadas são preservadas.
- QUANDO tento inativar uma disciplina com obras vinculadas, ENTÃO recebo aviso informando quantas obras serão afetadas antes de confirmar.
- Não é permitido cadastrar duas disciplinas com o mesmo nome.

??? question "Dúvida levantada com o cliente"
    Disciplinas ainda não fazem parte das informações guardadas no banco — verificar a necessidade de mantê-las. Ver [Notas da reunião](../cliente/notas.md#epico-4-gestao-do-acervo-administrador).

---

## US16 — Vínculo entre obra e disciplinas `MUST` · 3 pts

**Como** Diego, **posso** vincular cada obra a uma ou mais disciplinas, **para que** ela apareça na busca de todas as áreas que atende.

**Critérios de aceitação**

- DADO que estou editando uma obra, QUANDO seleciono múltiplas disciplinas e salvo, ENTÃO a obra passa a constar na busca de cada uma delas.
- QUANDO removo um vínculo, ENTÃO a obra deixa de aparecer naquela disciplina, mas permanece nas demais.
- Uma obra sem nenhuma disciplina vinculada é sinalizada na listagem administrativa como pendente de classificação.

??? question "Dúvida levantada com o cliente"
    Cadastrar obras no acervo e vincular a matérias — professores podem fazer esse vínculo? Ver [Notas da reunião](../cliente/notas.md#epico-4-gestao-do-acervo-administrador).

---

## US17 — Publicação de material pedagógico `MUST` · 5 pts

**Como** Diego, **posso** enviar arquivos de material pedagógico e vinculá-los a uma obra, **para que** o professor os encontre junto do livro.

**Critérios de aceitação**

- QUANDO envio um PDF informando título, tipo e obra vinculada, ENTÃO o material passa a aparecer na página daquela obra.
- QUANDO envio formato não permitido ou arquivo acima do limite de tamanho, ENTÃO vejo mensagem de erro e nada é salvo.
- QUANDO removo um material, ENTÃO ele deixa de ser listado e o download passa a ser negado.

??? question "Dúvidas levantadas com o cliente"
    - Verificar a necessidade de criar essa seção de material pedagógico.
    - É mais válido obter perguntas da IA ou adicionar aquisição de material pedagógico?
    - Material pedagógico ainda não é armazenado. Ver [Notas da reunião](../cliente/notas.md#epico-4-gestao-do-acervo-administrador).

---

## US18 — Obras em destaque `SHOULD` · 3 pts

**Como** Diego, **posso** marcar obras como destaque, **para que** elas apareçam na tela inicial do professor e eu direcione a atenção para lançamentos e campanhas.

**Critérios de aceitação**

- DADO que estou editando uma obra, QUANDO marco a opção "Destaque" e salvo, ENTÃO ela passa a constar na tela inicial do professor.
- QUANDO desmarco, ENTÃO ela deixa de aparecer no destaque, permanecendo normalmente na busca.
- QUANDO nenhuma obra está marcada como destaque, ENTÃO a tela inicial exibe as obras cadastradas mais recentemente.

??? tip "Descartável"
    Facilmente descartável se o escopo ficar grande. Ver [Notas da reunião](../cliente/notas.md#epico-4-gestao-do-acervo-administrador).
