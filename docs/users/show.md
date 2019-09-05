Detalhes de um usuário.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/users/{id}"
```

| Params | Description   |
| ------ | ------------- |
| id     | Id do usuário |

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

_http status code 200_

```json
{
  "data": {
    "id": 5,
    "name": "Funcionário Loja 1",
    "email": "func1@domain.com.br",
    "type": "seller",
    "is_active": 1,
    "created_at": "2019-09-05 09:11:22",
    "updated_at": "2019-09-05 09:11:22",
    "group": {
      "id": 1,
      "name": "Lojista Padrão"
    },
    "company": {
      "id": 1,
      "name": "Total Tech"
    }
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

**Usuário não encontrado**

_Http status code 404_

```json
{
  "error": "User not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
