Detalhes de um campo personalizado.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/custom_fields/{id}"
```

| Params | Description   |
| ------ | ------------- |
| id     | Id do campo personalizado |

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
        "created_at": "2020-09-09 15:54:44",
        "updated_at": "2020-09-09 16:19:27",
        "deleted_at": ""
    },
    "_debugbar": {
        "querys": {
            "nb_statements": 1,
            "nb_failed_statements": 0,
            "accumulated_duration": 0.04375,
            "accumulated_duration_str": "43.75ms",
            "statements": [
                {
                    "sql": "select * from `product_custom_fields` where `id` = '8' and `client_id` = 1 and `product_custom_fields`.`deleted_at` is null limit 1",
                    "type": "query",
                    "params": [],
                    "bindings": [
                        "8",
                        "1"
                    ],
                    "hints": [
                        "Use <code>SELECT *</code> only if you need all columns from table",
                        "<code>LIMIT</code> without <code>ORDER BY</code> causes non-deterministic results, depending on the query execution plan"
                    ],
                    "backtrace": [],
                    "duration": 0.04375,
                    "duration_str": "43.75ms",
                    "stmt_id": "",
                    "connection": "pedidos_digitais"
                }
            ]
        }
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

**Campo não encontrado**

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
