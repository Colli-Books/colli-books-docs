# Notas da reunião com o cliente

Anotações brutas levantadas com o cliente (Diego — Colli Books Editora) sobre o backlog da PC1. Cada seção agrupa as dúvidas e ajustes por épico.

!!! info "Ideias adicionais mencionadas"
    - Área do professor: material didático, livros disponibilizados para escolas e professores, obter perguntas relacionadas às matérias, **joguinhos** (ex.: Kahoot) — ideia de utilizar IA integrada.
    - Área do cliente: comprar coisas (substituir a loja dele), colocar no carrinho.
    - Site em WordPress: **manter o que funciona**.
    - A mais: adicionar **"reels"** como novelinha de cada livro.

---

## Épico 1 — Acesso e Contas

- **US01** — O administrador deve cadastrar tudo ou somente enviar o convite de e-mail e o próprio professor cadastra as informações pertinentes?
    - Seleciona as matérias relevantes.
    - Cadastra informações pessoais.
- **US02** — O professor pode solicitar a senha via reenvio do link caso tenha expirado?
    - Link só é reenviado se não tiver senha cadastrada ainda.
    - Não precisa solicitar novamente para a editora.
- **US04** — É necessário esse critério?
    - "QUANDO estou logado, ENTÃO posso alterar minha senha informando a senha atual."
- **US05** — A data do último acesso é necessária?
    - As outras informações não são suficientes?
    - "QUANDO reenvio o convite de um professor pendente, ENTÃO um novo link é gerado e o anterior é invalidado." — **contradiz a US01**, que diz que o link não é enviado quando o usuário já está cadastrado/convidado.
- **Ação:** criar nova história de usuário com acesso do administrador e redefinição de senha.

---

## Épico 2 — Busca do Acervo por Disciplina

- **US09** — revisar critérios de aceitação.
- **US10** — confirmar se as disciplinas são pré-cadastradas antes ou pelo professor e podem ser alteradas.
- **US11** — facilmente descartável se o escopo ficar grande.

---

## Épico 3 — Material Pedagógico

- **US12** — o que seriam os materiais pedagógicos?
    - As perguntas criadas pela IA?
    - **Ação:** necessidade de uma nova US informando como são visualizadas essas perguntas da IA.
- **US13** — facilmente descartável se o escopo ficar grande.

---

## Épico 4 — Gestão do Acervo (Administrador)

!!! danger "IMPORTANTE"
    Entender como está sendo acessada as informações, se tem um banco de dados e como são adicionadas novas informações.

- **US15** — Disciplinas ainda não fazem parte das informações guardadas no banco — verificar a necessidade de mantê-las.
- **US17** — Verificar a necessidade de criar essa seção de material pedagógico.
    - É mais válido obter perguntas da IA ou adicionar aquisição de material pedagógico?
    - Material pedagógico ainda não é armazenado.
- **US18** — facilmente descartável se o escopo ficar grande.

---

## Geral

- Cadastrar obras no acervo e vincular a matérias — **professores podem fazer esse vínculo?**
