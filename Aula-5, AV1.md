### ESTRATÉGIA DE TESTE- Cenário fictício ###

**CENÁRIO**

A empresa FastDelivery está desenvolvendo um sistema de delivery para restaurantes. A plataforma permite que clientes realizem pedidos, acompanhem a entrega em tempo real, efetuem pagamentos online e avaliem os estabelecimentos. O sistema será utilizado por clientes, entregadores e administradores. O projeto está em desenvolvimento ativo, possui prazo de entrega de seis meses e conta com uma equipe reduzida composta por cinco desenvolvedores, um analista de requisitos e um profissional responsável pelos testes. Após o lançamento, novas funcionalidades e correções serão implementadas continuamente.

**ESTRATÉGIA DE TESTE**

**1. Objetivo da estratégia**
-----------------------------
O principal objetivo é garantir que as funcionalidades do  essenciais do sistema funcionem corretamente antes da entrega aos usuários, reduzindo falhas critícas e aumentando a confiabilidade da plataforma

Os aspectos que merecem maior atenção são:

**Cadastro e login de usuários.**

**Realização de pedidos.**

**Processamento de pagamentos.**

**Acompanhamento das entregas.**

**Segurança dos dados dos usuários.**

**2.TIPOS DE TESTES PRIORITÁRIOS**
----------------------------------
**Testes funcionais, para validar todas as funcionalidades principais.**

**Testes de integração, garantindo a comunicação entre módulos como pagamento, pedidos e entrega.**

**Testes de regressão, verificando se novas alterações não afetam funcionalidades já existentes.**

**Testes de usabilidade, assegurando que o sistema seja fácil de utilizar pelos clientes.**

**Menor prioridade**
----------------------------------------------
**Testes de carga e desempenho avançados, que serão realizados apenas próximos ao lançamento.**

**Testes de compatibilidade com navegadores menos utilizados.**

**Justificativa: Como o sistema será utilizado por usuários reais e possui prazo limitado, é mais importante garantir que as funções principais estejam corretas e estáveis. Testes mais complexos podem ser executados em etapas posteriores.**

**ABORDAGENS DE TESTE**
---------------
**TESTES MANUAIS:**

**Validação de interface**

**Testes exploratório**

**Testes de usuabilidade**

**Verificação dos fluxos completos da compra**
----------------------------------
**TESTES AUTOMIZADOS:**

**Teste Unitário**

**Teste de Integração**

**Teste de Regressão executados sempre que houve alteração no sistema**

**Justificativa: Os testes manuais ajudam a identificar problemas relacionados à experiência do usuário, enquanto a automação reduz o tempo gasto com verificações repetitivas e aumenta a confiabilidade das novas versões.**

RISCOS E MITIGAÇÃO
--------------------
Principais Risco:

**Falhas no processamento de pagamentos**

**Erros na realização de pedidos**

**Problemas de informações envolvendo dados dos usuários**

**Correções que gerem novos erros no sistema**
---------------------------------
**Como a estratégia resolve esses riscos**

**Execução frequente de testes funcionais e de integração.**

**Automação dos testes de regressão para detectar falhas rapidamente.**

**Testes contínuos durante todo o desenvolvimento.**

**Priorização das funcionalidades críticas antes da entrega.**

**Recursos e Cronograma**
------------------
Equipe envolvida:
**1 Analista de Testes.**

**5 Desenvolvedores responsáveis pelos testes unitários.**

**Participação do Product Owner na validação final das funcionalidades.**

**Cronograma:**
**Testes unitários durante o desenvolvimento de cada funcionalidade.**

**Testes de integração ao final de cada sprint.**

**Testes de regressão antes de cada nova versão.**

**Testes de aceitação próximos ao lançamento.**
---------------------------------------
Frequência dos testes:

**Os testes serão contínuos, ocorrendo durante todo o ciclo de desenvolvimento. Dessa forma, os problemas serão identificados mais cedo, reduzindo custos de correção e aumentando a qualidade do sistema antes da entrega aos usuários.**
