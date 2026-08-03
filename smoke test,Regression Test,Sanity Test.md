### ATIVIDADE 5 CASOS DE SMOKE TEST, SANITY TEST, REGRESSION TEST

***Cenário: Uma nova versão de um sistema bancário foi implantada com correção no login e um ajuste na exibição do saldo tela inicial.**

### Smoker test:

**1ºCASO**

**ID**: SMK01

**TÍTULO**:Validação e login com credenciais válidas

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

**TÍTULO**: Validação do acesso ao menu principal da conta após login

**PRÉ-CONDIÇÃO**

**PASSOS**:

**RESULTADO ESPERADO**:
