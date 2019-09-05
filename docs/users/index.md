Lista os usuários cadastrados.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/users"
```

## Headers

```
"Authorization": "Bearer TOKEN"
```

## User Types

| Type    | Description   | Access           |
| ------- | ------------- | ---------------- |
| regular | Regular users | Dashboard        |
| seller  | Seller users  | Frontend / Store |
| agent   | Agent users   | Dashboard        |

## Response

_http status code 200_

```json
{
  "data": [
    {
      "id": 3,
      "name": "Representante 1",
      "email": "rep1@domain.com.br",
      "type": "agent",
      "is_active": 1,
      "created_at": "2019-09-03 08:16:12",
      "updated_at": "2019-09-03 08:16:12",
      "group": {
        "id": 3,
        "name": "Meus Representantes"
      },
      "company": null
    },
    {
      "id": 4,
      "name": "Representante 2",
      "email": "rep2@domain.com.br",
      "type": "agent",
      "is_active": 1,
      "created_at": "2019-09-03 08:17:07",
      "updated_at": "2019-09-03 08:17:07",
      "group": {
        "id": 3,
        "name": "Meus Representantes"
      },
      "company": null
    },
    {
      "id": 5,
      "name": "Funcionário Loja 1",
      "email": "func1@domain.com.br",
      "type": "seller",
      "is_active": 1,
      "created_at": "2019-09-05 09:11:22",
      "updated_at": "2019-09-05 09:11:22",
      "group": {
        "id": 1,
        "name": "Lojista Padrão"
      },
      "company": {
        "id": 1,
        "name": "Total Tech"
      }
    },
    {
      "id": 6,
      "name": "Colab1",
      "email": "colab1@gmail.com",
      "type": "regular",
      "is_active": 1,
      "created_at": "2019-09-05 09:56:50",
      "updated_at": "2019-09-05 09:56:50",
      "group": {
        "id": 4,
        "name": "Meus Colaboradores"
      },
      "company": null
    }
  ],
  "links": {
    "first": "https://app.pedidosdigitais.com.br/api/v2/users?page=1",
    "last": "https://app.pedidosdigitais.com.br/api/v2/users?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "https://app.pedidosdigitais.com.br/api/v2/users",
    "per_page": 20,
    "to": 4,
    "total": 4
  }
}
```

# Errors

**Token não enviado**

_Http status code 401_

```json
{
  "error": "Token not found."
}
```

**Token inválido**

_Http status code 401_

```json
{
  "error": "Invalid token."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
