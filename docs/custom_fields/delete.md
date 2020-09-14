Remove um campo personalizado.

## Endpoint

```
DELETE "https://app.pedidosdigitais.com.br/api/v2/custom_fields/{id}"
```

| Params | Description                     |
| ------ | ------------------------------- |
| id     | Id do campo personalizado que será removido |

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

**Campo não encontrado.**

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
