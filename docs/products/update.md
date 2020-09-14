Adiciona um novo produto.

## Endpoint

```
PUT "https://app.pedidosdigitais.com.br/api/v2/products/{id}"
```

| Params | Description                     |
| ------ | ------------------------------- |
| id     | Id do produto que será alterado |

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
  "stock": 500.00,
  "price": {
    "default": 1580.95
  },
  "category_id": 1,
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
          "path": "/storage/uploads/1/products/variations/300x300/azul.png"
        },
        {
          "value": "Textura 3",
          "file_id": 1
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
    "file_id": 1
  },
  "has_stock": 1,
  "is_featured": 0,
  "is_automated": 0,
  "is_active": 1
}
```

| Field                          | Description                                                                | Rules                                          |
| ------------------------------ | -------------------------------------------------------------------------- | ---------------------------------------------- |
| code                           | Código do produto                                                          | Obrigatório, mín 3, máx 30, único              |
| name                           | Nome do produto                                                            | Obrigatório, mín 2, máx 150                    |
| average_weight                 | Peso médio do produto                                                      | Numérico, min 0.01, máx 10000000               |
| stock                          | Estoque disponível do produto                                              | Numérico, min 0.01
| price.default                  | Valor do produto                                                           | Obrigatório, numérico, máx 10000000            |
| category_id                    | Id da categoria do produto                                                 | Obrigatório, numérico, Id deve existir         |
| video                          | Vídeo do produto                                                           | Link youtube, máx 200                          |
| description.text               | Descrição em texto simples                                                 | Máx 250                                        |
| description.html               | Descrição em html                                                          |                                                |
| variations[].type              | Tipo de variação                                                           | Valores aceitos: select, radio, text, image    |
| variations[].name              | Nome da variação                                                           | Máx 50                                         |
| variations[].options[].value   | Valor de uma opção de variação                                             | Regras                                         |
| variations[].options[].default | Se essa opção de variação será a padrão                                    | Valores aceitos: 0 ou 1                        |
| variations[].options[].file_id | Id do arquivo enviado na api de uploads para o tipo "image"                | Numérico, Id do upload de arquivo deve existir |
| variations[].options[].path    | Caso não queira mudar a foto dessa opção de variação envie o mesmo caminho | Obrigatório caso não envie um novo `file_id`   |
| variations[].maxlength         | Máximo de caracteres para tipo "text"                                      | Numérico                                       |
| catalog.title                  | Título para o catálogo                                                     | Máx 30                                         |
| catalog.collection             | Nome da coleção para o catálogo                                            | Máx 30                                         |
| catalog.description            | Descrição para o catálogo                                                  | Máx 5.000                                      |
| catalog.price.default          | Valor padrão para o catálogo                                               | Numérico                                       |
| catalog.price.offer            | Valor de oferta para o catálogo                                            | Numérico                                       |
| catalog.file_id                | Id do arquivo enviado pela api de uploads para o catálogo                  | Id do upload de arquivo deve existir           |
| has_stock                      | Se tem pronta entrega                                                      | Valores aceitos: 0 ou 1                        |
| is_featured                    | Se é um produto em destaque                                                | Valores aceitos: 0 ou 1                        |
| is_automated                   | Se o produto vai participar da automatização de e-mail marketing           | Valores aceitos: 0 ou 1                        |
| is_active                      | Se o produto está ativo                                                    | Valores aceitos: 0 ou 1                        |

Fique atento na hora de enviar as opções das variações já que elas podem ser diferentes dependendo do `type` escolhido.

No `Body` acima tem os 4 tipos de variação como exemplo.

Como você pode ver no `Body` do `json` você pode enviar vários `file_id`. Esses número deve ser de um `id` existente que você pode enviar através do [endpoint de uploads](/api-docs/uploads/create/).

## Imagens do produto

As imagens do produto são gerenciadas a partir de um conjunto de [endpoints específicos para gerenciamento de imagens](#link).

## Response

_http status code 201_

```json
{
  "data": {
    "id": 13,
    "code": "CODE512",
    "name": "Nome do produto",
    "average_weight": 1.85,
    "stock": 500.00,
    "price": {
      "default": 1580.95
    },
    "category": {
      "id": 1,
      "name": "Notebooks"
    },
    "images": [
      {
        "id": 36,
        "path": "https://app.pedidosdigitais.com.br/storage/uploads/1/products/500x500/2019-06-28-164720.jpg",
        "default": 0
      },
      {
        "id": 38,
        "path": "https://app.pedidosdigitais.com.br/storage/uploads/1/products/500x500/2019-06-28-164720-4.jpg",
        "default": 1
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
            "path": "/storage/uploads/1/products/variations/300x300/2019-06-28-164720-180.jpg"
          },
          {
            "value": "Textura 2",
            "path": "/storage/uploads/1/products/variations/300x300/2019-06-28-164720-181.jpg"
          },
          {
            "value": "Textura 3",
            "path": "/storage/uploads/1/products/variations/300x300/2019-06-28-164720-182.jpg"
          }
        ]
      }
    ],
    "catalog": {
      "is_catalog": 1,
      "title": "Teste",
      "collection": "2018",
      "description": "Descrição de teste",
      "price": {
        "default": 29.9,
        "offer": 19.95
      },
      "image": "https://app.pedidosdigitais.com.br/storage/uploads/1/catalog/500x500/2019-06-28-164720-29.jpg"
    },
    "has_stock": 1,
    "is_featured": 0,
    "is_automated": 0,
    "is_active": 1,
    "created_at": "2019-09-17 14:36:13",
    "updated_at": "2019-09-18 14:54:01",
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
