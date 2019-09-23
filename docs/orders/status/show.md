Detalhes de um status de pedido.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/orders/status/{id}"
```

| Params | Description  |
| ------ | ------------ |
| id     | Id do status |

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

_http status code 200_

```json
{
  "data": {
    "id": 1,
    "name": "Aguardando Pagto.",
    "color": "#EEEEEE",
    "is_active": 1,
    "created_at": "2019-09-06 11:10:50",
    "updated_at": "2019-09-23 16:15:57"
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
