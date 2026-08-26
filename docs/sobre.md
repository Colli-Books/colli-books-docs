# Sobre

Esta documentação descreve o produto **Colli Books**, plataforma de consulta ao acervo por disciplina voltada a professores, desenvolvida como projeto da disciplina de **TPPE** (Técnicas de Programação para Engenharia) da Universidade de Brasília em parceria com a **Colli Books Editora**.

---

## Estrutura do repositório

```
colli-books-docs/
├── mkdocs.yml          # Configuração do MkDocs Material
├── requirements.txt    # Dependências Python
├── docs/
│   ├── index.md        # Página inicial
│   ├── produto/        # Visão, personas e escopo
│   ├── backlog/        # Histórias de usuário por épico
│   ├── cliente/        # Notas da reunião e pontos a confirmar
│   └── imagens/        # Recursos visuais
└── site/               # Saída do build (gerada)
```

---

## Como rodar

### Pré-requisitos

- Python 3.10+
- `pip`

### Passo a passo

```bash
# 1. Criar e ativar um ambiente virtual (recomendado)
python3 -m venv .venv
source .venv/bin/activate

# 2. Instalar as dependências
pip install -r requirements.txt

# 3. Servir localmente
mkdocs serve
# Acesse http://127.0.0.1:8000

# 4. Gerar o site estático
mkdocs build
# O conteúdo fica em site/
```

---

## Como contribuir

1. Edite os arquivos Markdown em `docs/`.
2. Ajuste a navegação em `mkdocs.yml` (chave `nav`) quando adicionar ou remover páginas.
3. Verifique localmente com `mkdocs serve` antes de commitar.
4. O build pode ser publicado em GitHub Pages com `mkdocs gh-deploy`.
