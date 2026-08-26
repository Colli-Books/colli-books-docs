# Colli Books — Documentação

Documentação do produto **Colli Books** construída com [MkDocs](https://www.mkdocs.org/) e o tema [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

## Visão geral

Plataforma de consulta ao acervo por disciplina, voltada a professores, desenvolvida como projeto da disciplina de TPPE/UnB em parceria com a Colli Books Editora.

## Como rodar localmente

```bash
# Ambiente virtual (opcional, recomendado)
python3 -m venv .venv
source .venv/bin/activate

# Instalar dependências
pip install -r requirements.txt

# Servir em http://127.0.0.1:8000
mkdocs serve

# Gerar site estático em site/
mkdocs build
```

## Estrutura

```
colli-books-docs/
├── mkdocs.yml          # Configuração do MkDocs Material
├── requirements.txt    # Dependências
└── docs/               # Conteúdo em Markdown
    ├── index.md
    ├── produto/        # Visão, personas, escopo
    ├── backlog/        # Histórias de usuário por épico
    └── cliente/        # Notas da reunião e pontos a confirmar
```

## Publicar no GitHub Pages

```bash
mkdocs gh-deploy
```
