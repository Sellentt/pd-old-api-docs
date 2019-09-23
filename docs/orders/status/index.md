Listar os status dos pedidos.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/orders/status"
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
      "name": "Recebido",
      "color": "#808080",
      "is_active": 1,
      "created_at": "2019-09-06 11:10:50",
      "updated_at": "2019-09-23 15:53:28"
    },
    {
      "id": 3,
      "name": "Aguardando Pagto.",
      "color": "#EEEEEE",
      "is_active": 1,
      "created_at": "2019-09-23 16:12:53",
      "updated_at": "2019-09-23 16:12:53"
    }
  ]
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
