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


