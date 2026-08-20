### BDD VS TRADICIONAL

BDD:
>/< gherkin

feature: login no sistema. permitir que administrador acesse o sistema utilizando credenciais válidas.

Scenario: login com credenciais válidas

Given: O administrador estar na tela de login
When: O administrador informa "admin" no campo de usuário
And: Informa "admin@123" no campo de senha
And: Clica no botão "entrar"
Then: O sistema deve validar as credenciais
And: Permitir o acesso à clinica psi

-------------------------

Tradicional:

Id:001

Título: Login com credenciais válidas

Tipo: Caminho feliz

Pré-condição: O administrador deve estar na tela de login do sistema

Passos: Inserir "admin" no campo de usuário, Inserir "admin@123" no campo de senha, clicar no botão "Entrar"

Resultado Esperado: O sistema deve válidar as credenciais e permitir o acesso à clínica psi

--------------------------------------------

Qual o formato mais fácil de escrever? **Tradiconal, porque é mais direto e eu já estou acostumado com a estrutura**

Qual comunica melhor o comportamento? **BDD, porque descreve de forma mais natural o comportamento esperado do sistema, e facilitando a compreensão por pessoas técnicas e não técnicas**

Qual seria mais fácil de manter? **O BDD, principalmente quando existem muitos cenários, porque a estrutura padronizada ( Given, And, Then) facilita a organização e atualização dos testes.**
