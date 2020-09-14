Listar os valores dos campos personalizados.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/custom_values"
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
    "id": 1,
    "product_id": 40986,
    "product_custom_field_id": 3,
    "value": "JOAO",
    "created_at": "2020-07-27 11:35:13",
    "updated_at": "2020-07-27 11:35:13",
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
