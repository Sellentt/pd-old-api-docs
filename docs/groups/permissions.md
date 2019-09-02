Lista as permissões separados por grupo de permissão.

## Endpoint

```
"https://app.pedidosdigitais.com.br/api/v2//users/groups/permissions"
```

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

*http status code 200*

```json
{
  "data": [
    {
      "id": 19,
      "readable_name": "E-mail Marketing",
      "permissions": [
        {
          "id": 63,
          "readable_name": "Configurar automatização"
        },
        {
          "id": 64,
          "readable_name": "Listar campanhas"
        },
        {
          "id": 65,
          "readable_name": "Criar campanhas"
        },
        {
          "id": 66,
          "readable_name": "Alterar campanhas"
        },
        {
          "id": 67,
          "readable_name": "Remover campanhas"
        }
      ]
    },
    {
      "id": 21,
      "readable_name": "Catálogo Digital",
      "permissions": [
        {
          "id": 74,
          "readable_name": "Listar Catálogos"
        },
        {
          "id": 75,
          "readable_name": "Criar Catálogos"
        },
        {
          "id": 76,
          "readable_name": "Alterar Catálogos"
        },
        {
          "id": 77,
          "readable_name": "Remover Catálogos"
        }
      ]
    }
  ]
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
