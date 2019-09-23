Remove uma variação precificada de um produto.

## Endpoint

```
DELETE "https://app.pedidosdigitais.com.br/api/v2/products/{id}/variations/{variation_id}"
```

| Params       | Description                |
| ------------ | -------------------------- |
| id           | Id do produto              |
| variation_id | Id da variação precificada |

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

**Variação não encontrada**

_Http status code 404_

```json
{
  "error": "Variation not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
