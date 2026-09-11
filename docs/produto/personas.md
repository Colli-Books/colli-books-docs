# Personas

O sistema tem dois perfis de usuário. As personas abaixo guiam as decisões de produto e priorização do backlog.

---

## Persona 1 — Paulo Menezes, Professor

Professor da rede de ensino, leciona uma ou duas disciplinas. Procura obras literárias que dialoguem com o conteúdo que precisa ensinar. Acessa o sistema com frequência baixa, geralmente no planejamento do bimestre, muitas vezes pelo celular.

| O que faz (Atividades) | O que espera (Objetivos) |
| --- | --- |
| Busca obras pelo nome em um campo de busca | Localizar um livro específico rapidamente |
| Filtra a busca por tema e escolaridade | Ver apenas os livros que servem à sua área e à faixa etária da turma |
| Vincula-se aos temas e escolaridades que leciona | Que o sistema lhe apresente as obras da sua área |
| Abre o detalhe de uma obra | Avaliar se o livro atende ao seu planejamento |
| Guarda obras que pretende indicar à coordenação | Manter uma seleção pessoal salva entre acessos |
| Acessa o link de compra da obra | Comprar na loja oficial da editora |

---

## Persona 2 — Diego, Administrador da Editora

Responsável por manter o acervo e a base de professores. Conhece o catálogo a fundo, mas não tem formação técnica. Precisa cadastrar, classificar e liberar acesso sem depender de desenvolvedor.

| O que faz (Atividades) | O que espera (Objetivos) |
| --- | --- |
| Cadastra e edita as obras do acervo | Manter o catálogo atualizado por conta própria, em um só lugar |
| Cria temas e escolaridades e os vincula às obras | Que a busca do professor devolva resultado coerente |
| Cadastra os professores a partir de um e-mail | Controlar exatamente quem entra na plataforma |

!!! note "Diretriz de interface para o administrador"
    A editora já opera diariamente o painel do WordPress. O painel administrativo deste sistema deve seguir o mesmo modelo mental — listagem com busca e filtro, botão de adicionar, formulário de campos, salvar — sem inventar padrões de interação novos. Familiaridade reduz o custo de adoção e pesa na avaliação do cliente na PC3.
