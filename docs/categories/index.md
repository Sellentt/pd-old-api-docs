Lista as categorias de um cliente.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/categories"
```

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

*http status code 200*

```json
{
  "data": [
    {
      "id": 1,
      "parent_id": null,
      "name": "Notebooks"
    },
    {
      "id": 2,
      "parent_id": 1,
      "name": "Samsung"
    },
    {
      "id": 3,
      "parent_id": null,
      "name": "Acessórios"
    },
    {
      "id": 4,
      "parent_id": 3,
      "name": "SSD"
    }
  ],
  "links": {
    "first": "https://app.pedidosdigitais.com.br/api/v2/categories?page=1",
    "last": "https://app.pedidosdigitais.com.br/api/v2/categories?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "https://app.pedidosdigitais.com.br/api/v2/categories",
    "per_page": 20,
    "to": 4,
    "total": 4
  }
}
```

# Errors

**Token não enviado**

*Http status code 401*

```json
{
  "error": "Token not found."
}
```

**Token inválido**

*Http status code 401*

```json
{
  "error": "Invalid token."
}
```

**Erro interno do servidor**

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
