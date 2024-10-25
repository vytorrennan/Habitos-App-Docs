## Número do Caso de Uso: UC01
### Nome do Caso de Uso: Gerenciar Conta de Usuário

**Ator(es):** Usuário

### Descrição:
Este caso de uso permite ao usuário criar uma nova conta.

### Pré-Condições:
- O usuário deve ter um endereço de e-mail válido para o cadastro.

### Pós-Condições:
- A nova conta é criada, permitindo o login do usuário.
- As informações da conta são atualizadas no sistema.

### Cenário Principal:

#### Criar Conta
1. [IN] O usuário clica na opção "Cadastrar nova conta".
2. [OUT] O sistema redireciona para a página de cadastro.
3. [IN] O usuário preenche o formulário de cadastro com as informações necessárias. [Campos], [Exceção 1], [Exceção 2].
4. [OUT] O sistema conclui o cadastro.

### Cenário Alternativo:
- **E-mail já cadastrado:**
    1. [IN] O usuário tenta cadastrar-se com um e-mail que já foi utilizado.
    2. [OUT] O sistema exibe uma mensagem de erro informando que o e-mail já está em uso.

### Exceções:
- **Exceção 1: Dados inválidos:**
    1. [OUT] O sistema exibe uma mensagem informando que algum campo contém dados inválidos.
    2. [IN] O usuário corrige os campos.
    3. [OUT] O sistema valida os dados novamente.

- **Exceção 2: Campo obrigatório em branco:**
    1. [IN] O usuário tenta enviar o formulário com campos obrigatórios em branco.
    2. [OUT] O sistema exibe uma mensagem de erro e solicita que o usuário preencha todos os campos obrigatórios.

### Campos:
- Nome completo
- E-mail
- Senha
- Confirmação de senha


## Número do Caso de Uso: UC02
### Nome do Caso de Uso: Gerenciar Notas
**Ator(es):** Usuário autenticado  
**Descrição:**  
Este caso de uso permite que o usuário autenticado crie, edite, visualize e apague notas no sistema, organizando-as por categorias.  
**Pré-Condições:**  
- O usuário deve estar autenticado no sistema.
  
**Pós-Condições:**  
- As informações das notas são atualizadas no sistema.
- As notas podem ser criadas, editadas ou removidas, conforme a operação realizada.

### Fluxo Principal

#### Criar Nota
1. [IN] O usuário seleciona a opção "Criar nova nota".
2. [OUT] O sistema exibe um formulário de criação de nota.
3. [IN] O usuário preenche os campos obrigatórios (título, conteúdo, categoria).
4. [IN] O usuário clica em "Salvar".
5. [OUT] O sistema valida as informações e salva a nova nota.
6. [OUT] O sistema exibe uma mensagem de confirmação.

#### Editar Nota
1. [IN] O usuário acessa a opção "Gerenciar Notas".
2. [OUT] O sistema exibe uma lista de notas criadas.
3. [IN] O usuário escolhe uma nota da lista e clica em "Editar".
4. [OUT] O sistema exibe um formulário com as informações atuais da nota.
5. [IN] O usuário modifica as informações e clica em "Salvar".
6. [OUT] O sistema valida as informações e atualiza a nota.
7. [OUT] O sistema exibe uma mensagem de confirmação.

#### Visualizar Nota
1. [IN] O usuário acessa a opção "Gerenciar Notas".
2. [OUT] O sistema exibe uma lista de notas criadas.
3. [IN] O usuário escolhe uma nota da lista e clica em "Visualizar".
4. [OUT] O sistema exibe as informações detalhadas da nota.

#### Apagar Nota
1. [IN] O usuário acessa a opção "Gerenciar Notas".
2. [OUT] O sistema exibe uma lista de notas criadas.
3. [IN] O usuário escolhe uma nota da lista e clica em "Apagar".
4. [OUT] O sistema solicita confirmação para apagar a nota.
5. [IN] O usuário confirma a exclusão.
6. [OUT] O sistema remove a nota da lista.
7. [OUT] O sistema exibe uma mensagem de confirmação.

### Fluxo Alternativo

#### Erro ao Criar Nota
- [OUT] Se o usuário não preencher todos os campos obrigatórios, o sistema exibe uma mensagem de erro e solicita correção.

#### Erro ao Apagar Nota
- [OUT] Se houver um erro durante a exclusão (ex: falha no sistema), o sistema exibe uma mensagem de erro informando o motivo.

### Requisitos Não Funcionais
- **RNF 1:** O sistema deve garantir que o conteúdo das notas seja salvo de forma segura e criptografada no banco de dados.
- **RNF 2:** O sistema deve ser capaz de lidar com múltiplas notas criadas por diferentes usuários sem comprometer o desempenho.
- **RNF 3:** O sistema deve fornecer uma interface de usuário intuitiva e responsiva para gerenciar notas.

