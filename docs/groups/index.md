Lista os grupos de usuários.

## Endpoint

```
"https://app.pedidosdigitais.com.br/api/v2/users/groups"
```

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Group Types

| Type | Description | Access
|---|---|---|
| regular | Regular users | Dashboard |
| seller | Seller users | Frontend / Store |
| agent | Agent users | Dashboard |

## Response

*http status code 200*

```json
{
  "data": [
    {
      "id": 1,
      "type": "seller",
      "name": "Lojistas Classe A",
      "created_at": "2019-08-26 08:36:04",
      "updated_at": "2019-08-28 10:54:24"
    },
    {
      "id": 2,
      "type": "agent",
      "name": "Meus Representantes",
      "created_at": "2019-08-28 10:43:18",
      "updated_at": "2019-08-28 10:43:18"
    },
    {
      "id": 3,
      "type": "regular",
      "name": "Colaboradores",
      "created_at": "2019-08-28 10:53:08",
      "updated_at": "2019-08-28 10:53:08"
    },
    {
      "id": 4,
      "type": "seller",
      "name": "Lojistas Padrão",
      "created_at": "2019-08-28 10:53:52",
      "updated_at": "2019-08-28 10:53:52"
    }
  ],
  "links": {
    "first": "https://app.pedidosdigitais.com.br/api/v2/users/groups?page=1",
    "last": "https://app.pedidosdigitais.com.br/api/v2/users/groups?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "https://app.pedidosdigitais.com.br/api/v2/users/groups",
    "per_page": 20,
    "to": 4,
    "total": 4
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

**Erro interno do servidor**

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
