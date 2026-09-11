# Épico 1 — Acesso e Contas

Conjunto de histórias que controlam quem entra no sistema e como. O acesso é sempre iniciado pelo administrador — não há auto-cadastro. O administrador é pré-cadastrado no banco de dados; não há fluxo de cadastro de administrador no sistema.

---

## US01 — Cadastro de professor pelo administrador `MUST` · 3 pts

**Como** Diego (Administrador), **posso** cadastrar um professor a partir de um e-mail, **para que** somente educadores selecionados pela editora tenham acesso ao acervo.

**Critérios de aceitação**

- DADO que estou no painel administrativo, QUANDO cadastro um professor informando o e-mail, ENTÃO a conta é criada com status "Convite pendente" e um link de convite é gerado.
- ENTÃO o link de convite é exibido para cópia, permitindo o envio por e-mail ou WhatsApp.
- QUANDO informo um e-mail já cadastrado, ENTÃO vejo mensagem de erro e nenhuma conta é duplicada.
- ENQUANTO a senha não for definida, o login com esse e-mail é bloqueado.

---

## US02 — Primeiro acesso e definição de senha `MUST` · 3 pts

**Como** Paulo (Professor), **posso** abrir o link de convite e definir minha própria senha, **para que** eu acesse a plataforma sem receber uma senha por mensagem.

**Critérios de aceitação**

- DADO que abro um link de convite válido, ENTÃO vejo meu e-mail já preenchido como usuário e um formulário para definir a senha.
- QUANDO defino uma senha com no mínimo 8 caracteres e confirmo, ENTÃO minha conta é ativada, o link deixa de ser válido e sou autenticado.
- QUANDO o link está expirado e a senha ainda não foi definida, ENTÃO vejo a opção de solicitar um novo link de convite, sem precisar acionar a editora.
- QUANDO o link já foi utilizado (senha já definida), ENTÃO vejo mensagem orientando a usar o "Esqueci minha senha" para redefinir o acesso.
- A senha é armazenada com hash.

---

## US03 — Autenticação `MUST` · 2 pts

**Como** professor ou administrador com conta ativa, **posso** entrar e sair do sistema usando meu e-mail e senha, **para que** meu acesso seja pessoal e protegido.

**Critérios de aceitação**

- DADO que informo credenciais corretas, QUANDO clico em "Entrar", ENTÃO sou levado à tela inicial.
- QUANDO as credenciais estão incorretas, ENTÃO vejo mensagem genérica, sem revelar se o e-mail existe.
- QUANDO acesso uma página restrita sem estar logado, ENTÃO sou redirecionado ao login.
- QUANDO clico em "Sair", ENTÃO a sessão é encerrada.

---

## US04 — Redefinição de senha `MUST` · 3 pts

**Como** usuário do sistema, **posso** redefinir minha senha a qualquer momento por e-mail ("Esqueci minha senha"), **para que** eu recupere o acesso sem depender da editora.

**Critérios de aceitação**

- DADO que informo meu e-mail em "Esqueci minha senha", ENTÃO recebo um link de redefinição com prazo de validade.
- QUANDO uso o link, ENTÃO defino uma nova senha e o link deixa de ser válido.
- QUANDO o e-mail não existe na base, ENTÃO a mensagem exibida é a mesma, para não revelar quais contas existem.

---

## US05 — Autenticação do administrador `MUST` · 2 pts

**Como** Diego (Administrador), **posso** entrar e sair do painel administrativo usando meu e-mail e senha, **para que** meu acesso seja pessoal e protegido.

**Critérios de aceitação**

- DADO que informo credenciais corretas, QUANDO clico em "Entrar", ENTÃO sou levado ao painel administrativo e vejo meu nome no cabeçalho.
- QUANDO as credenciais estão incorretas, ENTÃO vejo mensagem genérica, sem revelar se o e-mail existe.
- QUANDO acesso uma página administrativa sem estar logado como administrador, ENTÃO sou redirecionado ao login.
- QUANDO clico em "Sair", ENTÃO a sessão é encerrada.
- A conta do administrador é pré-cadastrada no banco de dados com e-mail e senha; não há fluxo de cadastro de administrador no sistema.

---

## US06 — Redefinição de senha do administrador `MUST` · 3 pts

**Como** Diego (Administrador), **posso** redefinir minha senha a qualquer momento por e-mail ("Esqueci minha senha"), **para que** eu recupere o acesso ao painel sem intervenção externa.

**Critérios de aceitação**

- DADO que informo meu e-mail em "Esqueci minha senha", ENTÃO recebo um link de redefinição com prazo de validade.
- QUANDO uso o link, ENTÃO defino uma nova senha e o link deixa de ser válido.
- QUANDO o e-mail não existe na base, ENTÃO a mensagem exibida é a mesma, para não revelar quais contas existem.
