# Colli Books

Bem-vindo à documentação do produto **Colli Books** — a plataforma de consulta ao acervo por disciplina, voltada a professores.

!!! info "Sobre este projeto"
    Documentação viva do projeto desenvolvido na disciplina de **TPPE** (Técnicas de Programação para Engenharia) da Universidade de Brasília, em parceria com a **Colli Books Editora**.

---

## Resumo do produto

O sistema resolve um problema único: **um professor precisa descobrir quais obras do acervo servem à disciplina que leciona.** A editora cadastra o professor, ele recebe um convite, define sua senha, busca por disciplina (ex.: Matemática) e encontra as obras daquela área com o material pedagógico correspondente.

### Perfis de usuário

| Perfil | Responsabilidade |
| --- | --- |
| **Professor** | Consome o acervo. Busca, consulta e baixa material. |
| **Administrador** | Alimenta o acervo e controla quem tem acesso. |

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
| `MUST` | 14 | 54 |
| `SHOULD` | 4 | 12 |
| **Total** | **18** | **66** |

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
