# Protótipo de Alta Fidelidade

### Visualização do Protótipo

<center>

<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="1000" height="1100" src="https://embed.figma.com/proto/RB1DIEdnMMeDdUoLJUP3b9/Collibooks?node-id=1-1245&p=f&scaling=min-zoom&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=1%3A1245&show-proto-sidebar=1&embed-host=share" allowfullscreen></iframe>

</center>

---

## 1. Fluxo Geral e Autenticação

Esse modulo engloba o controle de acesso dos usuários, autenticações e páginas institucionais de suporte.


### 1.1. Tela de Login (Admin e Professor)
* **História de Usuário Vinculadas:** [US03 - Autenticação](),[US05 - Autenticação do Administrador]().
* **Objetivo:** Permitir que o acesso seguro a plataforma de acordo com o perfil do usuário.

#### Componentes e Interações
* **Campos de Entrada:** E-mail e Senha.
* **Ações:** Botão `Entrar` e link `Esqueci minha senha`.
* **Fluxo do Perfil:** Redireciona o Administrador para a *Visão Geral(Dashboard)* e o Professor para o *Catalogo de Obras*.


### 1.2. Tela: Páginas Institucionais (Sobre nós, Termos de Uso, Política de Privacidade)
* **História de Usuário Vinculadas:** [US18 - Navegação com seções institucionais]().
* **Objetivo:** Exibir o conteúdo de suporte, diretrizes da LGPD e Informações corporativas da Editora.

#### Componentes e Interações
* Conteúdo textual formatado em seções explicativas.
* Botão de navegação para voltar ao catálogo ou painel.

---

## 2. Fluxo Admin

Fluxo responsável pela gestão do acervo, convites dos professores e gestão do sistema.

### 2.1.Tela Home (Admin)
* **História de Usuário Vinculadas:** [US13 - Página de início do administrador]()
* **Objetivo:** Visão rápida de informações gerais do sistema

#### Componentes e Interações
* **Ações:** Botão `Menu Sanduíche`, botão `Convidar Professor`, botão de `Perfil` no canto superior direito e botão de `Cadastrar Nova Obra` e botões de navegação fixa no rodapé.

### 2.2. Menu Lateral (Admin)
* **História de Usuário Vinculadas:** [US18 — Navegação com seções institucionais]()
* **Objetivo:** Menu de navegação para telas de visão geral, catálogo geral e sobre nós, links para editora, PNLD, Blog e Anima Kids.

#### Componentes e Interações
* **Ações:** Botões de navegação para as outras telas.

### 2.3. Perfil Admin
* **História de Usuário Vinculadas:** [US14 — Página pessoal do administrador]()
* **Objetivo:** Mostrar email do administrador e botão de `sair`.

#### Componentes e Interações
* **Ações:** Botão de `Sair`

### 2.4. Gestão de Professores e Convidar Professores
* **História de Usuário Vinculadas:** [US01 — Cadastro de professor pelo administrador]()
* **Objetivo:** Visualizar professores cadastrados, situação de cadastro e filtros por nome, escola, Convidar professores informando nome completo e email.

#### Componentes e Interações
* **Ações:** Botão de `Convidar Professor`, botão de `Enviar Convite`, botão de `Cancelar`


### 2.6. Cadastro de Obra e Edição de Obra
* **História de Usuário Vinculadas:** [US15 — Cadastro e edição de obras](), [US17 — Vínculo entre obra, temas e escolaridades]()
* **Objetivo:** Cadastrar novas obras, informando dados do livro e edição dos dados de obras cadastradas.

### 2.7. Cadastro de Escolaridade e Tema
* **História de Usuário Vinculadas:** [US16 — Cadastro de temas e escolaridades ]()
* **Objetivo:** Cadastrar temas e escolaridades com o fim de categorizar os livros, possibilitando busca de livros por estas categorias.

### 2.8. Catálogo de Obras
* **História de Usuário Vinculadas:** [US07 — Busca de obras por nome]()
* **Objetivo:** Visualizar obras cadastradas e possibilitar edição delas.

---

## 3. Fluxo Professor

Documentação das telas do fluxo do professor, baseada nos protótipos e componentes visuais no Figma.

### 3.1. Tela: Busca e Catálogo de Obras
* **História de Usuário Vinculadas:** [US07 - Busca por nome]().
* **Objetivo:** Permitir ao professor explorar o acervo da editora, realizar buscas por palavras chaves e também aplicar filtros pedagógicos.

#### Componentes e Interações (Figma)
* **Barra de Busca Superior:** Input com o placeholder *"Buscar por titulo, autor, ISBN.."*
* **Filtro Rápido:** Botões seletores de filtro por escolaridade (*ex: Ensino Fundamental I, Ensino Fundamental II..*) e temas (*ex: Bullying, Imaginação..*).
* **Cards do Acervo:**
    * Imagem de capa do livro;
    * Titulo da obra e Nome do Autor.
    * Tags temáticas associadas.
    * Botão de ação rápidas e clique no card para ver detalhes.
* **Barra de navegação Inferior (Bottom Bar):** Ícone fixos para `ColliBooks`, `Seleção` ,`Perfil`.


### 3.2. Tela: Detalhes da Obra
* **História de Usuário Vinculadas:** [US09 - Detalhe da obra]().
* **Objetivo:** Exibir a ficha técnica completa, sinopse, material de apoio pedagógico e ações de compra/salvamento do livro.

#### Componentes e Interações (Figma)
* **Cabeçalho Visual:** Exibição da imagem de capa expandida do livro.
* **Ações Principais:**
    * Botão em Destaque verde: `Comprar Livro` (Abre a loja oficial a editora em uma nova aba).
    * botão secundário de contorno: `Salvar na Seleção` / `Adicionar a Seleção`.
* **Identificação:** Tags temáticas (*ex: Pedagógico, Aventura...*), Titulo da Obra (*ex: O mistério da floresta*) e Autor.
* **Bloco "Sinopse":** Texto detalhando o enredo a proposta da obra.
* **Bloco "Material Pedagógico:** Cards com botão de download para materiais de apoio:
    * *Guia de Leitura (PDF)*.
    * *Atividades Complementares (PDF)*.
* **Ficha Técnica e Metadados:**
    * Indicadores numéricos: `Nº de Páginas` e `Edição`.
    * Código `ISBN`.
    * Chips de `Disciplinas Atendidas` (*ex: Língua Portuguesa, Ciências, Educação Ambiental..*).

### 3.3. Tela: Minhas Seleções
* **História de Usuário Vinculadas:** [US12 - Seleção e salvamento de obras]().
* **Objetivo:** Espaço pessoal onde o professor consulta e gerencia as obras das quais tem interesse, seja para planejamento de aula ou avaliação.

#### Componentes e Interações (Figma)
* **Cabeçalho da Tela :** Título *"Obras Selecionadas"* acompanhado da descrição *"Obras que você separou para avaliação pedagógica"*.
* **Lista de Cards Salvos:**
    * Apresentação resumida dos livros favoritados (Capa, título e autor).
    * Opção de navegação para abrir o detalhe da obra.
    * Botão/ícone para remover a obra da seleção pessoal.

### 3.4. Tela: Perfil do Professor
* **História de Usuário Vinculadas:** [US10 - Informações pessoais]().
* **Objetivo:** Gerenciamento de dados pessoais do professor.

#### Componentes e Interações (Figma)
* **Identificação do Usuário:** Nome completo (*ex: Ana Silva*) e e-mail institucional.
* **Card "Minhas Informações:** Formulário para visualização do e-mail e atualização nome completo e escola/instituição associada.
* **Card "Fale Conosco":** Atalho/Formulário de suporte para envio de mensagens direcionadas a equipe da editora
* **Botão de "`Sair`":** Botão vermelho no rodapé para encerrar a sessão (Logout).

### 3.5. Tela: Menu Lateral
* **História de Usuário Vinculadas:** [US18 - Navegação institucionais]().
* **Objetivo:** Barra lateral de acesso rápido pelas paginas institucionais.


#### Componentes e Interações (Figma)
* **Lista de Opções de Navegação:** `Catálogo Geral`, `Editora`, `PNLD`, `Anima Kids`, `Sobre Nós`.
* **Rodapé Institucional:** Links diretos para Termo de Uso, Política de Privacidade e ícones para redes sociais (Facebook, Instagram, Twitter, YouTube).


