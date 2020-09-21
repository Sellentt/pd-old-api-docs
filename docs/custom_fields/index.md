Listar os campos personalizados de um cliente.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/custom_fields"
```

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
    "first": "https://app.pedidosdigitais.com.br/api/v2/custom_fields?page=1",
    "last": "https://app.pedidosdigitais.com.br/api/v2/custom_fields?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "https://app.pedidosdigitais.com.br/api/v2/custom_fields",
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
