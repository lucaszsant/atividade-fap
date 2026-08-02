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


