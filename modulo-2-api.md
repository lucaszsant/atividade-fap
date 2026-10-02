# Análise da API Pública ReqRes

## API escolhida

**API:** ReqRes

**Documentação:** https://reqres.in/

A ReqRes é uma API pública utilizada para estudos e testes de aplicações. Nesta atividade foram analisados dois endpoints: um endpoint de leitura utilizando GET e um endpoint de criação utilizando POST.

---

# 1. Endpoint GET — Consulta de usuários

## 1. Identificação e Finalidade

### Endpoint/Rota

GET /api/users

### Objetivo de Negócio

Esse endpoint permite consultar uma lista de usuários cadastrados no sistema. Em uma aplicação real, poderia ser utilizado para exibir uma lista de usuários em uma tela administrativa.

---

## 2. Estrutura do Request

### Método HTTP

GET

### URL Completa

https://reqres.in/api/users?page=2

O parâmetro page=2 indica que estamos solicitando a segunda página da lista de usuários.

### Headers

Não foi necessário informar headers para realizar essa chamada GET.

### Body

N/A

A requisição GET utilizada não possui corpo.

---

## 3. Estrutura do Response

### Status Code Esperado

200 OK

O código 200 indica que a requisição foi processada com sucesso.

### Payload de Retorno

A chamada foi executada utilizando um script TypeScript com fetch. Abaixo está o JSON real retornado pela API:

```json
{
  page: 2
  "per_page": 6,
  "total": 12,
  "total_pages": 2,
  "data": [
    {
      "id": 7,
      "email": "michael.lawson@reqres.in",
      "first_name": "Michael",
      "last_name": "Lawson",
      "avatar": "https://reqres.in/img/faces/7-image.jpg"
    },
    {
      "id": 8,
      "email": "lindsay.ferguson@reqres.in",
      "first_name": "Lindsay",
      "last_name": "Ferguson",
      "avatar": "https://reqres.in/img/faces/8-image.jpg"
    },
    {
      "id": 9,
      "email": "tobias.funke@reqres.in",
      "first_name": "Tobias",
      "last_name": "Funke",
      "avatar": "https://reqres.in/img/faces/9-image.jpg"
    },
    {
      "id": 10,
      "email": "byron.fields@reqres.in",
      "first_name": "Byron",
      "last_name": "Fields",
      "avatar": "https://reqres.in/img/faces/10-image.jpg"
    },
    {
      "id": 11,
      "email": "george.edwards@reqres.in",
      "first_name": "George",
      "last_name": "Edwards",
      "avatar": "https://reqres.in/img/faces/11-image.jpg"
    },
    {
      "id": 12,
      "email": "rachel.howell@reqres.in",
      "first_name": "Rachel",
      "last_name": "Howell",
      "avatar": "https://reqres.in/img/faces/12-image.jpg"
    }
  ],
  "support": {
    "url": "https://benhowdle.im/first-cto-playbook?utm_source=reqres&utm_medium=json&utm_campaign=referral&utm_content=c_script",
    "text": "Become a better CTO. A playbook of painful stories and practical advice from a two-time startup CTO."
  },
  "_meta": {
    "powered_by": "ReqRes",
    "docs_url": "https://app.reqres.in/documentation",
    "upgrade_url": "https://app.reqres.in/upgrade",
    "example_url": "https://app.reqres.in/examples/notes-app",
    "variant": "v1_a",
    "message": "Your data persists here. Add auth, logs, and custom schemas to build a real backend.",
    "cta": {
      "label": "See example app",
      "url": "https://app.reqres.in/examples/notes-app"
    },
    "context": "legacy_success"
  }
}
