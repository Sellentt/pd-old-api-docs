Remove uma nova categoria.

## Endpoint

```
DELETE "https://app.pedidosdigitais.com.br/api/v2/categories/{id}"
```

| Params | Description |
|---|---|
| id | Id da categoria que será removida |

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

*http status code 200*

```
empty
```

## Errors

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

**Categoria não encontrada**

*Http status code 404*

```json
{
  "error": "Category not found."
}
```

**Erro interno do servidor**

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
