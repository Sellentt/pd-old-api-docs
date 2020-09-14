Listar os campos personalizados de um cliente.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/custom_fields"
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
      "custom_field_type": "technical_sheet",
      "name": "Quantidade de Memória RAM",
      "type": "select",
      "options": [
          "10",
          "15",
          "20"
      ],
      "maxlength": null,
      "is_active": 1,
      "is_mandatory": 1,
      "created_at": "2020-07-24 13:30:51",
      "updated_at": "2020-08-18 13:15:50",
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
