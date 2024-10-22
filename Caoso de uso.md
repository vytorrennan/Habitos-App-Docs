
# Casos de Uso - Aplicativo de Hábitos

## UC01 - **Login**

**NOME DO CASO DE USO:**  
Login

**ATOR:**  
Usuário

**OBJETIVO:**  
Permitir que o usuário acesse o sistema com suas credenciais.

**PRÉ-CONDIÇÕES:**  
O usuário deve possuir uma conta previamente cadastrada.

**PÓS-CONDIÇÕES:**  
O sistema autentica o usuário e exibe uma mensagem de boas-vindas.

**CENÁRIO PRINCIPAL:**

1. [INT] O usuário abre o aplicativo e acessa a página de login.
2. [INT] O usuário insere o e-mail e a senha.
3. [INT] O usuário clica no botão "Login".
4. [OUT] O sistema autentica o usuário.
5. [OUT] O sistema exibe uma mensagem de boas-vindas e redireciona o usuário para a tela inicial.

**CENÁRIOS ALTERNATIVOS:**

- **E1:** O sistema não consegue autenticar o usuário devido a credenciais incorretas.  
  - O sistema exibe uma mensagem de erro informando que o e-mail ou a senha estão incorretos.

- **E2:** O usuário não insere as credenciais.  
  - O sistema solicita que o usuário preencha os campos obrigatórios.

**REGRAS DE NEGÓCIO:**

- RN01: O sistema deve limitar o número de tentativas de login para evitar ataques de força bruta.

---

## UC02 - **Registro de Conta**

**NOME DO CASO DE USO:**  
Registro de Conta

**ATOR:**  
Usuário

**OBJETIVO:**  
Permitir que o usuário crie uma nova conta.

**PRÉ-CONDIÇÕES:**  
O usuário não deve ter uma conta previamente registrada com o mesmo e-mail ou nome de usuário.

**PÓS-CONDIÇÕES:**  
O sistema cria uma nova conta e exibe uma mensagem de confirmação.

**CENÁRIO PRINCIPAL:**

1. [INT] O usuário acessa a página de registro.
2. [INT] O usuário preenche os campos de registro (nome, e-mail, senha).
3. [INT] O usuário clica no botão "Registrar".
4. [OUT] O sistema valida as informações e cria a nova conta.
5. [OUT] O sistema exibe uma mensagem de confirmação e redireciona o usuário para a tela inicial.

**CENÁRIOS ALTERNATIVOS:**

- **E1:** O e-mail ou nome de usuário já está registrado no sistema.  
  - O sistema exibe uma mensagem informando que o e-mail ou nome de usuário já foi utilizado.

- **E2:** O usuário não preenche todos os campos obrigatórios.  
  - O sistema exibe uma mensagem solicitando o preenchimento dos campos faltantes.

**REGRAS DE NEGÓCIO:**

- RN01: O sistema deve validar se o e-mail inserido está em um formato correto.
- RN02: A senha deve ter um mínimo de 8 caracteres, incluindo letras e números.

---
## UC03 - **Criar Hábito**

**NOME DO CASO DE USO:**  
Criar Hábito

**ATOR:**  
Usuário

**OBJETIVO:**  
Permitir que o usuário crie um novo hábito com detalhes personalizados.

**PRÉ-CONDIÇÕES:**  
O usuário deve estar autenticado no sistema.

**PÓS-CONDIÇÕES:**  
O sistema salva o novo hábito e exibe uma mensagem de confirmação.

**CENÁRIO PRINCIPAL:**

1. [INT] O usuário acessa a página de criação de hábitos.
2. [INT] O usuário preenche os campos de nome, frequência, dias da semana e datas de início e término.
3. [INT] O usuário clica no botão "Salvar Hábito".
4. [OUT] O sistema valida as informações e salva o hábito no banco de dados.
5. [OUT] O sistema exibe um "toast" de confirmação com a mensagem "Hábito salvo".

**CENÁRIOS ALTERNATIVOS:**

- **E1:** O usuário não preenche todos os campos obrigatórios.  
  - O sistema exibe uma mensagem informando quais campos precisam ser preenchidos.

- **E2:** O hábito já existe com o mesmo nome.  
  - O sistema solicita que o usuário escolha um nome diferente para o hábito.

**REGRAS DE NEGÓCIO:**

- RN01: O nome do hábito deve ser único para o usuário.
- RN02: O sistema deve permitir que o usuário personalize a frequência e duração do hábito.

---

## UC04 - **Acessar Hábito**

**NOME DO CASO DE USO:**  
Acessar Hábito

**ATOR:**  
Usuário

**OBJETIVO:**  
Permitir que o usuário visualize os detalhes de um hábito específico.

**PRÉ-CONDIÇÕES:**  
O usuário deve estar autenticado no sistema e possuir hábitos cadastrados.

**PÓS-CONDIÇÕES:**  
O sistema exibe as informações do hábito selecionado.

**CENÁRIO PRINCIPAL:**

1. [INT] O usuário acessa a lista de hábitos cadastrados.
2. [INT] O usuário seleciona um hábito específico.
3. [OUT] O sistema busca os dados do hábito no banco de dados.
4. [OUT] O sistema exibe as informações detalhadas do hábito na tela do usuário.

**CENÁRIOS ALTERNATIVOS:**

- **E1:** O hábito selecionado não existe.  
  - O sistema exibe uma mensagem informando que o hábito não foi encontrado.

**REGRAS DE NEGÓCIO:**

- RN01: O sistema deve garantir que apenas o proprietário do hábito possa visualizá-lo.
- RN02: As informações do hábito devem ser exibidas de maneira clara, incluindo o progresso.

---

## UC05 - **Deletar Hábito**

**NOME DO CASO DE USO:**  
Deletar Hábito

**ATOR:**  
Usuário

**OBJETIVO:**  
Permitir que o usuário exclua um hábito existente.

**PRÉ-CONDIÇÕES:**  
O usuário deve estar autenticado e possuir hábitos cadastrados.

**PÓS-CONDIÇÕES:**  
O hábito é removido do sistema e o usuário recebe uma confirmação da exclusão.

**CENÁRIO PRINCIPAL:**

1. [INT] O usuário acessa a lista de hábitos.
2. [INT] O usuário seleciona o hábito que deseja excluir.
3. [INT] O sistema pergunta se o usuário confirma a exclusão.
4. [INT] O usuário confirma a exclusão.
5. [OUT] O sistema remove o hábito do banco de dados.
6. [OUT] O sistema exibe uma mensagem de confirmação da exclusão.

**CENÁRIOS ALTERNATIVOS:**

- **E1:** O usuário cancela a exclusão.  
  - O sistema mantém o hábito sem alterações.

**REGRAS DE NEGÓCIO:**

- RN01: O sistema deve solicitar confirmação do usuário antes de excluir qualquer hábito.
- RN02: O sistema deve garantir que apenas o proprietário do hábito possa excluí-lo.

---

## UC06 - **Logout**

**NOME DO CASO DE USO:**  
Logout

**ATOR:**  
Usuário

**OBJETIVO:**  
Permitir que o usuário encerre sua sessão e saia do aplicativo.

**PRÉ-CONDIÇÕES:**  
O usuário deve estar autenticado no sistema.

**PÓS-CONDIÇÕES:**  
O sistema encerra a sessão do usuário e o redireciona para a página de login.

**CENÁRIO PRINCIPAL:**

1. [INT] O usuário clica no botão "Logout".
2. [OUT] O sistema encerra a sessão do usuário.
3. [OUT] O sistema redireciona o usuário para a tela de login.

**CENÁRIOS ALTERNATIVOS:**

- **E1:** O sistema encontra um erro ao encerrar a sessão.  
  - O sistema exibe uma mensagem de erro e solicita que o usuário tente novamente.

**REGRAS DE NEGÓCIO:**

- RN01: O sistema deve encerrar todas as sessões ativas do usuário em diferentes dispositivos.
- RN02: O sistema deve garantir que os dados temporários do usuário sejam apagados após o logout.
