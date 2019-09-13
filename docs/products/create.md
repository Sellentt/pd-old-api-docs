Adiciona um novo produto.

## Endpoint

```
POST "https://app.pedidosdigitais.com.br/api/v2/products"
```

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
{
  "code": "CODE",
  "name": "Nome do produto",
  "average_weight": 1.85,
  "price": {
    "default": 1580.95
  },
  "category_id": 1,
  "images": [
    {
      "file_id": 1,
      "default": 0
    },
    {
      "file_id": 2,
      "default": 1
    },
    {
      "file_id": 3,
      "default": 0
    }
  ],
  "video": "https://www.youtube.com/watch?v=KG54us1diCw",
  "description": {
    "text": "text description",
    "html": "html description"
  },
  "variations": [
    {
      "type": "select",
      "name": "Cor",
      "options": [
        {
          "value": "Azul",
          "default": 0
        },
        {
          "value": "Amarelo",
          "default": 1
        },
        {
          "value": "Vermelho",
          "default": 0
        }
      ]
    },
    {
      "type": "radio",
      "name": "Tamanho",
      "options": [
        {
          "value": "Pequeno",
          "default": 0
        },
        {
          "value": "Médio",
          "default": 0
        },
        {
          "value": "Grande",
          "default": 0
        }
      ]
    },
    {
      "type": "text",
      "name": "Gravura",
      "maxlength": 50
    },
    {
      "type": "image",
      "name": "Textura",
      "options": [
        {
          "value": "Textura 1",
          "file_id": 1
        },
        {
          "value": "Textura 2",
          "file_id": 2
        },
        {
          "value": "Textura 3",
          "file_id": 8
        }
      ]
    }
  ],
  "catalog": {
    "title": "Teste",
    "collection": "2018",
    "description": "Descrição de teste",
    "price": {
      "default": 29.9,
      "offer": 19.95
    },
    "file_id": 5
  },
  "has_stock": 1,
  "is_featured": 0,
  "is_automated": 0,
  "is_active": 1
}
```

| XXXX | YYYY | Regras |

| Field                          | Description                                                      | Rules                                          |
| ------------------------------ | ---------------------------------------------------------------- | ---------------------------------------------- |
| code                           | Código do produto                                                | Obrigatório, mín 3, máx 30, único              |
| name                           | Nome do produto                                                  | Obrigatório, mín 2, máx 150                    |
| average_weight                 | Peso médio do produto                                            | Numérico, min 0.01, máx 10000000               |
| price.default                  | Valor do produto                                                 | Obrigatório, numérico, máx 10000000            |
| category_id                    | Id da categoria do produto                                       | Obrigatório, numérico, Id deve existir         |
| images[].file_id               | Id do arquivo enviado na api de uploads                          | Id do upload de arquivo deve existir           |
| images[].default               | Se é a imagem padrão                                             | Se é padrão, valores aceitos: 0 ou 1           |
| video                          | Vídeo do produto                                                 | Link youtube, máx 200                          |
| description.text               | Descrição em texto simples                                       | Máx 250                                        |
| description.html               | Descrição em html                                                |                                                |
| variations[].type              | Tipo de variação                                                 | Valores aceitos: select, radio, text, image    |
| variations[].name              | Nome da variação                                                 | Máx 50                                         |
| variations[].options[].value   | Valor de uma opção de variação                                   | Regras                                         |
| variations[].options[].default | Se essa opção de variação será a padrão                          | Valores aceitos: 0 ou 1                        |
| variations[].options[].file_id | Id do arquivo enviado na api de uploads para o tipo "image"      | Numérico, Id do upload de arquivo deve existir |
| variations[].maxlength         | Máximo de caracteres para tipo "text"                            | Numérico                                       |
| catalog.title                  | Título para o catálogo                                           | Máx 30                                         |
| catalog.collection             | Nome da coleção para o catálogo                                  | Máx 30                                         |
| catalog.description            | Descrição para o catálogo                                        | Máx 5.000                                      |
| catalog.price.default          | Valor padrão para o catálogo                                     | Numérico                                       |
| catalog.price.offer            | Valor de oferta para o catálogo                                  | Numérico                                       |
| catalog.file_id                | Id do arquivo enviado pela api de uploads para o catálogo        | Id do upload de arquivo deve existir           |
| has_stock                      | Se tem pronta entrega                                            | Valores aceitos: 0 ou 1                        |
| is_featured                    | Se é um produto em destaque                                      | Valores aceitos: 0 ou 1                        |
| is_automated                   | Se o produto vai participar da automatização de e-mail marketing | Valores aceitos: 0 ou 1                        |
| is_active                      | Se o produto está ativo                                          | Valores aceitos: 0 ou 1                        |

Fique atento na hora de enviar as opções das variações já que elas podem ser diferentes dependendo do `type` escolhido.

No `Body` acima tem os 4 tipos de variação como exemplo.

Como você pode ver no `Body` do `json` você pode enviar vários `file_id`. Esses número deve ser de um `id` existente que você pode enviar através do [endpoint de uploads](/api-docs/uploads/create/).

## Response

_http status code 201_

```json
{
  "data": {
    "id": 11,
    "code": "CODE12",
    "name": "Nome do produto",
    "average_weight": 1.85,
    "price": {
      "default": 1580.95
    },
    "category": {
      "id": 1,
      "client_id": 1,
      "parent_id": null,
      "_lft": 1,
      "_rgt": 10,
      "slug": "notebooks",
      "name": "Notebooks",
      "description": "",
      "is_active": 1,
      "permission_id": 90,
      "created_at": "2019-09-02 15:18:54",
      "updated_at": "2019-09-02 15:18:54",
      "deleted_at": null
    },
    "images": [
      {
        "id": 17,
        "path": "https://app.pedidosdigitais.com.br/storage/uploads/1/products/500x500/2019-06-28-164720-9.jpg",
        "default": 0
      },
      {
        "id": 18,
        "path": "https://app.pedidosdigitais.com.br/storage/uploads/1/products/500x500/2019-06-28-164720-1-7.jpg",
        "default": 1
      },
      {
        "id": 19,
        "path": "https://app.pedidosdigitais.com.br/storage/uploads/1/products/500x500/2019-06-28-164720-2-7.jpg",
        "default": 0
      }
    ],
    "video": "https://www.youtube.com/watch?v=KG54us1diCw",
    "description": {
      "text": "text description",
      "html": "html description"
    },
    "variations": [
      {
        "type": "select",
        "slug": "cor",
        "name": "Cor",
        "options": ["Azul", "*Amarelo", "Vermelho"]
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
        "options": [50]
      },
      {
        "type": "image",
        "slug": "textura",
        "name": "Textura",
        "options": [
          {
            "value": "Textura 1",
            "path": "/storage/uploads/1/products/variations/300x300/2019-06-28-164720-47.jpg"
          },
          {
            "value": "Textura 2",
            "path": "/storage/uploads/1/products/variations/300x300/2019-06-28-164720-1-34.jpg"
          },
          {
            "value": "Textura 3",
            "path": "/storage/uploads/1/products/variations/300x300/2019-06-28-164720-7-34.jpg"
          }
        ]
      }
    ],
    "catalog": {
      "is_catalog": 0,
      "title": "Teste",
      "collection": "2018",
      "description": "Descrição de teste",
      "price": {
        "default": 29.9,
        "offer": 19.95
      },
      "image": "https://app.pedidosdigitais.com.br/storage/uploads/1/catalog/500x500/2019-06-28-164720-4-22.jpg"
    },
    "has_stock": 1,
    "is_featured": 0,
    "is_automated": 0,
    "is_active": 1,
    "created_at": "2019-09-13 16:52:09",
    "updated_at": "2019-09-13 16:52:09",
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
