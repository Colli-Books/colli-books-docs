# Épico 1 — Acesso e Contas

Conjunto de histórias que controlam quem entra no sistema e como. O acesso é sempre iniciado pelo administrador — não há auto-cadastro.

---

## US01 — Cadastro de professor pelo administrador `MUST` · 3 pts

**Como** Diego (Administrador), **posso** cadastrar um professor informando nome, e-mail, escola e disciplinas, **para que** somente educadores selecionados pela editora tenham acesso ao acervo.

**Critérios de aceitação**

- DADO que estou no painel administrativo, QUANDO cadastro um professor com os campos obrigatórios, ENTÃO a conta é criada com status "Convite pendente" e um link de convite é gerado.
- ENTÃO o link de convite é exibido para cópia, permitindo o envio por e-mail ou WhatsApp.
- QUANDO informo um e-mail já cadastrado, ENTÃO vejo mensagem de erro e nenhuma conta é duplicada.
- ENQUANTO a senha não for definida, o login com esse e-mail é bloqueado.

??? question "Dúvida levantada com o cliente"
    O administrador deve cadastrar tudo ou somente enviar o convite de e-mail e o próprio professor cadastra as informações pertinentes (seleciona as matérias relevantes, cadastra informações pessoais)? Ver [Notas da reunião](../cliente/notas.md#epico-1-acesso-e-contas).

---

## US02 — Primeiro acesso e definição de senha `MUST` · 3 pts

**Como** Paulo (Professor), **posso** abrir o link de convite e definir minha própria senha, **para que** eu acesse a plataforma sem receber uma senha por mensagem.

**Critérios de aceitação**

- DADO que abro um link de convite válido, ENTÃO vejo meu e-mail já preenchido como usuário e um formulário para definir a senha.
- QUANDO defino uma senha com no mínimo 8 caracteres e confirmo, ENTÃO minha conta é ativada, o link deixa de ser válido e sou autenticado.
- QUANDO o link está expirado ou já foi utilizado, ENTÃO vejo mensagem orientando a solicitar novo convite à editora.
- A senha é armazenada com hash.

??? question "Dúvida levantada com o cliente"
    O professor pode solicitar a senha via reenvio do link caso tenha expirado? — link só é reenviado se não tiver senha cadastrada ainda; não precisa solicitar novamente para a editora. Ver [Notas da reunião](../cliente/notas.md#epico-1-acesso-e-contas).

---

## US03 — Autenticação `MUST` · 2 pts

**Como** professor com conta ativa, **posso** entrar e sair do sistema usando meu e-mail e senha, **para que** meu acesso ao acervo seja pessoal e protegido.

**Critérios de aceitação**

- DADO que informo credenciais corretas, QUANDO clico em "Entrar", ENTÃO sou levado à tela inicial e vejo meu nome no cabeçalho.
- QUANDO as credenciais estão incorretas, ENTÃO vejo mensagem genérica, sem revelar se o e-mail existe.
- QUANDO acesso uma página restrita sem estar logado, ENTÃO sou redirecionado ao login.
- QUANDO clico em "Sair", ENTÃO a sessão é encerrada.

---

## US04 — Redefinição de senha `MUST` · 3 pts

**Como** Paulo, **posso** redefinir minha senha a qualquer momento por e-mail, **para que** eu recupere o acesso sem depender da editora.

**Critérios de aceitação**

- DADO que informo meu e-mail em "Esqueci minha senha", ENTÃO recebo um link de redefinição com prazo de validade.
- QUANDO uso o link, ENTÃO defino uma nova senha e o link deixa de ser válido.
- QUANDO o e-mail não existe na base, ENTÃO a mensagem exibida é a mesma, para não revelar quais contas existem.
- QUANDO estou logado, ENTÃO posso alterar minha senha informando a senha atual.

??? question "Dúvida levantada com o cliente"
    É necessário esse último critério (alterar senha logado informando a senha atual)? Ver [Notas da reunião](../cliente/notas.md#epico-1-acesso-e-contas).

---

## US05 — Gestão de acessos `SHOULD` · 3 pts

**Como** Diego, **posso** reenviar convites e desativar ou reativar o acesso de um professor, **para que** eu mantenha a base de usuários sob controle ao longo do tempo.

**Critérios de aceitação**

- DADO que acesso a lista de professores, ENTÃO vejo nome, e-mail, escola, disciplinas, status e data do último acesso.
- QUANDO reenvio o convite de um professor pendente, ENTÃO um novo link é gerado e o anterior é invalidado.
- QUANDO desativo um professor, ENTÃO ele perde o acesso imediatamente, sem ser excluído da base.
- QUANDO reativo um professor, ENTÃO ele volta a acessar com a senha que já possuía.

??? question "Dúvidas levantadas com o cliente"
    - A data do último acesso é necessária? As outras informações não são suficientes?
    - O critério de reenvio de convite parece contradizer a US01 (que diz que o link não é enviado quando o usuário já está cadastrado/convidado).
    - **Ação:** criar nova história de usuário com acesso do administrador e redefinição de senha. Ver [Notas da reunião](../cliente/notas.md#epico-1-acesso-e-contas).
