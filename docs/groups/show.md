Detalhes de um grupo de usuários.

## Endpoint

```
"https://app.pedidosdigitais.com.br/api/v2/users/groups/{id}"
```

| Params | Description |
|---|---|
| id | Id do grupo |

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
    "type": "seller",
    "name": "Lojistas Classe A",
    "metadata": {
      "diff_price": {
        "type": "desc",
        "percent": 5
      },
      "categories": [
        {
          "id": 3,
          "name": "Acessórios"
        },
        {
          "id": 52,
          "name": "Notebooks"
        }
      ]
    },
    "created_at": "2019-08-26 08:36:04",
    "updated_at": "2019-08-28 10:54:24"
  }
}
```

| Key | Description |
|---|---|
| id | Id do grupo |
| type | Tipo do grupo (regular, seller, agent) |
| name | Nome do grupo |
| metadata.diff_price | Grupo de configurações de preço diferenciado (pode ser null)
| metadata.diff_price.type | Tipo de diferença de preço (desc, acresc)
| metadata.diff_price.percent | Porcentagem de desconto ou acréscimo |
| metadata.categories.*.id | Id da categoria |
| metadata.categories.*.name | Nome da categoria |
| created_at | Data de criação do grupo |
| updated_at | Data de alteração do grupo |

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

**Grupo não encontrado.**

*Http status code 404*

```json
{
  "error": "Group not found."
}
```

**Erro interno do servidor**

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
