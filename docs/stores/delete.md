Remove uma nova categoria.

## Endpoint

```
DELETE "https://app.pedidosdigitais.com.br/api/v2/stores/{id}"
```

| Params | Description                  |
| ------ | ---------------------------- |
| id     | Id da loja que será removida |

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

**Categoria não encontrada**

_Http status code 404_

```json
{
  "error": "Store not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
