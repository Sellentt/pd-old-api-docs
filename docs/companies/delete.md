Remove um cliente.

**Endpoint**

```
DELETE "https://app.pedidosdigitais.com.br/api/v2/companies/{id}"
```

| Params | Description |
|---|---|
| id | Id do cliente que será removido |

**Headers**

```
"Authorization": "Bearer TOKEN"
```

**Response**

*http status code 200*

```
empty
```

**Errors**

Token não enviado

*Http status code 401*

```json
{
  "error": "Token not found."
}
```

Token inválido

*Http status code 401*

```json
{
  "error": "Invalid token."
}
```

Cliente não encontrado.

*Http status code 404*

```json
{
  "error": "Company not found."
}
```

Erro interno do servidor

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
