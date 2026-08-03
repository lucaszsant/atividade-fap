 # Atividade - Teste de Sistema e Aceitação

## Etapa 1 - Compreensão do Cenário

### Funcionalidades envolvidas

- Tela de login
- Validação das credenciais 
- Acesso à conta
- Visualização do saldo

### Fluxo principal
 Fluxo sequencial (caminho feliz)
O usuário acessa a tela de logi,informa e-mail e senha válidos,realiza o login,acessa a conta, e visualiza o saldo

### variação de fluxo
O usuário realiza o login com sucesso e acessa sua conta e, em vez de visualizar o saldo imediatamente, navega pela conta antes de consultar o saldo

### Etapa 2- Escrever testes de sistemas

### 2 testes de fluxo principal(caminho feliz)

**id**: Test01

**título**: Login com credenciais válidas

**pré-condição**: Estar na tela de login


**passos**: Usuário estar na tela de login, informa um e-mail e senha válidos, e acessa a pagina principal do banco

**resultado**: o usuário consegue acessar o sistema.

**Id**:test02

**título**: pagamento de conta com sucesso

**pré-condição**: Estar na tela de  pagamento

**passos**: O usuário está na tela de login, informa e-mail e senha válidos, acessa a área de pagamentos e realiza o pagamento

**resultado**: O usuário consegue efetuar o pagamento.

### 2 teste de fluxo alternativo

**id**: Test03

**título**: Validar login com senha inválida

**pré-condição**: Usuário coloca senha inválida

**passos**: Usuário estar na tela de login, informar o e-mail válido mas a senha inválida, clica no botão entrar

**resultado**: o sistema exibe uma mensagem dizendo " Senha inválido"



**id**: Test04

**título**: Validar login com campo obrigatório não preenchido

**pré-condição**: Usuário está  de login e possui uma conta cadastrada no sistemas.

**passos**: O usuário estar na tela de login, e não informar o email e senha, clica no botão entrar

**resultado**: o sistema exibe uma mensagem dizendo "preencha os campos obrigatórios"


### Etapa 3- escrever testes de aceitação ### 

**2 testes de fluxos principal(caminho feliz)**

**id**: Lgn01

**título**: Cliente acessa a sua conta bancária com sucesso 

**pré-condição**: Cliente possui uma conta cadastrada e suas credenciais são válidas

**passos**: O usuário estar na tela de login, informar seu e-mail e senha validas, clica no botão entrar

**resultado**: Cliente consegue acessar sua conta e utilizar os serviços disponiveis.




**id**: Lgn02

**título**: cliente realiza o pagamento com sucesso

**pré-condição**: cliente possui uma conta cadastrada no banco e uma conta válida para pagamento 

**passos**: cliente estar na tela de login, informa seu email e senha, clica no botão entrar, seleciona a opção pagamento, cliente confirma a operação 

**resultado**: cliente consegue realizar o pagamento e recebe a confirmação da transação



### 2 testes de fluxo alternativo.

**id**: Lgn03

**título**: Cliente não consegue acessar a conta com senha inválida

**pré-condição**: Cliente possui uma conta cadastrada no banco.

**passos**: Cliente acessa a tela de login, Cliente informa um e-mail válido e uma senha incorreta. Cliente tenta acessar a conta.

**resultado**: o sistema exibe uma mensagem dizendo "senha incorreta"



**id**: Lgn04

**título**: Cliente não consegue realizar pagamento sem informações obrigatórias

**pré-condição**: Cliente possui uma conta cadastrada no banco e está na área de pagamentos.

**passos**:Cliente seleciona a opção de pagamento.Cliente deixa um campo obrigatório sem preencher.Cliente tenta confirmar o pagamento.

**Resultado**: Sistema informa que existem campos obrigatórios não preenchidos e impede a conclusão do pagamento até que as informações sejam corrigidas.






### etapa 4- justificativa e classificação

### teste de sistema

**id:test01- login com credenciais invalidas** 

**Por que este é um teste de sistema?**

**Porque verifica se a funcionalidade de login funciona corretamente quando o usuário informa credenciais válidas e se o sistema permite o acesso à conta.**

**Ponto de vista adotado:**

**Visão do sistema, verificando o comportamento da aplicação durante o processo de autenticação.**

**Tipo de validação realizada:**

**Validação funcional do processo de login e acesso ao sistema.**




**id:Test02 - Pagamento de conta com sucesso**

**Classificação: Teste de Sistema**

**Por que este é um teste de sistema?**

**Porque valida se o sistema permite que o usuário realize uma operação de pagamento corretamente após acessar sua conta.**

**Ponto de vista adotado:**

**Visão do sistema, analisando se a funcionalidade de pagamento executa a operação esperada.**

**Tipo de validação realizada:**

**Validação funcional do fluxo de pagamento.**


**id:Test03 - Validar login com senha inválida**

**Classificação: Teste de Sistema**

**Por que este é um teste de sistema?**

**Porque verifica se o sistema identifica uma senha incorreta e apresenta uma resposta adequada ao usuário.**

**Ponto de vista adotado:**

**Visão do sistema, avaliando o tratamento de dados inválidos durante a autenticação.**

**Tipo de validação realizada:**

**Validação funcional das regras de autenticação e tratamento de erros.**





**id Test04 - Validar login com campo obrigatório não preenchido**

**Classificação: Teste de Sistema**

**Por que este é um teste de sistema?**

**Porque verifica se o sistema realiza a validação dos campos obrigatórios antes de permitir o acesso.**

**Ponto de vista adotado:**

**Visão do sistema, avaliando as regras de validação dos dados inseridos.**

**Tipo de validação realizada:**

**Validação funcional dos campos obrigatórios e mensagens de erro.**





**Testes de Aceitação**

**id Lgn01 - Cliente acessa sua conta bancária com sucesso**

**Classificação: Teste de Aceitação**

**Por que este é um teste de aceitação?**

**Porque valida se o cliente consegue acessar sua conta e utilizar os serviços bancários esperados, atendendo uma necessidade real do usuário.**

**Ponto de vista adotado:**

**Visão do cliente e do negócio, considerando a experiência e o objetivo do usuário.**

**Tipo de validação realizada:**

**Validação do valor entregue ao usuário através do acesso à conta.**


**id Lgn02 - Cliente realiza o pagamento com sucesso**

**Classificação: Teste de Aceitação**

**Por que este é um teste de aceitação?**

**Porque verifica se o cliente consegue realizar uma operação importante do serviço bancário e concluir seu objetivo.**

**Ponto de vista adotado:**

**Visão do cliente e do negócio, avaliando se o serviço atende à necessidade do usuário.**

**Tipo de validação realizada:**

**Validação da entrega de valor através da realização do pagamento.**



**id Lgn03 - Cliente não consegue acessar a conta com senha inválida**

**Classificação: Teste de Aceitação**

**Por que este é um teste de aceitação?**

**Porque verifica se o sistema oferece uma resposta adequada ao cliente quando ele não consegue realizar o acesso por erro nas credenciais.**

**Ponto de vista adotado:**

**Visão do cliente, considerando a orientação e segurança durante a tentativa de acesso.**

**Tipo de validação realizada:**

**Validação da experiência do usuário no tratamento de uma situação de erro.**




**id:lgn04 - Cliente não consegue realizar pagamento sem informações obrigatórias**

**Classificação: Teste de Aceitação**

**Por que este é um teste de aceitação?**

**Porque valida se o cliente é impedido de realizar uma operação incompleta e recebe orientação para corrigir os dados necessários.**

**Ponto de vista adotado:**

**Visão do cliente e do negócio, garantindo que a operação seja realizada com segurança.**

**Tipo de validação realizada:**

**Validação da regra de negócio e da experiência do usuário durante uma situação alternativa.**
