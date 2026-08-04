### ATIVIDADE 5 CASOS DE SMOKE TEST, SANITY TEST, REGRESSION TEST

***Cenário: Uma nova versão de um sistema bancário foi implantada com correção no login e um ajuste na exibição do saldo tela inicial.**

### Smoke test:

**1ºCASO**

**ID**: SMK01

**TÍTULO**:Validação do login com credenciais válidas

**PRÉ CONDIÇÃO**: Usuário cadastrado no sistema

**PASSOS**: Usuário estar na tela de login, informar e-mail válido e senha válida, clicar no botão entrar

**RESULTADO ESPERADO**: Usuário realiza o login com sucesso

--------------------------------------------------------------



**2ºCASO**

**ID**: SMK02

**TÍTULO**: Validação do carregamento de informação após tela de login

**PRÉ-CONDIÇÃO**: Usuário possui uma conta cadastrada e realizou login com sucesso no sistema

**PASSOS**: Usuário estar na tela de login, informar e-mail e senha válidos, clicar no botão entrar, aguardar o carregamento da conta do usuário

**RESULTADO ESPERADO**: As informações  da conta são carregada corretamente após o login.

--------------------------------------------------------------------------------------

**3ºcaso**

**ID**: SMK03

**TÍTULO**: Transição entre as telas

**PRÉ-CONDIÇÃO**: Usuário estar autenticado no sistema  e possui acesso ao menu principal

**PASSOS**: Usuário estar na tela de login, informar e-mail e senha válidos, acessar serviços disponíveis no menu, retornar para a tela inicial.

**RESULTADO ESPERADO**: As telas são carregadas corretamente e a navegação entre elas funciona sem erros.

--------------------------------------------------------------------------------------

**4ºCASO**

**ID**: SMK04

**TÍTULO**: Validação da visualização do saldo na tela inicial após login

**PRÉ-CONDIÇÃO**: Usuário possui uma conta cadastrada com saldo disponível

**PASSOS**: Usuário estar na tela de login, informar e-mail e senha válidos, acessar a tela inicial da conta, verificar a área de exibição do saldo.

**RESULTADO ESPERADO**: O saldo da conta é exibido corretamente na tela inicial.

-------------------------------------------------------------------------

**5ºCASO**

**ID**: SMK05

**TÍTULO**: Validação de acesso à área de pagamentos

**PRÉ-CONDIÇÃO** Usuário autenticado no sistema

**PASSOS**: Usuário estar na tela de login, informar e-mail e senha válidos, clicar no botão entrar, acessar ao menu principal, selecionar a opção pagamentos

**RESULTADO ESPERADO**: A tela de pagamento é carregada com sucesso e está disponível para  utilização

-------------------------------------------------------------------------------------------------------

### Sanity test

**1ºCASO**

**ID**: SNT01

**TÍTULO**: Validação da realização de  pagamento com sucesso

**PRÉ-CONDIÇÃO**: Usuário autenticado no sistema e  possui saldo suficiente para efetuar o pagamento

**PASSOS**: acessar a area de pagamentos, efetuar o pagamento,confirmar a operação

**RESULTADO ESPERADO**: O pagamento é realizado com sucesso e a confirmação da transação é exibida ao usuário

------------------------------------------------------------------------------------------------------------

**2ºCASO**

**ID**: SNT02

**TÍTULO** Validação do login após correção

**PRÉ-CONDIÇÃO**: Usuário cadastrado no sistema com credenciais válidas

**PASSOS**: Acessar a tela de login, informar e-mail e senha válidos, clicar no botão entrar. 

**RESULTADO ESPERADO**: Usuário consegue realizar login e acessar a conta

--------------------------------------------------------------------

**3ºCASO**

**ID**: SNT03

**TÍTULO**: Validação da atualização do saldo após transferência

**PRÉ-CONDIÇÃO**: Usuário autenticado no sistema, possui saldo disponível e realizou uma transferência com sucesso

**PASSOS**: acessar a tela inicial da conta, consultar saldo disponível após a transferência

**RESULTADO ESPERADO**: O saldo da conta é atualizado corretamente após a realização da transferência.

-----------------------------------------------------------------------------------------------

**4ºCASO**

**ID**:SNT04

**TÍTULO**: Validação do recebimento de uma transferência com mensagem de confirmação

**PRÉ-CONDIÇÃO**: Usuário autenticado no sistema e possui uma conta ativa para recebimento

**PASSOS**: Realizar uma transferência para a conta do usuário, acessar a conta após o recebimento, verificar a mensagem após a operação

**RESULTADO ESPERADO**: O valor recebido é registrado corretamente na conta e uma mensagem de confirmação é exibida para o usuário.

---------------------------------------------------------------------------------------------------------------------------

**5ºCASO**

**ID**: SNT05

**TÍTULO**: Validação da exibição do saldo após login

**PRÉ-CONDIÇÃO**: Usuário cadastrado no sistema com saldo disponível.

**PASSOS**: Realizar login no sistema, aguardar o carregamento da tela inicial, verificar o saldo exibido 

**RESULTADO ESPERADO**: O saldo da conta é exibido após o  login

-----------------------------------------------------------------------

**regression test**

**1ºCASO**

**ID**: REG01

**TÍTULO**: Validação da realização de pagamento após atualização do sistema

**PRÉ-CONDIÇÃO**: Usuário autenticado no sistema e possui saldo suficiente

**PASSOS**: Realiza login, acessar à área de pagamento, efetuar o pagamento e confirmar a operação

**RESULTADO ESPERADO**: O pagamento é realizado com sucesso e a confirmação é exibida ao usuário

---------------------------------------------------------------------------------------------

**2CASO**

**ID**: REG02

**TÍTULO**: Validação de realização de transferência entre contas

**PRÉ-CONDIÇÃO**: Usuário autenticado e com saldo disponível

**PASSOS**: Realizar login, acessar a opção de transferência, informar uma conta válida, inserir um valor e confirmar a operação

**RESULTADO ESPERADO**: A transferência é concluida com sucesso e o comprovante é exibido ao usuário

-----------------------------------------------------

**3CASO**

**ID**: REG03

**TÍTULO**: Validação da atualização do saldo após pagamento

**PRÉ-CONDIÇÃO**: Usuário autenticado e com saldo suficiente

**PASSOS**: Realizar pagamento e retornar à tela inicial

**RESULTADO ESPERADO**: O saldo é atualizado corretamente após a realização do pagamento

----------------------------------------

**4CASO**

**ID**: REG04

**TÍTULO**: Validação da  navegação entre as funcionalidade do sistema

**PRÉ-CONDIÇÃO**: Usuário autenticado no sistema

**PASSOS**: Realizar login, acessar as telas de saldo, pagamentos, tranferências, e voltar para tela inicial

**RESULTADO ESPERADO**: Todas as telas são carregadas corretamente, e permanecem funcionando

-----------------------------------------

**5CASO**

**ID**: REG05

**TÍTULO**: Validação de logout e novo login após utilização do sistema

**PRÉ-CONDIÇÃO**: Usuário autenticado no sistema

**PASSOS**: Realizar operações no sistema, efetuar logout e realizar um novo login com credenciais válidas.

**RESULTADO ESPERADO**: O logout é realizado com sucesso e o usuário consegue acessar novamente sua conta sem apresentar erros.

-----------------------------------------------------------




