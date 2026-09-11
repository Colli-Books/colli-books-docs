# Resumo do backlog

| Prioridade | Quantidade | Pontos |
| --- | --- | --- |
| `MUST` | 15 | 54 |
| `SHOULD` | 3 | 7 |
| **Total** | **18** | **61** |

---

## Nota sobre a carga do acervo

O acervo da editora tem cerca de **60 obras**, mantidas hoje em site WordPress e em catálogo PDF. Nenhuma dessas fontes contém a classificação por tema e escolaridade, que é o dado central deste sistema e precisará ser definido manualmente pela editora, obra a obra.

**Em produção**, o cadastro é feito pela editora no painel administrativo do sistema ([US15](epico-3-gestao.md#us15-cadastro-e-edicao-de-obras-must-8-pts) a [US17](epico-3-gestao.md#us17-vinculo-entre-obra-temas-e-escolaridades-must-3-pts)). A equipe de desenvolvimento não mantém o acervo após o encerramento da disciplina. O modelo é o mesmo que a editora já pratica no WordPress: formulário, upload de imagem e publicação, sem contato com código.

### Não há estória de importação em lote

Para 60 obras, o cadastro manual é mais barato que construir e validar um importador, e a extração automática a partir de PDF é imprecisa demais para um MVP.

### Dados de teste

A equipe fará a carga de uma amostra de **15 a 20 obras reais**, retiradas do site da editora, por meio de um *script de seed* versionado no repositório e executado na subida do ambiente via Docker Compose. Isso garante que qualquer integrante suba a aplicação com a mesma base e que a demonstração seja reproduzível em qualquer máquina.

!!! warning "Cobertura mínima da amostra"
    A amostra deve cobrir **pelo menos 5 temas distintos e todas as escolaridades** — com dados concentrados em um único tema, a busca da [US07](epico-2-busca.md#us07-busca-de-obras-por-nome-must-3-pts) parece não funcionar durante a apresentação, ainda que esteja correta.

O *script de seed* é tarefa técnica de infraestrutura, não funcionalidade do produto, e por isso não figura como estória do backlog.
