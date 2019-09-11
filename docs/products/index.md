Listar os produtos de um cliente.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/products"
```

# Query strings (Filters)

| Field | Type                       | Description                                                           |
| ----- | -------------------------- | --------------------------------------------------------------------- |
| after | date (YYYY-MM-DDTHH:MM:SS) | Dos produtos alterados desta data em diante (ex: 2019-09-05T12:00:00) |
| page  | integer                    | Paginação dos produtos                                                |

**Observações**

Quando é enviado o parâmetro `after` o sistema irá retornar todos os produtos que foram alterados desta data em diante, inclusive os produtos que foram _"removidos"_.

Você pode identificar que um produto foi removido caso exista na chave `deleted_at` um valor preenchido. Esse valor é a data/hora que o produto foi removido.

Veja abaixo um exemplo usando os dois parâmetros:

```
GET "https://app.pedidosdigitais.com.br/api/v2/products?page=1&after=2019-09-10"
```

Na requisição acima, o sistema irá retornar a primeira página (20 registros por página) dos produtos que foram alterados ou removidos do dia 10/09/2019 em diante.

Passar o parâmetro `after` é uma ótima forma de criar uma rotina que irá atualizar seu sistema de tempos em tempos caso o cliente tenha feito alguma alteração de produto direto no painel do Pedidos Digitais.

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
      "id": 3,
      "code": "1005",
      "name": "Produto de teste completamento preenchido",
      "average_weight": "12.55",
      "price": {
        "default": "1850.79"
      },
      "category": {
        "id": 4,
        "name": "Samsung"
      },
      "images": [
        {
          "id": 3,
          "path": "https://app.pedidosdigitais.com.br/storage/uploads/1/products/500x500/image.jpg",
          "default": 1
        }
      ],
      "video": "https://www.youtube.com/watch?v=CODE",
      "description": {
        "text": "Minha descrição em texto simples.",
        "html": "<p>Minha <strong>descri&ccedil;&atilde;o</strong> em <em>HTML</em>.</p>"
      },
      "variations": [
        {
          "type": "select",
          "slug": "cor",
          "name": "Cor",
          "options": ["Azul", "*Amarelo", "Vermelho", "Verde"]
        },
        {
          "type": "radio",
          "slug": "tamanho",
          "name": "Tamanho",
          "options": ["Pequeno", "Médio", "Grande"]
        },
        {
          "type": "text",
          "slug": "gravura",
          "name": "Gravura",
          "options": ["50"]
        },
        {
          "type": "image",
          "slug": "estampa",
          "name": "Estampa",
          "options": [
            {
              "value": "Imagem 1",
              "path": "/storage/uploads/1/products/variations/300x300/2019-06-28-164720-5.jpg"
            },
            {
              "value": "Imagem 2",
              "path": "/storage/uploads/1/products/variations/300x300/2019-06-28-164720-6.jpg"
            }
          ]
        }
      ],
      "catalog": {
        "is_catalog": 1,
        "title": "Título para o catálogo",
        "collection": "Coleção Verão",
        "description": "Descrição em texto simples para o catálogo.",
        "price": {
          "default": "2250.99",
          "offer": "1850.79"
        },
        "image": "https://app.pedidosdigitais.com.br/storage/uploads/1/catalog/500x500/2019-06-28-164720.jpg"
      },
      "has_stock": 1,
      "is_featured": 1,
      "is_automated": 1,
      "is_active": 1,
      "created_at": "2019-09-10 12:12:51",
      "updated_at": "2019-09-10 12:12:51",
      "deleted_at": ""
    }
  ],
  "links": {
    "first": "https://app.pedidosdigitais.com.br/api/v2/products?page=1",
    "last": "https://app.pedidosdigitais.com.br/api/v2/products?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "https://app.pedidosdigitais.com.br/api/v2/products",
    "per_page": 20,
    "to": 3,
    "total": 3
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

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
