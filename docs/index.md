# Colli Books

Bem-vindo à documentação do produto **Colli Books** — a plataforma de consulta ao acervo por tema e escolaridade, voltada a professores.

!!! info "Sobre este projeto"
    Documentação viva do projeto desenvolvido na disciplina de **TPPE** (Técnicas de Programação para Engenharia) da Universidade de Brasília, em parceria com a **Colli Books Editora**.

---

## Resumo do produto

O sistema resolve um problema único: **um professor precisa descobrir quais obras do acervo contém o tema que procura.** A editora cadastra o professor a partir de um e-mail, ele recebe um convite, define sua senha, busca obras pelo nome, filtra por tema e escolaridade, e encontra as obras daquela área — com um link direto para compra na loja oficial.

### Perfis de usuário

| Perfil | Responsabilidade |
| --- | --- |
| **Professor** | Consome o acervo. Busca, filtra, consulta, seleciona e salva obras. |
| **Administrador** | Alimenta o acervo, cria temas e escolaridades, vincula-os aos livros e controla quem tem acesso. |

Não há área de cliente final, carrinho, orçamento ou venda dentro do sistema. A venda continua na loja oficial existente.

---

## Navegação rápida

- [:material-eye: Visão do produto](produto/visao.md) — decisões de acesso e técnicas centrais.
- [:material-account-group: Personas](produto/personas.md) — Paulo (Professor) e Diego (Administrador).
- [:material-format-list-bulleted: Backlog do produto](backlog/index.md) — 18 histórias de usuário organizadas em 4 épicos.
- [:material-note-text: Notas da reunião com o cliente](cliente/notas.md) — dúvidas e ajustes levantados.
- [:material-help-circle-outline: Pontos a confirmar](cliente/pontos-a-confirmar.md) — perguntas em aberto com a editora.

---

## Resumo do backlog

| Prioridade | Quantidade | Pontos |
| --- | --- | --- |
| `MUST` | 15 | 54 |
| `SHOULD` | 3 | 7 |
| **Total** | **18** | **61** |

**Prioridade:** `MUST` = essencial ao MVP · `SHOULD` = importante, entra se houver folga.
**Estimativa:** story points (Fibonacci).

---

## Como rodar esta documentação localmente

```bash
# Instalar as dependências
pip install -r requirements.txt

# Servir localmente em http://127.0.0.1:8000
mkdocs serve

# Gerar o site estático em site/
mkdocs build
```

Consulte o [Sobre](sobre.md) para mais detalhes sobre a estrutura deste repositório.
