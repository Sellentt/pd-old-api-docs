Detalhes de um produto.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/products/{id}"
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
  "data": {
    "id": 14526,
    "code": "MOTOG",
    "name": "Moto G Novo Produto",
    "average_weight": "12.50",
    "price": {
      "default": "1980.91"
    },
    "category": {
      "id": 65,
      "name": "Geral"
    },
    "images": [
      {
        "id": 8535,
        "path": "http://app.pedidosdigitais.com.br/storage/uploads/1/products/500x500/MOTOG.jpg",
        "default": 1
      },
      {
        "id": 17405,
        "path": "http://app.pedidosdigitais.com.br/storage/uploads/1/products/500x500/61tqkjf2sdl-sl1000-1.jpg",
        "default": 0
      }
    ],
    "video": null,
    "description": {
      "text": "",
      "html": "<p>Descri&ccedil;&atilde;o do <strong>moto g</strong></p>"
    },
    "variations": [
      {
        "type": "select",
        "slug": "aro",
        "name": "Aro",
        "options": [
          "10",
          "11",
          "12",
          "13",
          "14",
          "15",
          "16",
          "17",
          "18",
          "19",
          "20"
        ]
      }
    ],
    "catalog": {
      "is_catalog": 1,
      "title": "Teste",
      "collection": "2018",
      "description": "Descrição de teste",
      "price": {
        "default": "199.20",
        "offer": "152.14"
      },
      "image": "http://app.pedidosdigitais.com.br/storage/uploads/1/catalog/500x500/captura-de-tela-de-2018-08-07-231044.png"
    },
    "has_stock": 0,
    "is_featured": 0,
    "is_automated": 1,
    "is_active": 1,
    "created_at": "2018-08-16 23:17:44",
    "updated_at": "2019-08-14 11:01:12",
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

**Loja não encontrada**

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
