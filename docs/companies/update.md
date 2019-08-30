Altera um cliente.

## Endpoint

```
PUT "https://app.pedidosdigitais.com.br/api/v2/companies/{id}"
```

| Params | Description |
|---|---|
| id | Id do cliente que será alterado |

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
{
  "code": "1005",
  "name": "Apple Inc.", 
  "group_id": 1
}
```

| Field | Description | Rules |
|---|---|---|
| code (*required*) | Código do cliente | Min 1, max 50 |
| name (*required*) | Nome do cliente | Min 2, max 100 |
| group_id (*required*) | Id do grupo | Deve ser de um grupo que existe |


## Response

*http status code 200*

```json
{
  "data": {
    "id": 1,
    "code": "1005",
    "name": "Apple Inc.",
    "created_at": "2019-08-28 15:43:56",
    "updated_at": "2019-08-29 11:05:45",
    "group": {
      "id": 4,
      "name": "Lojistas Padrão"
    }
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

**Cliente não encontrado**

*Http status code 404*

```json
{
  "error": "Company not found."
}
```

**Grupo não encontrado**

*Http status code 404*

```json
{
  "error": "Group not found."
}
```

**Erros nos dados enviados**

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

**Erro interno do servidor**

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
