# Atividade Avaliativa — Técnicas de Teste de Software

## 1. Casos de Teste — Valor Limite

### CT-01 — Cadastro de quantidade mínima de estoque

**Técnica utilizada:** Valor Limite

**Objetivo:** Verificar se o sistema aceita corretamente a quantidade mínima de estoque permitida para um produto.

**Entradas:**
- Valor mínimo permitido: 1 unidade
- Valor informado: 1 unidade

**Resultado esperado:**

O sistema deve aceitar o valor 1 e permitir o cadastro do produto com a quantidade mínima de estoque informada.

---

### CT-02 — Cadastro de quantidade máxima de estoque

**Técnica utilizada:** Valor Limite

**Objetivo:** Verificar se o sistema aceita a quantidade máxima de estoque permitida.

**Entradas:**
- Valor máximo permitido: 1000 unidades
- Valor informado: 1000 unidades

**Resultado esperado:**

O sistema deve aceitar o valor 1000 e permitir o cadastro do produto normalmente.

---

### CT-03 — Cadastro de quantidade abaixo do limite mínimo

**Técnica utilizada:** Valor Limite

**Objetivo:** Verificar o comportamento do sistema quando é informada uma quantidade abaixo do limite mínimo permitido.

**Entradas:**
- Valor mínimo permitido: 1 unidade
- Valor informado: 0 unidades

**Resultado esperado:**

O sistema deve rejeitar o valor informado e apresentar uma mensagem indicando que a quantidade deve ser maior que zero.

---

## 2. Casos de Teste — Particionamento de Equivalência

### CT-04 — Cadastro de produto com quantidade válida

**Técnica utilizada:** Particionamento de Equivalência

**Objetivo:** Verificar se o sistema aceita uma quantidade pertencente à classe de valores válidos.

**Entradas:**
- Quantidade informada: 25 unidades
- Classe válida: valores maiores que 0

**Resultado esperado:**

O sistema deve aceitar a quantidade de 25 unidades e permitir o cadastro do produto.

---

### CT-05 — Cadastro de produto com quantidade negativa

**Técnica utilizada:** Particionamento de Equivalência

**Objetivo:** Verificar se o sistema rejeita valores negativos para a quantidade de estoque.

**Entradas:**
- Quantidade informada: -5 unidades
- Classe inválida: valores menores que 0

**Resultado esperado:**

O sistema deve rejeitar o valor informado e apresentar uma mensagem de erro informando que a quantidade não pode ser negativa.

---

### CT-06 — Cadastro de produto sem informar a quantidade

**Técnica utilizada:** Particionamento de Equivalência

**Objetivo:** Verificar o comportamento do sistema quando o campo de quantidade não é preenchido.

**Entradas:**
- Quantidade informada: campo vazio
- Classe inválida: campo não preenchido

**Resultado esperado:**

O sistema deve impedir o cadastro e informar que o campo de quantidade é obrigatório.

---

# 3. Estados e Transições

## Estado 01 — Produto não cadastrado

**Estado:** O produto ainda não foi cadastrado no sistema.

**Transição:** O usuário preenche os dados do produto e seleciona a opção de cadastrar.

**Próximo estado:** Produto cadastrado.

---

## Estado 02 — Produto cadastrado

**Estado:** O produto foi cadastrado corretamente e está disponível no sistema.

**Transição:** O usuário realiza uma consulta pelo nome do produto.

**Próximo estado:** Produto localizado/consultado.

---

## Estado 03 — Produto localizado/consultado

**Estado:** O sistema encontrou o produto pesquisado e apresenta suas informações.

**Transição:** O usuário encerra a consulta ou realiza uma nova pesquisa.

**Próximo estado:** Sistema disponível para uma nova consulta.

---

# 4. Resumo dos Testes

| ID | Técnica Utilizada | Entrada | Resultado Esperado |
|---|---|---|---|
| CT-01 | Valor Limite | 1 unidade | Sistema aceita o valor |
| CT-02 | Valor Limite | 1000 unidades | Sistema aceita o valor |
| CT-03 | Valor Limite | 0 unidades | Sistema rejeita o valor |
| CT-04 | Particionamento de Equivalência | 25 unidades | Sistema aceita o valor |
| CT-05 | Particionamento de Equivalência | -5 unidades | Sistema rejeita o valor |
| CT-06 | Particionamento de Equivalência | Campo vazio | Sistema informa que o campo é obrigatório |

## Observação

Os casos de teste foram estruturados considerando uma aplicação de gerenciamento de produtos/materiais de uma clínica, utilizando como exemplo o cadastro e controle da quantidade em estoque.
