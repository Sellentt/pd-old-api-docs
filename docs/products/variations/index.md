Listar as variações precificadas de um produto.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/products/{id}/variations"
```

| Params | Description   |
| ------ | ------------- |
| id     | Id do produto |

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

_http status code 200_

```json
{
  "data": [
    {
      "id": 7,
      "name": "SSD 1 TB",
      "price_change_type": "increase",
      "price_change_amount": "0.12",
      "price_change_option": "amount",
      "created_at": "2019-09-19 12:02:58",
      "updated_at": "2019-09-19 12:02:58"
    },
    {
      "id": 8,
      "name": "SSD 512 GB",
      "price_change_type": "none",
      "price_change_amount": null,
      "price_change_option": null,
      "created_at": "2019-09-19 17:28:20",
      "updated_at": "2019-09-19 17:28:20"
    }
  ]
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

**Produto não encontrado**

_Http status code 404_

```json
{
  "error": "Product not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
