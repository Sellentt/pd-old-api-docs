Remove uma imagem de um produto

## Endpoint

```
DELETE "https://app.pedidosdigitais.com.br/api/v2/products/{id}/images/{image_id}"
```

| Params   | Description   |
| -------- | ------------- |
| id       | Id do produto |
| image_id | Id da imagem  |

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

**Imagem não encontrada**

_Http status code 404_

```json
{
  "error": "Image not found."
}
```

**Imagem padrão não pode ser removida**

_Http status code 401_

```json
{
  "error": "Default image cannot be deleted."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
