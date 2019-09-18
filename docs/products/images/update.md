Altera uma imagem no produto.

## Endpoint

```
PUT "https://app.pedidosdigitais.com.br/api/v2/products/{id}/images/{image_id}"
```

| Params   | Description   |
| -------- | ------------- |
| id       | Id do produto |
| image_id | Id da imagem  |

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
{
  "default": 1
}
```

| Field   | Description             | Rules                                |
| ------- | ----------------------- | ------------------------------------ |
| default | Se a imagem será padrão | Obrigatório, ùnico valor possível: 1 |

## Response

_http status code 201_

```json
{
  "data": {
    "id": 38,
    "url": "https://app.pedidosdigitais.com.br/storage/uploads/1/products/500x500/2019-06-28-164720-4.jpg",
    "default": 1
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

**Imagem não encontrado**

_Http status code 404_

```json
{
  "error": "Imagem not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
