Detalhes de um cliente.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/companies/{id}"
```

| Params | Description |
|---|---|
| id | Id do cliente |

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

*http status code 200*

```json
{
  "data": {
    "id": 1,
    "code": "1020",
    "name": "Cliente 1",
    "created_at": "2019-08-26 08:36:56",
    "updated_at": "2019-08-26 08:36:56",
    "group": {
      "id": 1,
      "name": "Lojistas Classe A"
    }
  }
}
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

**Cliente não encontrado**

*Http status code 404*

```json
{
  "error": "Company not found."
}
```

**Erro interno do servidor**

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
