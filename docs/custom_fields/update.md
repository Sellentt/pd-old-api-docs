Altera um campo personalizado.

## Endpoint

```
PUT "https://app.pedidosdigitais.com.br/api/v2/custom_fields/{id}"
```

| Params | Description                     |
| ------ | ------------------------------- |
| id     | Id do campo personalizado que será alterado |

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
{
    "custom_field_type": "technical_sheet",
    "name": "Quantidade de Memória RAM2",
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
        "id": 8,
        "custom_field_type": "technical_sheet",
        "name": "Quantidade de Memória RAM2",
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
        "updated_at": "2020-09-10 16:56:09",
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
