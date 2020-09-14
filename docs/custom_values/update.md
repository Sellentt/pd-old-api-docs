Altera um campo personalizado.

## Endpoint

```
PUT "https://app.pedidosdigitais.com.br/api/v2/custom_values/{id}"
```

| Params | Description                     |
| ------ | ------------------------------- |
| id     | Id do campo personalizado com valor que será alterado |

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
{
    "product_id": "23726",
    "product_custom_field_id": "9",
    "value": "1"
}
```

| Field                          | Description                                                      | Rules                                          |
| ------------------------------ | ---------------------------------------------------------------- | ---------------------------------------------- |
| product_id                     | Id do produto que receberá o valor                               | Obrigatório, produto existente
| product_custom_field_id        | ID do campo personalizado                                        | Obrigatório, campo personalizado existente
| value                          | Valor que será adicionado ao campo                               | Obrigatório
| name                           | Nome do campo                                                    | Obrigatório                      |

## Response

_http status code 201_

```json
{
    "data": {
        "id": 61,
        "product_id": 23726,
        "product_custom_field_id": 9,
        "value": "1",
        "created_at": "2020-09-14 10:02:41",
        "updated_at": "2020-09-14 13:22:46",
        "deleted_at": ""
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
    "field1": "Error message 1.",
    "field1": "Error message 2.",
    "field1": "Error message 3."
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
