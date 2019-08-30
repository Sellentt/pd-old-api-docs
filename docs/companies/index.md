Lista os clientes.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/companies"
```

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

*http status code 200*

```json
{
  "data": [
    {
      "id": 1,
      "code": "1020",
      "name": "Cliente 1",
      "created_at": "2019-08-26 08:36:56",
      "updated_at": "2019-08-26 08:36:56",
      "group": {
        "id": 1,
        "name": "Lojistas Classe A"
      }
    },
    {
      "id": 2,
      "code": "1021",
      "name": "Google Inc.",
      "created_at": "2019-08-28 15:43:21",
      "updated_at": "2019-08-28 15:43:21",
      "group": {
        "id": 1,
        "name": "Lojistas Classe A"
      }
    },
    {
      "id": 3,
      "code": "1022",
      "name": "Apple Inc.",
      "created_at": "2019-08-28 15:43:56",
      "updated_at": "2019-08-28 15:43:56",
      "group": {
        "id": 1,
        "name": "Lojistas Classe A"
      }
    }
  ],
  "links": {
    "first": "https://app.pedidosdigitais.com.br/api/v2/companies?page=1",
    "last": "https://app.pedidosdigitais.com.br/api/v2/companies?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "https://app.pedidosdigitais.com.br/api/v2/companies",
    "per_page": 20,
    "to": 3,
    "total": 3
  }
}
```

## Errors

**Token não enviado**

*Http status code 401*

```json
{
  "error": "Token not found."
}
```

**Token inválido**

*Http status code 401*

```json
{
  "error": "Invalid token."
}
```

**Erro interno do servidor**

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
