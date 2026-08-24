# Clínica Psi — Análise de Testes Funcionais e Não Funcionais

## 1. Introdução

A Clínica Psi é um sistema de gerenciamento de uma clínica de psicologia. O sistema possui funcionalidades relacionadas ao cadastro de pacientes e psicólogos, gerenciamento de agenda, agendamento e reagendamento de consultas, controle de presença, registro de prontuários e evoluções, controle financeiro, gerenciamento de produtos e estoque e controle de acesso por meio de perfis e permissões.

O objetivo desta atividade é identificar, projetar e justificar diferentes tipos de testes de software aplicáveis ao sistema Clínica Psi.

Foram considerados testes funcionais e não funcionais, abrangendo:

* testes unitários;
* testes de integração;
* testes de sistema;
* testes de aceitação;
* testes de performance;
* testes de segurança;
* testes de usabilidade;
* testes de compatibilidade.

Para os testes funcionais, foram analisadas as principais regras e funcionalidades do sistema. Para os testes não funcionais, foram definidos critérios que permitem verificar características como velocidade, segurança, facilidade de uso e funcionamento em diferentes ambientes.

Os testes foram planejados considerando que o sistema completo possui interface web, regras de negócio, API e banco de dados.

### Observação sobre a execução

O endereço da aplicação informado no enunciado foi consultado durante a elaboração deste relatório. No momento da verificação, o endereço estava retornando erro 404 (página não encontrada). Dessa forma, não foram inventados resultados de execução, evidências ou defeitos que não puderam ser observados.

Os testes abaixo representam os cenários e critérios que devem ser utilizados quando a aplicação estiver disponível para execução.

Também foi considerado que todos os dados utilizados nos testes devem ser fictícios, principalmente dados relacionados a pacientes, prontuários, CPF, informações financeiras e demais dados sensíveis.

---

# Parte 1 — Testes Funcionais

## Exercício 1 — Identificação das funcionalidades

Foram selecionadas cinco funcionalidades importantes da Clínica Psi:

1. Cadastro de paciente;
2. Cadastro de psicólogo;
3. Agendamento de consulta;
4. Reagendamento de consulta;
5. Registro de prontuário e evolução.

### 1.1 Cadastro de paciente

**Objetivo:** permitir que a clínica cadastre um novo paciente no sistema para que ele possa posteriormente ser localizado, receber consultas e possuir seus registros vinculados ao cadastro.

**Usuário:** recepcionista ou outro usuário autorizado.

**Dados necessários:**

* nome completo;
* CPF;
* telefone;
* e-mail;
* data de nascimento;
* demais informações obrigatórias solicitadas pelo sistema.

**Resultado esperado:**

O sistema deve validar os dados informados e cadastrar o paciente com sucesso. Após o cadastro, o paciente deve poder ser localizado pela funcionalidade de pesquisa.

**Possíveis condições de erro:**

* nome obrigatório não preenchido;
* CPF inválido;
* CPF já cadastrado;
* e-mail em formato inválido;
* telefone em formato inválido;
* campos obrigatórios não preenchidos;
* tentativa de cadastro por usuário sem permissão.

---

### 1.2 Cadastro de psicólogo

**Objetivo:** permitir o cadastro dos profissionais que realizarão os atendimentos.

**Usuário:** administrador ou usuário autorizado.

**Dados necessários:**

* nome completo;
* CPF;
* e-mail;
* telefone;
* número do CRP;
* demais informações obrigatórias.

**Resultado esperado:**

O sistema deve validar os dados e registrar o psicólogo. O profissional cadastrado deve poder ser utilizado posteriormente no agendamento de consultas.

**Possíveis condições de erro:**

* CRP inválido;
* CRP já cadastrado;
* CPF inválido;
* CPF já existente;
* e-mail inválido;
* campos obrigatórios não preenchidos;
* usuário sem permissão para cadastrar profissionais.

---

### 1.3 Agendamento de consulta

**Objetivo:** permitir que uma consulta seja marcada para um paciente com um determinado psicólogo, data e horário.

**Usuário:** recepcionista ou usuário autorizado.

**Dados necessários:**

* paciente;
* psicólogo;
* data;
* horário;
* informações adicionais necessárias para o agendamento.

**Resultado esperado:**

O sistema deve verificar se o horário está disponível e registrar a consulta. O compromisso deve aparecer na agenda do psicólogo e estar associado ao paciente correto.

**Possíveis condições de erro:**

* paciente inexistente;
* psicólogo inexistente;
* data inválida;
* horário já ocupado;
* campos obrigatórios não preenchidos;
* tentativa de agendamento por usuário sem permissão.

---

### 1.4 Reagendamento de consulta

**Objetivo:** permitir a alteração da data ou do horário de uma consulta existente.

**Usuário:** recepcionista ou usuário autorizado.

**Dados necessários:**

* consulta existente;
* nova data;
* novo horário.

**Resultado esperado:**

A consulta deve deixar de ocupar o horário antigo e passar a ocupar o novo horário. A agenda deve apresentar a consulta somente no novo horário.

**Possíveis condições de erro:**

* consulta inexistente;
* novo horário ocupado;
* nova data inválida;
* tentativa de alteração por usuário sem permissão;
* falha na atualização da agenda.

---

### 1.5 Registro de prontuário e evolução

**Objetivo:** permitir que o psicólogo registre informações relacionadas ao atendimento realizado.

**Usuário:** psicólogo autorizado.

**Dados necessários:**

* paciente;
* consulta;
* data do atendimento;
* evolução;
* informações clínicas permitidas pelo sistema.

**Resultado esperado:**

O registro deve ser salvo e permanecer associado ao paciente e ao atendimento correspondente. Usuários não autorizados não devem conseguir visualizar ou alterar informações do prontuário.

**Possíveis condições de erro:**

* paciente inexistente;
* consulta inexistente;
* campo obrigatório não preenchido;
* usuário sem permissão;
* falha ao salvar;
* tentativa de acesso por perfil não autorizado.

---

# Exercício 2 — Testes Unitários

Testes unitários verificam pequenas unidades de código de forma isolada. O objetivo é verificar uma função ou regra específica sem depender da interface do sistema, do banco de dados ou de serviços externos.

Foram selecionados cinco testes unitários.

---

## Teste unitário 1 — Cálculo do saldo financeiro

**Função/regra:** calcular saldo financeiro.

**Entrada:**

* Receitas: R$ 2.000,00
* Despesas: R$ 800,00

**Resultado esperado:**

R$ 1.200,00.

**Regra:**

Saldo = Receitas - Despesas.

**Por que é unitário?**

Porque verifica isoladamente uma regra matemática de cálculo. Não é necessário abrir a interface, acessar o banco de dados ou consultar outro serviço.

**Casos adicionais recomendados:**

* receitas de R$ 1.000,00 e despesas de R$ 1.000,00 → saldo R$ 0,00;
* receitas de R$ 500,00 e despesas de R$ 800,00 → saldo -R$ 300,00;
* receitas de R$ 0,00 e despesas de R$ 0,00 → saldo R$ 0,00.

---

## Teste unitário 2 — Validação de CPF

**Função/regra:** validar CPF.

**Entrada válida fictícia:**

Um CPF fictício que possua formato e dígitos verificadores matematicamente válidos.

**Resultado esperado:**

A função deve retornar que o CPF é válido.

**Entrada inválida:**

CPF com quantidade incorreta de caracteres ou com dígitos verificadores inválidos.

**Resultado esperado:**

A função deve retornar que o CPF é inválido.

**Por que é unitário?**

Porque somente a função responsável pela validação do CPF é testada. O teste não precisa cadastrar o paciente, acessar a interface ou gravar informações no banco de dados.

---

## Teste unitário 3 — Validação de e-mail

**Função/regra:** validar formato de e-mail.

**Entrada válida:**

`paciente.teste@example.com`

**Resultado esperado:**

E-mail considerado válido.

**Entrada inválida:**

`paciente.teste`

**Resultado esperado:**

E-mail considerado inválido.

**Por que é unitário?**

Porque o teste verifica somente a função de validação do formato do e-mail, sem depender de cadastro, banco de dados ou interface.

---

## Teste unitário 4 — Cálculo do valor total de uma compra

**Função/regra:** calcular o valor total de uma compra.

**Entrada:**

* Produto A: 2 unidades × R$ 10,00;
* Produto B: 3 unidades × R$ 5,00.

**Cálculo:**

Produto A = R$ 20,00.

Produto B = R$ 15,00.

Total = R$ 35,00.

**Resultado esperado:**

R$ 35,00.

**Por que é unitário?**

Porque a função de cálculo do total pode ser executada isoladamente com os valores fornecidos, sem necessidade de realizar uma compra real ou acessar o estoque.

---

## Teste unitário 5 — Verificação de estoque abaixo do mínimo

**Função/regra:** identificar se a quantidade disponível está abaixo do estoque mínimo.

**Entrada:**

* Quantidade atual: 3 unidades;
* Estoque mínimo: 5 unidades.

**Resultado esperado:**

O sistema deve identificar que o produto está abaixo do estoque mínimo.

**Outro caso:**

* Quantidade atual: 8 unidades;
* Estoque mínimo: 5 unidades.

**Resultado esperado:**

O sistema não deve indicar estoque abaixo do mínimo.

**Por que é unitário?**

Porque somente a regra responsável por comparar a quantidade atual com o estoque mínimo é verificada.

---

# Exercício 3 — Testes de Integração

Testes de integração verificam a comunicação entre dois ou mais componentes do sistema. O objetivo é confirmar que os dados enviados por um componente são corretamente recebidos, processados e utilizados pelo outro componente.

---

## Teste de integração 1 — Cadastro de paciente + banco de dados

**Componentes integrados:**

Cadastro de pacientes + banco de dados.

**Ação:**

Cadastrar um paciente utilizando dados fictícios.

**Resultado esperado:**

O cadastro deve ser salvo no banco de dados. Ao realizar uma nova pesquisa, o paciente deve ser localizado com os mesmos dados informados no cadastro.

**Risco:**

O sistema informar que o cadastro foi realizado, mas os dados não serem realmente persistidos.

**Justificativa:**

O teste verifica a comunicação entre a camada responsável pelo cadastro e o mecanismo de persistência dos dados.

---

## Teste de integração 2 — Agendamento + agenda do psicólogo

**Componentes integrados:**

Agendamento + agenda.

**Ação:**

Selecionar um paciente, psicólogo, data e horário disponível e confirmar o agendamento.

**Resultado esperado:**

A consulta deve ser registrada e aparecer como ocupada na agenda do psicólogo.

**Risco:**

O agendamento ser salvo, mas o horário continuar aparecendo como disponível, permitindo outro agendamento no mesmo horário.

**Justificativa:**

O teste verifica se os dados do agendamento são corretamente enviados para a agenda.

---

## Teste de integração 3 — Check-in + controle de presença

**Componentes integrados:**

Check-in + controle de presença.

**Ação:**

Realizar o check-in de uma consulta agendada.

**Resultado esperado:**

A presença do paciente deve ser registrada e associada à consulta correta.

**Risco:**

O check-in ser realizado, mas a presença não aparecer no controle de atendimento.

**Justificativa:**

O teste verifica a troca de informações entre o componente responsável pelo check-in e o componente responsável pelo controle de presença.

---

## Teste de integração 4 — Receita/despesa + relatório financeiro

**Componentes integrados:**

Lançamento financeiro + relatório financeiro.

**Ação:**

Cadastrar uma receita fictícia de R$ 2.000,00 e uma despesa fictícia de R$ 800,00.

**Resultado esperado:**

O relatório financeiro deve apresentar os lançamentos e calcular o saldo de R$ 1.200,00.

**Risco:**

O lançamento ser registrado, mas não aparecer no relatório ou ser contabilizado com valor incorreto.

**Justificativa:**

O teste verifica se os dados financeiros registrados são corretamente enviados e utilizados pelo módulo de relatórios.

---

## Teste de integração 5 — Compra + estoque

**Componentes integrados:**

Registro de compra + controle de estoque.

**Ação:**

Cadastrar uma entrada de 10 unidades de determinado produto.

**Resultado esperado:**

A quantidade disponível no estoque deve aumentar em 10 unidades.

**Risco:**

A compra ser registrada, mas a quantidade de estoque permanecer inalterada.

**Justificativa:**

O teste verifica a comunicação entre o registro da movimentação e o controle de estoque.

---

# Exercício 4 — Testes de Sistema

Testes de sistema avaliam o sistema de forma completa, utilizando a interface e executando fluxos semelhantes aos realizados pelos usuários finais.

---

## Cenário 1 — Atendimento completo

### Objetivo

Verificar se é possível executar um fluxo completo desde o cadastro do paciente até o registro financeiro.

### Pré-condições

* Sistema disponível;
* usuário autorizado para realizar os procedimentos;
* dados fictícios disponíveis;
* psicólogo cadastrado;
* horário disponível na agenda.

### Dados utilizados

Paciente fictício:

* Nome: João da Silva Teste
* CPF: utilizar CPF fictício válido
* E-mail: [joao.teste@example.com](mailto:joao.teste@example.com)

Psicólogo:

* Nome: Ana Psicóloga Teste
* CRP: utilizar número fictício apropriado para teste.

### Passos

1. Acessar o sistema.
2. Cadastrar o paciente.
3. Pesquisar o paciente pelo nome ou CPF.
4. Confirmar que o paciente foi localizado.
5. Criar um agendamento para o paciente.
6. Selecionar um horário disponível.
7. Confirmar o agendamento.
8. Realizar o check-in.
9. Registrar a evolução da sessão.
10. Registrar uma receita fictícia.
11. Abrir o relatório financeiro.
12. Verificar o lançamento realizado.

### Resultado esperado

O paciente deve ser cadastrado e localizado corretamente. O agendamento deve aparecer na agenda. O check-in deve ser registrado. A evolução deve ser vinculada ao atendimento. O lançamento financeiro deve aparecer no relatório.

### Resultado obtido

Não foi possível confirmar a execução completa no endereço fornecido no enunciado, pois a aplicação retornou erro 404 durante a verificação.

### Situação

**Não executado — aplicação indisponível no endereço informado.**

### Evidência

Erro HTTP 404 apresentado ao acessar o endereço informado no enunciado.

### Justificativa

Este é um teste de sistema porque avalia um fluxo completo envolvendo várias funcionalidades pela perspectiva do usuário final.

---

# Cenário 2 — Reagendamento

### Objetivo

Verificar se uma consulta pode ser reagendada corretamente e se o horário antigo é liberado.

### Pré-condições

* paciente cadastrado;
* psicólogo cadastrado;
* consulta previamente agendada;
* existência de um novo horário disponível.

### Dados utilizados

Consulta original:

* Data: 10/09/2026;
* Horário: 14:00.

Novo horário:

* Data: 11/09/2026;
* Horário: 15:00.

### Passos

1. Acessar a agenda.
2. Localizar a consulta.
3. Selecionar a opção de reagendamento.
4. Escolher a nova data.
5. Escolher o novo horário.
6. Confirmar o reagendamento.
7. Consultar novamente o horário original.
8. Consultar o novo horário.
9. Verificar os dados apresentados na agenda.

### Resultado esperado

O horário original deve ser liberado. A consulta deve aparecer no novo horário. Os dados do paciente e do psicólogo devem continuar associados à consulta.

### Resultado obtido

Não executado devido à indisponibilidade da aplicação no endereço informado.

### Situação

**Não executado.**

### Evidência

Aplicação retornando erro 404.

### Justificativa

É um teste de sistema porque utiliza a interface e verifica o fluxo completo de alteração de uma consulta.

---

# Cenário 3 — Controle de estoque

### Objetivo

Verificar o funcionamento completo do cadastro e movimentação de produtos.

### Pré-condições

* usuário autorizado;
* sistema disponível.

### Dados utilizados

Produto:

* Nome: Álcool Gel Teste;
* Quantidade inicial: 0;
* Estoque mínimo: 5;
* Entrada: 10 unidades;
* Saída: 6 unidades.

### Passos

1. Acessar o módulo de produtos.
2. Cadastrar o produto.
3. Definir o estoque mínimo como 5 unidades.
4. Registrar entrada de 10 unidades.
5. Conferir o estoque.
6. Registrar saída de 6 unidades.
7. Conferir novamente o estoque.
8. Verificar o alerta de estoque mínimo.

### Resultado esperado

Após a entrada, o estoque deve possuir 10 unidades.

Após a saída de 6 unidades, o estoque deve possuir 4 unidades.

Como 4 é menor que o estoque mínimo de 5, o sistema deve indicar que o produto está abaixo do estoque mínimo.

### Resultado obtido

Não executado devido à indisponibilidade da aplicação no endereço informado.

### Situação

**Não executado.**

### Evidência

Aplicação retornando erro 404.

### Justificativa

O teste avalia o fluxo completo pela interface, envolvendo cadastro, entrada, saída e alerta de estoque.

---

# Cenário 4 — Controle de acesso

### Objetivo

Verificar se diferentes perfis possuem somente as permissões autorizadas.

### Pré-condições

* existência de usuário recepcionista;
* existência de usuário psicólogo;
* existência de perfis configurados;
* aplicação disponível.

### Passos

1. Entrar no sistema utilizando um usuário com perfil de recepcionista.
2. Tentar acessar o módulo de prontuários.
3. Verificar se o acesso é permitido ou negado conforme as regras definidas.
4. Sair do sistema.
5. Entrar utilizando um usuário com perfil de psicólogo.
6. Acessar o módulo de prontuários.
7. Verificar se o acesso autorizado funciona.
8. Verificar se o psicólogo consegue acessar somente as funções permitidas.

### Resultado esperado

Usuários sem permissão para acessar prontuários devem ter o acesso bloqueado.

O psicólogo autorizado deve conseguir acessar o prontuário conforme suas permissões.

### Resultado obtido

Não executado devido à indisponibilidade da aplicação no endereço informado.

### Situação

**Não executado.**

### Evidência

Aplicação retornando erro 404.

### Justificativa

É um teste de sistema porque o comportamento é verificado utilizando os perfis reais pela interface do sistema.

---

# Cenário 5 — Cadastro e localização de paciente

### Objetivo

Verificar se um paciente cadastrado pode posteriormente ser localizado utilizando diferentes critérios de pesquisa.

### Pré-condições

* sistema disponível;
* usuário autorizado.

### Dados utilizados

Paciente fictício:

* Nome: Maria Teste da Silva;
* CPF: utilizar CPF fictício válido;
* E-mail: [maria.teste@example.com](mailto:maria.teste@example.com).

### Passos

1. Acessar o cadastro de pacientes.
2. Cadastrar o paciente.
3. Salvar o cadastro.
4. Abrir a tela de pesquisa.
5. Pesquisar pelo nome.
6. Verificar o resultado.
7. Pesquisar pelo CPF.
8. Verificar o resultado.

### Resultado esperado

O paciente deve ser localizado tanto pelo nome quanto pelo CPF.

### Resultado obtido

Não executado devido à indisponibilidade da aplicação no endereço informado.

### Situação

**Não executado.**

### Evidência

Aplicação retornando erro 404.

### Justificativa

O cenário utiliza a interface e verifica o funcionamento conjunto do cadastro, armazenamento e pesquisa.

---

# Exercício 5 — Testes de Aceitação

Os testes de aceitação verificam se o sistema atende às necessidades do negócio e dos usuários da clínica. São testes que podem ser utilizados para decidir se determinada funcionalidade está adequada para ser aceita pelo cliente ou responsável pelo sistema.

---

## Critério de aceitação 1 — Agendamento

**Dado que** o paciente e o psicólogo estejam cadastrados e exista um horário disponível,

**Quando** a recepcionista selecionar o paciente, o psicólogo, a data e o horário e confirmar o agendamento,

**Então** o sistema deverá registrar a consulta e apresentar o compromisso na agenda do psicólogo.

**Critério de aprovação:**

O agendamento deve ser salvo corretamente e aparecer na agenda.

---

## Critério de aceitação 2 — Impedir conflito de horário

**Dado que** o psicólogo já possua uma consulta agendada para determinado horário,

**Quando** outro usuário tentar agendar uma segunda consulta para o mesmo psicólogo, na mesma data e horário,

**Então** o sistema deverá impedir o segundo agendamento e informar que o horário está indisponível.

**Critério de aprovação:**

Não podem existir duas consultas simultâneas para o mesmo psicólogo.

---

## Critério de aceitação 3 — Proteção de prontuários

**Dado que** um usuário não possua permissão para acessar prontuários,

**Quando** esse usuário tentar acessar informações de prontuário,

**Então** o sistema deverá bloquear o acesso.

**Critério de aprovação:**

Informações de prontuários somente podem ser acessadas por usuários autorizados.

---

## Critério de aceitação 4 — Atualização financeira

**Dado que** exista uma receita e uma despesa cadastradas,

**Quando** o usuário abrir o relatório financeiro,

**Então** o sistema deverá apresentar os lançamentos e calcular corretamente o saldo.

**Exemplo:**

Receita: R$ 2.000,00.

Despesa: R$ 800,00.

Saldo esperado: R$ 1.200,00.

**Critério de aprovação:**

O relatório deve apresentar os valores corretos.

---

## Critério de aceitação 5 — Alerta de estoque mínimo

**Dado que** um produto possua estoque mínimo de 5 unidades,

**Quando** a quantidade disponível ficar abaixo de 5 unidades,

**Então** o sistema deverá apresentar um alerta informando que o produto está abaixo do estoque mínimo.

**Critério de aprovação:**

O alerta deve aparecer quando a quantidade estiver abaixo do limite configurado.

---

# Exercício 6 — Classificação dos Testes

## 1. Verificar se receitas − despesas retorna o saldo correto.

**Classificação:** Teste unitário.

**Justificativa:**

Apenas uma regra matemática é verificada de forma isolada. Não é necessário utilizar a interface, o banco de dados ou outros componentes.

---

## 2. Verificar se uma receita salva aparece no relatório financeiro.

**Classificação:** Teste de integração.

**Justificativa:**

O teste verifica a comunicação entre o componente responsável pelo lançamento financeiro e o componente responsável pelo relatório.

---

## 3. Executar todo o fluxo entre cadastro, atendimento e pagamento.

**Classificação:** Teste de sistema.

**Justificativa:**

É avaliado um fluxo completo utilizando várias funcionalidades do sistema, semelhante ao uso realizado por um usuário final.

---

## 4. Confirmar com a direção da clínica se o relatório atende às necessidades administrativas.

**Classificação:** Teste de aceitação.

**Justificativa:**

O objetivo é verificar se a funcionalidade atende às necessidades reais do negócio e se pode ser aprovada pelo responsável pela clínica.

---

## 5. Verificar isoladamente a validação de CPF.

**Classificação:** Teste unitário.

**Justificativa:**

Apenas a função de validação do CPF é analisada, sem dependência de outros componentes.

---

## 6. Verificar se um reagendamento atualiza a agenda.

**Classificação:** Teste de integração.

**Justificativa:**

O teste verifica se a alteração realizada no componente de agendamento é corretamente refletida na agenda.

---

## 7. Avaliar se apenas psicólogos podem visualizar prontuários.

**Classificação:** Teste de sistema.

**Justificativa:**

O teste pode ser executado utilizando a interface e diferentes perfis de usuários, verificando o comportamento completo do sistema diante de uma tentativa de acesso.

---

## 8. Confirmar com a recepcionista se o processo de agendamento é adequado à rotina da clínica.

**Classificação:** Teste de aceitação.

**Justificativa:**

A recepcionista representa uma usuária do sistema e sua avaliação permite verificar se a funcionalidade atende à necessidade real da clínica.

---

# Parte 2 — Checklist de Testes Não Funcionais

Os testes não funcionais verificam características relacionadas à qualidade do sistema, como desempenho, segurança, facilidade de utilização e compatibilidade.

Foram definidos 20 testes, sendo:

* 5 de performance;
* 5 de segurança;
* 5 de usabilidade;
* 5 de compatibilidade.

---

# 2.1 Testes de Performance

## P01 — Tempo de carregamento da página inicial

**O que verificar:**

Verificar quanto tempo o sistema demora para apresentar a página inicial após o acesso.

**Como verificar:**

Abrir o sistema em um navegador e medir o tempo desde a solicitação até a apresentação da página utilizável.

**Critério esperado:**

A página inicial deve carregar em até 2 segundos em condições normais de rede e equipamento.

**Risco associado:**

Lentidão pode prejudicar a produtividade dos funcionários.

**Prioridade:**

Alta.

---

## P02 — Tempo de abertura da agenda

**O que verificar:**

Verificar o tempo necessário para abrir a agenda de consultas.

**Como verificar:**

Cadastrar ou simular grande quantidade de agendamentos e medir o tempo necessário para carregar a agenda.

**Critério esperado:**

A agenda deve estar disponível para interação em até 2 segundos em condições normais.

**Risco associado:**

Demora para consultar horários pode atrasar o atendimento.

**Prioridade:**

Alta.

---

## P03 — Velocidade da pesquisa de pacientes

**O que verificar:**

Verificar o tempo necessário para pesquisar um paciente.

**Como verificar:**

Realizar pesquisas por nome e CPF em uma base contendo diferentes quantidades de registros.

**Critério esperado:**

A pesquisa deve retornar resultados em até 2 segundos em uma base de tamanho esperado para a clínica.

**Risco associado:**

Pesquisa lenta pode aumentar o tempo necessário para realizar o atendimento.

**Prioridade:**

Alta.

---

## P04 — Tempo para salvar registros

**O que verificar:**

Verificar o tempo necessário para salvar cadastros e alterações.

**Como verificar:**

Realizar cadastros de pacientes, psicólogos e produtos e medir o tempo entre o comando de salvar e a confirmação da operação.

**Critério esperado:**

A confirmação deve ocorrer preferencialmente em até 2 segundos em condições normais.

**Risco associado:**

Demora pode levar o usuário a clicar várias vezes no botão, causando duplicidade ou confusão.

**Prioridade:**

Média.

---

## P05 — Comportamento com grande quantidade de dados

**O que verificar:**

Verificar o comportamento do sistema quando houver grande quantidade de pacientes, consultas, produtos e lançamentos financeiros.

**Como verificar:**

Executar o sistema com bases contendo aproximadamente 100, 1.000 e quantidade superior de registros, conforme capacidade definida para o projeto.

**Critério esperado:**

O sistema deve continuar funcionando sem travamentos e sem degradação que impeça o uso das funções principais.

**Risco associado:**

O sistema pode ficar lento ou travar quando a clínica possuir muitos registros.

**Prioridade:**

Alta.

---

# 2.2 Testes de Segurança

## S01 — Acesso não autenticado aos prontuários

**O que verificar:**

Verificar se um usuário não autenticado consegue acessar prontuários.

**Como verificar:**

Tentar acessar diretamente a funcionalidade de prontuários sem realizar login.

**Critério esperado:**

O acesso deve ser bloqueado.

**Risco associado:**

Exposição de informações sensíveis de saúde.

**Prioridade:**

Crítica.

---

## S02 — Restrição de acesso por perfil

**O que verificar:**

Verificar se cada perfil consegue acessar somente as funcionalidades autorizadas.

**Como verificar:**

Criar usuários com diferentes perfis e tentar acessar funcionalidades permitidas e não permitidas.

**Critério esperado:**

O sistema deve bloquear todas as funções não autorizadas.

**Risco associado:**

Acesso indevido a dados ou operações administrativas.

**Prioridade:**

Crítica.

---

## S03 — Entrada de HTML ou JavaScript

**O que verificar:**

Verificar se os campos de entrada aceitam código malicioso.

**Como verificar:**

Utilizar dados de teste controlados contendo caracteres e estruturas que representem possíveis entradas HTML ou JavaScript, sem executar ataques reais.

**Critério esperado:**

O sistema deve tratar a entrada como texto ou rejeitá-la, sem executar código no navegador.

**Risco associado:**

Possibilidade de execução de código malicioso e comprometimento da segurança dos usuários.

**Prioridade:**

Crítica.

---

## S04 — Exposição de informações sensíveis no armazenamento do navegador

**O que verificar:**

Verificar se dados sensíveis, principalmente informações de pacientes e prontuários, ficam expostos de forma inadequada no armazenamento do navegador.

**Como verificar:**

Inspecionar o armazenamento local do navegador durante testes utilizando somente dados fictícios.

**Critério esperado:**

Dados sensíveis não devem ficar armazenados de forma inadequadamente acessível a usuários não autorizados.

**Risco associado:**

Exposição de informações pessoais e clínicas.

**Prioridade:**

Crítica.

---

## S05 — Expiração da sessão

**O que verificar:**

Verificar se a sessão do usuário é encerrada após logout ou expiração.

**Como verificar:**

Realizar login, sair do sistema e tentar retornar a uma tela protegida utilizando o histórico ou endereço direto.

**Critério esperado:**

Após o logout, páginas protegidas devem exigir nova autenticação.

**Risco associado:**

Outra pessoa utilizando o mesmo computador poderia acessar informações privadas.

**Prioridade:**

Alta.

---

# 2.3 Testes de Usabilidade

## U01 — Clareza dos menus

**O que verificar:**

Verificar se os nomes dos menus representam claramente suas funções.

**Como verificar:**

Solicitar que um usuário identifique onde cadastrar pacientes, agendar consultas, acessar agenda e consultar relatórios.

**Critério esperado:**

O usuário deve conseguir identificar as principais funções sem precisar de explicação adicional.

**Risco associado:**

Dificuldade de aprendizado e execução incorreta das tarefas.

**Prioridade:**

Média.

---

## U02 — Facilidade para cadastrar paciente

**O que verificar:**

Verificar se o processo de cadastro é simples e compreensível.

**Como verificar:**

Solicitar que um usuário realize um cadastro utilizando dados fictícios.

**Critério esperado:**

O usuário deve conseguir concluir o cadastro sem dificuldades ou dúvidas significativas.

**Risco associado:**

Cadastro incorreto e aumento do tempo de atendimento.

**Prioridade:**

Alta.

---

## U03 — Mensagens de erro

**O que verificar:**

Verificar se as mensagens apresentadas em situações de erro são claras.

**Como verificar:**

Tentar salvar um cadastro com campos obrigatórios vazios ou informações inválidas.

**Critério esperado:**

O sistema deve indicar claramente qual informação precisa ser corrigida.

**Risco associado:**

Usuário pode não compreender como corrigir o problema.

**Prioridade:**

Média.

---

## U04 — Confirmação antes de exclusões

**O que verificar:**

Verificar se o sistema solicita confirmação antes de excluir dados importantes.

**Como verificar:**

Tentar excluir um paciente, produto ou outro registro permitido.

**Critério esperado:**

O sistema deve apresentar uma confirmação antes de realizar a exclusão definitiva.

**Risco associado:**

Exclusão acidental de informações importantes.

**Prioridade:**

Alta.

---

## U05 — Indicação de campos obrigatórios

**O que verificar:**

Verificar se os campos obrigatórios estão visualmente identificados.

**Como verificar:**

Abrir os formulários de cadastro e observar a identificação dos campos obrigatórios.

**Critério esperado:**

O usuário deve conseguir identificar claramente quais campos precisam ser preenchidos.

**Risco associado:**

Aumento de erros e tentativas de envio de formulários incompletos.

**Prioridade:**

Média.

---

# 2.4 Testes de Compatibilidade

## C01 — Chrome

**O que verificar:**

Verificar o funcionamento do sistema no Google Chrome.

**Como verificar:**

Executar as principais funcionalidades no navegador.

**Critério esperado:**

Cadastro, agenda, consultas, relatórios e demais funções principais devem funcionar corretamente.

**Risco associado:**

Falha para usuários que utilizam o navegador.

**Prioridade:**

Alta.

---

## C02 — Firefox

**O que verificar:**

Verificar o funcionamento do sistema no Mozilla Firefox.

**Como verificar:**

Executar os principais fluxos utilizando o navegador Firefox.

**Critério esperado:**

As funcionalidades devem apresentar comportamento equivalente ao navegador principal.

**Risco associado:**

Parte dos usuários pode encontrar erros ou funções indisponíveis.

**Prioridade:**

Média.

---

## C03 — Microsoft Edge

**O que verificar:**

Verificar o funcionamento do sistema no Microsoft Edge.

**Como verificar:**

Executar os principais fluxos no navegador Edge.

**Critério esperado:**

O sistema deve carregar e executar suas principais funções corretamente.

**Risco associado:**

Incompatibilidades podem impedir o trabalho de determinados usuários.

**Prioridade:**

Média.

---

## C04 — Dispositivo móvel

**O que verificar:**

Verificar a utilização do sistema em celulares.

**Como verificar:**

Testar em resolução aproximada de 360 pixels de largura e verificar menus, formulários, tabelas e botões.

**Critério esperado:**

Os elementos devem permanecer acessíveis e não devem ultrapassar a tela de maneira que impeça a utilização.

**Risco associado:**

Tabelas ou botões podem ficar cortados e dificultar o atendimento.

**Prioridade:**

Alta.

---

## C05 — Diferentes resoluções de tela

**O que verificar:**

Verificar a apresentação em diferentes tamanhos de tela.

**Como verificar:**

Testar pelo menos as resoluções aproximadas de:

* 360 px;
* 768 px;
* 1366 px.

**Critério esperado:**

A interface deve permanecer utilizável nas diferentes resoluções.

**Risco associado:**

Problemas de layout podem impedir o acesso a informações ou funcionalidades.

**Prioridade:**

Alta.

---

# Resumo do Checklist Não Funcional

| Código | Categoria       | Teste                                   | Prioridade |
| ------ | --------------- | --------------------------------------- | ---------- |
| P01    | Performance     | Carregamento da página inicial          | Alta       |
| P02    | Performance     | Abertura da agenda                      | Alta       |
| P03    | Performance     | Pesquisa de pacientes                   | Alta       |
| P04    | Performance     | Salvamento de registros                 | Média      |
| P05    | Performance     | Grande quantidade de dados              | Alta       |
| S01    | Segurança       | Acesso não autenticado                  | Crítica    |
| S02    | Segurança       | Restrição por perfil                    | Crítica    |
| S03    | Segurança       | Entrada de HTML/JavaScript              | Crítica    |
| S04    | Segurança       | Exposição no armazenamento do navegador | Crítica    |
| S05    | Segurança       | Expiração da sessão                     | Alta       |
| U01    | Usabilidade     | Clareza dos menus                       | Média      |
| U02    | Usabilidade     | Cadastro de paciente                    | Alta       |
| U03    | Usabilidade     | Mensagens de erro                       | Média      |
| U04    | Usabilidade     | Confirmação de exclusões                | Alta       |
| U05    | Usabilidade     | Campos obrigatórios                     | Média      |
| C01    | Compatibilidade | Google Chrome                           | Alta       |
| C02    | Compatibilidade | Mozilla Firefox                         | Média      |
| C03    | Compatibilidade | Microsoft Edge                          | Média      |
| C04    | Compatibilidade | Dispositivo móvel                       | Alta       |
| C05    | Compatibilidade | Diferentes resoluções                   | Alta       |

---

# 3. Relatório de Defeitos

## 3.1 Defeito encontrado durante a verificação do endereço

**ID:** DEF-001

**Título:** Aplicação indisponível no endereço informado.

**Categoria:** Disponibilidade.

**Severidade:** Alta.

**Prioridade:** Alta.

**Pré-condição:**

Possuir acesso à internet e utilizar o endereço informado no enunciado.

**Passos para reprodução:**

1. Abrir um navegador.
2. Acessar o endereço da Clínica Psi informado na atividade.
3. Aguardar o carregamento da aplicação.

**Resultado esperado:**

A página inicial da Clínica Psi deveria ser exibida e permitir o acesso às funcionalidades disponíveis.

**Resultado obtido:**

O endereço retornou erro HTTP 404 (página não encontrada).

**Impacto:**

A indisponibilidade impede a execução dos testes de sistema, usabilidade e compatibilidade diretamente na aplicação.

**Evidência:**

Mensagem de erro HTTP 404 apresentada ao acessar o endereço.

**Situação:**

Reprovado/indisponível para execução.

**Observação:**

Esse defeito deve ser reavaliado posteriormente, pois pode estar relacionado à publicação do projeto, configuração do GitHub Pages, alteração do endereço ou indisponibilidade temporária.

---

# 4. Conclusão

A análise realizada demonstra que a Clínica Psi pode ser avaliada por diferentes níveis de testes.

Os testes unitários são importantes para verificar regras pequenas e isoladas, como validação de CPF, cálculo financeiro e identificação de estoque mínimo.

Os testes de integração são importantes para verificar a comunicação entre os componentes, como cadastro e banco de dados, agendamento e agenda, lançamento financeiro e relatório e movimentação de produtos e estoque.

Os testes de sistema permitem avaliar fluxos completos pela perspectiva do usuário, como o atendimento completo, reagendamento, controle de estoque e controle de acesso.

Os testes de aceitação verificam se as funcionalidades atendem às necessidades da clínica e dos usuários responsáveis pelo processo.

Além dos testes funcionais, os testes não funcionais são fundamentais para verificar aspectos de qualidade. Performance permite avaliar se o sistema apresenta velocidade adequada; segurança verifica a proteção dos dados e das funcionalidades; usabilidade verifica se os usuários conseguem utilizar o sistema de maneira clara e eficiente; e compatibilidade verifica o funcionamento em diferentes navegadores, dispositivos e resoluções.

A definição de riscos e prioridades permite identificar quais problemas devem receber maior atenção. Questões relacionadas à proteção de prontuários e dados sensíveis, por exemplo, devem receber prioridade crítica ou alta devido ao impacto que um acesso não autorizado poderia causar.

Durante a verificação realizada para este trabalho, a aplicação indicada no enunciado não estava disponível e retornou erro 404. Por esse motivo, os resultados dos testes que dependem da utilização da interface não foram inventados. Esses testes devem ser executados novamente quando a aplicação estiver disponível, registrando-se capturas de tela, vídeos ou outras evidências para comprovar os resultados.

Conclui-se que uma estratégia de testes completa deve combinar testes unitários, de integração, de sistema, de aceitação e não funcionais. A utilização conjunta desses níveis permite identificar problemas tanto nas regras individuais quanto na integração entre componentes e na experiência geral do usuário.

---

# 5. Resumo da Entrega

A atividade contempla os seguintes itens:

* 5 funcionalidades analisadas;
* 5 testes unitários;
* 5 testes de integração;
* 5 cenários de testes de sistema;
* 5 critérios de aceitação;
* classificação dos 8 cenários propostos;
* 5 testes de performance;
* 5 testes de segurança;
* 5 testes de usabilidade;
* 5 testes de compatibilidade;
* identificação de riscos;
* definição de prioridades;
* relatório de defeito;
* justificativas para as classificações;
* conclusão da análise.

Os dados utilizados nos testes propostos devem ser fictícios. Não devem ser utilizados CPF real, dados reais de pacientes, informações clínicas reais ou qualquer outro dado pessoal sensível.
