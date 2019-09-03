Remove uma categoria.

## Endpoint

```
DELETE "https://app.pedidosdigitais.com.br/api/v2/categories/{id}"
```

| Params | Description                       |
| ------ | --------------------------------- |
| id     | Id da categoria que será removida |

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

_http status code 200_

```
empty
```

## Errors

**Token não enviado**

_Http status code 401_

```json
{
  "error": "Token not found."nova categoria.
}
```

**Token inválido**

_Http status code 401_

```json
{
  "error": "Invalid token."
}
```

**Categoria não encontrada**

_Http status code 404_

```json
{
  "error": "Category not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
