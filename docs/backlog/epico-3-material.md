# Épico 3 — Material Pedagógico

Histórias que tratam do material de apoio vinculado a cada obra — o que o professor baixa para preparar a aula.

---

## US12 — Materiais da obra `MUST` · 3 pts

**Como** Paulo, **posso** ver os materiais pedagógicos vinculados a uma obra, **para que** eu saiba com que apoio didático posso contar.

**Critérios de aceitação**

- DADO que estou na página de uma obra, ENTÃO vejo os materiais com título, tipo (plano de aula, atividade complementar, guia de leitura) e tamanho do arquivo.
- QUANDO a obra não possui material, ENTÃO a seção informa que ainda não há material disponível.

??? question "Dúvidas levantadas com o cliente"
    - O que seriam os materiais pedagógicos? As perguntas criadas pela IA?
    - **Ação:** necessidade de uma nova US informando como são visualizadas essas perguntas da IA. Ver [Notas da reunião](../cliente/notas.md#epico-3-material-pedagogico).

---

## US13 — Download de material `MUST` · 3 pts

**Como** Paulo, **posso** baixar o material pedagógico em PDF, **para que** eu o utilize na preparação da aula.

**Critérios de aceitação**

- QUANDO clico em "Baixar", ENTÃO o arquivo é transferido e o evento é registrado com data, professor e material.
- QUANDO um usuário não autenticado acessa a URL direta do arquivo, ENTÃO o download é negado.

??? tip "Descartável"
    Facilmente descartável se o escopo ficar grande. Ver [Notas da reunião](../cliente/notas.md#epico-3-material-pedagogico).
