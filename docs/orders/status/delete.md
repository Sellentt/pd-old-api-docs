Remove um status de pedido.

## Endpoint

```
DELETE "https://app.pedidosdigitais.com.br/api/v2/orders/status/{id}"
```

| Params | Description            |
| ------ | ---------------------- |
| id     | Id do status do pedido |

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

**Status do pedido não encontrado**

_Http status code 404_

```json
{
  "error": "Order status not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
