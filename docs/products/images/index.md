Listar as imagens de um produto.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/products/{id}/images"
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
      "id": 36,
      "url": "https://api.pedidosdigitais.com.br/storage/uploads/1/products/500x500/2019-06-28-164720.jpg",
      "default": 0
    },
    {
      "id": 38,
      "url": "https://api.pedidosdigitais.com.br/storage/uploads/1/products/500x500/2019-06-28-164720-4.jpg",
      "default": 1
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

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
