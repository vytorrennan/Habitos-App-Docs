# NOME DO CASO DE USO CRÍTICO:
Login de Usuário

## ATOR:
Usuário

## OBJETIVO:
Permitir que o usuário acesse sua conta no sistema de maneira segura, utilizando credenciais válidas.

## PRÉ-CONDIÇÕES:
O usuário deve ter uma conta registrada no sistema.

## PÓS-CONDIÇÕES:
O sistema autentica o usuário e redireciona-o para a tela principal, exibindo uma mensagem de boas-vindas.

## CENÁRIO PRINCIPAL:
1. **[INT]** O usuário acessa a tela de login do aplicativo.
2. **[INT]** O usuário insere seu e-mail e senha nos campos correspondentes.
3. **[INT]** O usuário clica no botão "Login".
4. **[OUT]** O sistema valida as credenciais (e-mail e senha) contra os dados armazenados no banco de dados.
5. **[OUT]** Se as credenciais forem válidas, o sistema autentica o usuário com sucesso.
6. **[OUT]** O sistema exibe uma mensagem de boas-vindas ao usuário.
7. **[OUT]** O sistema redireciona o usuário para a tela inicial, onde ele pode gerenciar seus hábitos.

## CENÁRIOS ALTERNATIVOS:

### E1: O usuário insere credenciais inválidas (e-mail ou senha incorretos).
- **[OUT]** O sistema exibe uma mensagem de erro informando que o e-mail ou senha estão incorretos.
- **[OUT]** O sistema solicita que o usuário tente novamente.
- **[INT]** O usuário pode tentar novamente ou clicar em "Esqueci minha senha" para iniciar o processo de recuperação de senha.

### E2: O usuário excede o número máximo de tentativas de login com falhas.
- **[OUT]** O sistema bloqueia temporariamente a conta do usuário como medida de segurança.
- **[OUT]** O sistema exibe uma mensagem informando que a conta foi bloqueada devido a tentativas de login falhadas.
- **[OUT]** O usuário deve seguir o processo de recuperação de conta ou aguardar o tempo de desbloqueio.

## REGRAS DE NEGÓCIO:
- **RN01:** O sistema deve garantir que as credenciais do usuário (e-mail e senha) sejam armazenadas de forma segura, utilizando hash e criptografia.
- **RN02:** O sistema deve bloquear a conta do usuário após 5 tentativas de login falhadas consecutivas.
- **RN03:** O sistema deve redirecionar o usuário para a página de recuperação de senha caso ele clique em "Esqueci minha senha".
- **RN04:** O sistema deve registrar todas as tentativas de login, com informações como data, hora e endereço IP, para fins de auditoria e segurança.

## REQUISITOS FUNCIONAIS:
- **RF01:** O sistema deve permitir que o usuário insira e-mail e senha para autenticação.
- **RF02:** O sistema deve validar as credenciais do usuário contra o banco de dados.
- **RF03:** O sistema deve exibir mensagens de erro detalhadas, como "Senha incorreta" ou "E-mail não encontrado", para guiar o usuário.

