Adiciona um novo cliente.

**Endpoint**

```
POST "https://app.pedidosdigitais.com.br/api/v2/companies"
```

**Headers**

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

**Body**

```json
{
  "data": {
    "id": 6,
    "code": "1026",
    "name": "Apple Inc.",
    "created_at": "2019-08-29 08:41:14",
    "updated_at": "2019-08-29 08:41:14",
    "group": {
      "id": 1,
      "name": "Lojistas Classe A"
    }
  }
}
```

| Field | Description | Rules |
|---|---|---|
| code (*required*) | Código único do cliente | Min 2, max 50 |
| name (*required*) | Nome do cliente | Min 2, max 100 |
| group_id (*required*) | Id do grupo do tipo lojista | Deve existir |


**Response**

*http status code 201*


```json
{
  "data": {
    "id": 3,
    "code": "1022",
    "name": "Apple Inc.",
    "created_at": "2019-08-28 15:43:56",
    "updated_at": "2019-08-28 15:43:56"
  }
}
```

**Errors**

Token não enviado

*Http status code 401*

```json
{
  "error": "Token not found."
}
```

Token inválido

*Http status code 401*

```json
{
  "error": "Invalid token."
}
```

Erros nos dados enviados

*Http status code 422*


```json
{
  "error": "Unprocessable Entity",
  "invalid_fields": {
    "name": "The name field is required.",
    "code": "The code field is required.",
    "group_id": "The group id field is required."
  }
}
```

Erro interno do servidor

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```


