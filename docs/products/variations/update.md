Altera uma variação precificada de um produto.

## Endpoint

```
PUT "https://app.pedidosdigitais.com.br/api/v2/products/{id}/variations/{variation_id}"
```

| Params       | Description                |
| ------------ | -------------------------- |
| id           | Id do produto              |
| variation_id | Id da variação precificada |

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
{
  "name": "SSD 512 GB",
  "price_change_type": "increase",
  "price_change_amount": 1.5,
  "price_change_option": "amount"
}
```

| Field               | Description                      | Rules                                                                                            |
| ------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------ |
| name                | Nome da variação                 | Obrigatório, máx 50.                                                                             |
| price_change_type   | Se terá acréscimo no preço final | Obrigatório, Pode ser none ou increase                                                           |
| price_change_amount | Valor do acréscimo               | Obrigatório caso `price_change_type` for `increase`, deve ser um número com até 2 casas decimais |
| price_change_option | Tipo de acréscimo                | Obrigatório caso `price_change_type` for `increase`, Pode ser `amount` ou `percent`              |

## Response

_http status code 201_

```json
{
  "data": {
    "id": 8,
    "name": "SSD 512 GB",
    "price_change_type": "increase",
    "price_change_amount": 1.5,
    "price_change_option": "amount",
    "updated_at": "2019-09-19 17:28:20",
    "created_at": "2019-09-19 17:28:20"
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

**Variação não encontrado**

_Http status code 404_

```json
{
  "error": "Variation not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
