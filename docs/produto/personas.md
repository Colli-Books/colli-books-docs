# Personas

O sistema tem dois perfis de usuário. As personas abaixo guiam as decisões de produto e priorização do backlog.

---

## Persona 1 — Paulo Menezes, Professor

Professor da rede de ensino, leciona uma ou duas disciplinas. Procura obras literárias que dialoguem com o conteúdo que precisa ensinar e material de apoio para trabalhá-las em sala. Acessa o sistema com frequência baixa, geralmente no planejamento do bimestre, muitas vezes pelo celular.

| O que faz (Atividades) | O que espera (Objetivos) |
| --- | --- |
| Busca obras pela disciplina que leciona | Ver apenas os livros que servem à sua área, sem percorrer o acervo inteiro |
| Verifica se a obra é adequada à etapa de ensino da turma | Filtrar por Educação Infantil, Fundamental I, Fundamental II ou Médio |
| Baixa material pedagógico para preparar a aula | Encontrar o material vinculado à obra, e não solto em um drive |
| Guarda obras que pretende indicar à coordenação | Manter uma seleção pessoal salva entre acessos |

---

## Persona 2 — Diego, Administrador da Editora

Responsável por manter o acervo e a base de professores. Conhece o catálogo a fundo, mas não tem formação técnica. Precisa cadastrar, classificar e liberar acesso sem depender de desenvolvedor.

| O que faz (Atividades) | O que espera (Objetivos) |
| --- | --- |
| Cadastra e atualiza as obras do acervo | Manter o catálogo atualizado por conta própria, em um só lugar |
| Define quais disciplinas existem e classifica cada obra | Que a busca do professor devolva resultado coerente |
| Publica o material pedagógico de cada obra | Vincular o arquivo diretamente à obra correspondente |
| Cadastra os professores e envia o convite de acesso | Controlar exatamente quem entra na plataforma |

!!! note "Diretriz de interface para o administrador"
    A editora já opera diariamente o painel do WordPress. O painel administrativo deste sistema deve seguir o mesmo modelo mental — listagem com busca e filtro, botão de adicionar, formulário de campos, salvar — sem inventar padrões de interação novos. Familiaridade reduz o custo de adoção e pesa na avaliação do cliente na PC3.
