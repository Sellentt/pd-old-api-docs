Detalhes de uma variação precificada de um produto.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/products/{id}/variations/{variation_id}"
```

| Params       | Description                |
| ------------ | -------------------------- |
| id           | Id do produto              |
| variation_id | Id da variação precificada |

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

_http status code 200_

```json
{
  "data": {
    "id": 8,
    "name": "SSD 512 GB",
    "price_change_type": "increase",
    "price_change_amount": "1.50",
    "price_change_option": "amount",
    "created_at": "2019-09-19 17:28:20",
    "updated_at": "2019-09-19 17:28:20"
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

**Variação não encontrada**

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
