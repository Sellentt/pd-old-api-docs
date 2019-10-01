Altera um status de pedido.

## Endpoint

```
PUT "https://app.pedidosdigitais.com.br/api/v2/orders/status/{id}"
```

| Params | Description  |
| ------ | ------------ |
| id     | Id do status |

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
{
  "name": "Aguardando Pagto.",
  "color": "#CCCCCC",
  "is_active": 0
}
```

| Field                  | Description                | Rules                                                |
| ---------------------- | -------------------------- | ---------------------------------------------------- |
| name (_required_)      | Nome do status             | Min 2, max 200                                       |
| color (_required_)     | Cor hexadecimal            | Deve ser uma cor hexadecimal válida e iniciada com # |
| is_active (_required_) | Status do status do pedido | 0 ou 1                                               |

## Response

_http status code 200_

```json
{
  "data": {
    "id": 3,
    "name": "Aguardando Pagto.",
    "color": "#EEEEEE",
    "is_active": 1,
    "updated_at": "2019-09-23 16:12:53",
    "created_at": "2019-09-23 16:12:53"
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

**Status do pedido não encontrado**

_Http status code 404_

```json
{
  "error": "Order status not found."
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
