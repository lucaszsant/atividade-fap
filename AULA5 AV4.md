# Atividade Avaliativa — Clínica Psi

## 1. Cadastro de Casos de Teste

### TESTE 01 — Adicionar Produto/Material ao Carrinho

**ID:** TESTE-01

**Título:** Adicionar Produto/Material ao Carrinho

**Pré-condições:**

* Usuário deve estar autenticado no sistema.
* Deve existir um produto/material previamente cadastrado.

**Passos:**

1. Acessar a área de Produtos/Materiais.
2. Selecionar um produto/material.
3. Adicionar o produto/material ao carrinho.
4. Acessar o carrinho.
5. Verificar se o produto/material foi adicionado.

**Resultado esperado:**
O produto/material selecionado deve ser adicionado corretamente ao carrinho.

---

### TESTE 02 — Consulta de Produtos/Materiais

**ID:** TESTE-02

**Título:** Consulta de Produtos/Materiais

**Pré-condições:**

* Usuário deve estar autenticado no sistema.
* O produto/material "Esparadrapo" deve estar previamente cadastrado.

**Passos:**

1. Acessar a área de consulta de Produtos/Materiais.
2. Informar "Esparadrapo" no campo de pesquisa.
3. Realizar a pesquisa.
4. Verificar os resultados apresentados.

**Resultado esperado:**
O produto/material "Esparadrapo" deve ser exibido corretamente nos resultados da consulta.

---

## 2. Ciclos de Teste

### Smoke

Os testes de Smoke têm como objetivo verificar se as principais funcionalidades do sistema estão funcionando.

* TESTE-01 — Adicionar Produto/Material ao Carrinho
* TESTE-02 — Consulta de Produtos/Materiais

### Sanity

Os testes de Sanity têm como objetivo verificar funcionalidades específicas após alterações ou correções no sistema.

* TESTE-02 — Consulta de Produtos/Materiais

### Regression

Os testes de Regression têm como objetivo verificar se alterações realizadas no sistema não afetaram funcionalidades que já estavam funcionando.

* TESTE-01 — Adicionar Produto/Material ao Carrinho
* TESTE-02 — Consulta de Produtos/Materiais

---

## 3. Execução Simulada

### TESTE 02 — Consulta de Produtos/Materiais

**Ciclo:** Smoke

**Resultado obtido:**
Após realizar a pesquisa pelo produto "Esparadrapo", o produto foi exibido corretamente nos resultados da consulta.

**Status:** Aprovado

