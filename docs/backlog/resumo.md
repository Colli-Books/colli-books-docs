# Resumo do backlog

| Prioridade | Quantidade | Pontos |
| --- | --- | --- |
| `MUST` | 14 | 54 |
| `SHOULD` | 4 | 12 |
| **Total** | **18** | **66** |

---

## Nota sobre a carga do acervo

O acervo da editora tem cerca de **60 obras**, mantidas hoje em site WordPress e em catálogo PDF. Nenhuma dessas fontes contém a classificação por disciplina, que é o dado central deste sistema e precisará ser definido manualmente pela editora, obra a obra.

**Em produção**, o cadastro é feito pela editora no painel administrativo do sistema ([US14](epico-4-gestao.md#us14-cadastro-e-edicao-de-obras-must-8-pts) a [US18](epico-4-gestao.md#us18-obras-em-destaque-should-3-pts)). A equipe de desenvolvimento não mantém o acervo após o encerramento da disciplina. O modelo é o mesmo que a editora já pratica no WordPress: formulário, upload de imagem e publicação, sem contato com código.

### Não há estória de importação em lote

Para 60 obras, o cadastro manual é mais barato que construir e validar um importador, e a extração automática a partir de PDF é imprecisa demais para um MVP.

### Dados de teste

A equipe fará a carga de uma amostra de **15 a 20 obras reais**, retiradas do site da editora, por meio de um *script de seed* versionado no repositório e executado na subida do ambiente via Docker Compose. Isso garante que qualquer integrante suba a aplicação com a mesma base e que a demonstração seja reproduzível em qualquer máquina.

!!! warning "Cobertura mínima da amostra"
    A amostra deve cobrir **pelo menos 5 disciplinas distintas e todas as etapas de ensino** — com dados concentrados em uma única disciplina, a busca da [US06](epico-2-busca.md#us06-busca-por-disciplina-must-5-pts) parece não funcionar durante a apresentação, ainda que esteja correta.

O *script de seed* é tarefa técnica de infraestrutura, não funcionalidade do produto, e por isso não figura como estória do backlog.
