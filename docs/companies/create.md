Adiciona um novo cliente.

## Endpoint

```
POST "https://app.pedidosdigitais.com.br/api/v2/companies"
```

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
{
  "code": "1001",
  "name": "Info Basics Acessórios",
  "group_id": 1
}
```

| Field                 | Description                 | Rules          |
| --------------------- | --------------------------- | -------------- |
| code (_required_)     | Código único do cliente     | Min 2, max 50  |
| name (_required_)     | Nome do cliente             | Min 2, max 100 |
| group_id (_required_) | Id do grupo do tipo lojista | Deve existir   |

## Response

_http status code 201_

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

## Errors

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

**Erros nos dados enviados**

_Http status code 422_

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

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
