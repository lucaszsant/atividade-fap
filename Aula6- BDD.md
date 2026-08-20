## 2 Teste Para uma Funcionalidade do Projeto Clínica PSI ##

**1º teste**:
**Tipo: Caminho Feliz**
**Titulo: login  com credenciais válidas**

**id:001**
**pré-condição: O usuário deve estar na tela de login do sistema**

**passos: O testador deve inserir "admin" no campo de usuário, o testador deve inserir "admin@123" no campo de senha, e clicar no botão "entrar"**

Resultado Esperado: O sistema deve validar as credenciais e permitir o acesso a clínica psi.
Resultado Obtido: O sistema validou as credenciais e permitiu o acesso a clínica psi.
-----------------

**2ºteste:**
**Tipo: Caminho alternativo**

**Título: Falha ao pesquisar por produto ou material**

**id:002**

**pré-condição: O usuário deve estar na tela de pesquisa de produtos e materiais**

**passos: O usuário deve acessar a tela de pesquisa de produtos e materiais, o usuário deve digitar "esparadrapo" no campo de pesquisa, o usuário deve realizar a pesquisa**

**Resultado Esperado: O produto "esparadrapo" deve aparecer nos resultados de pesquisa para que o usuário possa visualizá-lo
**Resultado Obtido: O usuário pesquisa por "esparadrapo", mas o produto não é exibido nos resultados

