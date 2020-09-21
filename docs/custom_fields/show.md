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
  "error": "Custom Field not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
