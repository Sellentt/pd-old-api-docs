Adiciona um novo campo personalizado.

## Endpoint

```
POST "https://app.pedidosdigitais.com.br/api/v2/custom_fields"
```

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
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
```

| Field                          | Description                                                      | Rules                                          |
| ------------------------------ | ---------------------------------------------------------------- | ---------------------------------------------- |
| custom_field_type              | Tipo do campo (informação adicional ou ficha técnica)            | Obrigatório, Valores aceitos: tecnical_sheet ou additional_info
| type                           | Tipo do campo (seleção ou texto)                                 | Obrigatório, Valores aceitos: select, radio ou text
| options                        | Opções para um campo do tipo seleção                             | Obrigatório
| name                           | Nome do campo                                                    | Obrigatório, mín 2, máx 150                    |                    |
| max_length                     | Número máximo de caracteres para um campo do tipo texto          | Númerico
| is_mandatory                   | Se o campo é obrigatório                                         | Valores aceitos: 0 ou 1                        |
| is_active                      | Se o campo está ativo                                            | Valores aceitos: 0 ou 1                        |

## Response

_http status code 201_

```json
{
    "data": {
        "id": 9,
        "client_id": 1,
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
        "created_at": "2020-09-10 14:52:39",
        "updated_at": "2020-09-10 14:52:39",
        "deleted_at": ""
    },
    "_debugbar": {
        "querys": {
            "nb_statements": 4,
            "nb_failed_statements": 0,
            "accumulated_duration": 0.08835,
            "accumulated_duration_str": "88.35ms",
            "statements": [
                {
                    "sql": "select count(*) as aggregate from `api_tokens` where `id` = 1 and `client_id` = 1",
                    "type": "query",
                    "params": [],
                    "bindings": [
                        "1",
                        "1"
                    ],
                    "hints": [],
                    "backtrace": [],
                    "duration": 0.07872,
                    "duration_str": "78.72ms",
                    "stmt_id": "",
                    "connection": "pedidos_digitais"
                },
                {
                    "sql": "insert into `product_custom_fields` (`client_id`, `custom_field_type`, `name`, `type`, `options`, `is_active`, `is_mandatory`, `updated_at`, `created_at`) values (1, 'technical_sheet', 'Quantidade de Memória RAM', 'select', '[\\\"10\\\",\\\"15\\\",\\\"20\\\"]', 1, 1, '2020-09-10 14:52:39', '2020-09-10 14:52:39')",
                    "type": "query",
                    "params": [],
                    "bindings": [
                        "1",
                        "technical_sheet",
                        "Quantidade de Mem&oacute;ria RAM",
                        "select",
                        "[&quot;10&quot;,&quot;15&quot;,&quot;20&quot;]",
                        "1",
                        "1",
                        "2020-09-10 14:52:39",
                        "2020-09-10 14:52:39"
                    ],
                    "hints": [],
                    "backtrace": [],
                    "duration": 0.004900000000000001,
                    "duration_str": "4.9ms",
                    "stmt_id": "",
                    "connection": "pedidos_digitais"
                },
                {
                    "sql": "select * from `product_custom_fields` where `id` = 9 limit 1",
                    "type": "query",
                    "params": [],
                    "bindings": [
                        "9"
                    ],
                    "hints": [
                        "Use <code>SELECT *</code> only if you need all columns from table",
                        "<code>LIMIT</code> without <code>ORDER BY</code> causes non-deterministic results, depending on the query execution plan"
                    ],
                    "backtrace": [],
                    "duration": 0.00082,
                    "duration_str": "820μs",
                    "stmt_id": "",
                    "connection": "pedidos_digitais"
                },
                {
                    "sql":"insert into `activity_log` (`log_name`, `properties`, `subject_id`, `subject_type`, `description`, `updated_at`, `created_at`) values ('default', '{\\\"attributes\\\":{\\\"type\\\":\\\"select\\\",\\\"name\\\":\\\"Quantidade de Mem\ória RAM\\\",\\\"options\\\":[\\\"10\\\",\\\"15\\\",\\\"20\\\"],\\\"is_active\\\":1,\\\"is_mandatory\\\":1}}', 9, 'App\\Models\\ProductCustomFields', 'created', '2020-09-10 14:52:40', '2020-09-10 14:52:40')",
                    "type": "query",
                    "params": [],
                    "bindings": [
                        "default","{&quot;attributes&quot;:{&quot;type&quot;:&quot;select&quot;,&quot;name&quot;:&quot;Quantidade de Mem\ória RAM&quot;,&quot;options&quot;:[&quot;10&quot;,&quot;15&quot;,&quot;20&quot;],&quot;is_active&quot;:1,&quot;is_mandatory&quot;:1}}",
                        "9",
                        "App\\Models\\ProductCustomFields",
                        "created",
                        "2020-09-10 14:52:40",
                        "2020-09-10 14:52:40"
                    ],
                    "hints": [],
                    "backtrace": [],
                    "duration": 0.00391,
                    "duration_str": "3.91ms",
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
