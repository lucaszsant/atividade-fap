# Atividade Avaliativa — Avaliação Heurística

## Projeto

Clínica Psi

## Funcionalidade analisada

Consulta de Produtos/Materiais

A funcionalidade permite pesquisar produtos e materiais cadastrados no sistema e visualizar os resultados encontrados.

---

## Heurística 1 — Visibilidade do Status do Sistema

### Objetivo

Verificar se o sistema fornece informações claras ao usuário durante a realização da pesquisa e após a apresentação dos resultados.

### Testes realizados

* Pesquisa de um produto existente.
* Pesquisa de um produto inexistente.
* Observação do comportamento do sistema durante o processamento da pesquisa.
* Verificação da apresentação dos resultados.

### Falhas identificadas

* O sistema não apresenta um indicador visual de carregamento durante a realização da pesquisa.
* Não há uma indicação clara de que a pesquisa está sendo processada.
* Em situações de demora na resposta, o usuário pode não saber se a pesquisa foi realizada ou se o sistema apresentou algum problema.
* A ausência de feedback durante a pesquisa pode levar o usuário a clicar novamente no botão de pesquisa.

### Riscos identificados

A falta de feedback pode gerar dúvidas sobre o funcionamento do sistema e fazer com que o usuário repita a mesma ação desnecessariamente.

### Áreas que merecem mais atenção

* Feedback visual durante a pesquisa.
* Tempo de resposta da consulta.
* Indicação de processamento.
* Clareza na apresentação dos resultados.

---

## Heurística 2 — Prevenção de Erros

### Objetivo

Verificar se o sistema consegue evitar ou informar adequadamente situações de entrada inválida durante a consulta de produtos e materiais.

### Testes realizados

* Pesquisa com o campo vazio.
* Pesquisa de um produto inexistente.
* Inserção de caracteres especiais no campo de pesquisa.
* Verificação das mensagens apresentadas pelo sistema.

### Falhas identificadas

* O sistema não apresenta uma orientação clara quando o campo de pesquisa é deixado vazio.
* Ao pesquisar um produto inexistente, a ausência de uma mensagem específica pode dificultar a compreensão do usuário sobre o resultado da pesquisa.
* O campo de pesquisa não apresenta orientações sobre quais tipos de informações podem ser inseridas.
* Entradas inesperadas podem não receber um tratamento ou retorno claro para o usuário.

### Riscos identificados

A falta de validação e de mensagens claras pode fazer com que o usuário não compreenda o motivo de não obter resultados ou não saiba como corrigir a pesquisa.

### Áreas que merecem mais atenção

* Validação do campo de pesquisa.
* Tratamento de campos vazios.
* Tratamento de produtos inexistentes.
* Validação das informações inseridas.
* Mensagens de erro e orientação ao usuário.

---

## Justificativa das Escolhas

As heurísticas de Visibilidade do Status do Sistema e Prevenção de Erros foram escolhidas porque estão diretamente relacionadas à funcionalidade de Consulta de Produtos/Materiais.

A primeira permite avaliar se o usuário recebe informações suficientes sobre o processamento da pesquisa e sobre o resultado da ação realizada.

A segunda permite verificar o comportamento do sistema diante de situações diferentes do caminho normal, como campos vazios, produtos inexistentes e entradas inesperadas.

A aplicação dessas heurísticas permite identificar riscos relacionados à comunicação do sistema com o usuário, à validação das entradas e ao tratamento de situações que podem ocorrer durante a utilização da funcionalidade.
