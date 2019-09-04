Envia um novo arquivo de imagem.

**Atenção:** Ao enviar uma imagem você receberá um `id` como resposta. Guarde este `id` pois é ele que deverá ser enviado nos outros `endpoints` que necessitem de imagem.

**Importante:** As imagens enviadas para este endpoint estarão disponíveis por 7 dias para serem usadas nos outros recursos desta API.

## Endpoint

```
POST "https://app.pedidosdigitais.com.br/api/v2/uploads"
```

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "multipart/form-data"
```

## Body

| Field             | Description       | Rules                                   |
| ----------------- | ----------------- | --------------------------------------- |
| file (_required_) | Arquivo da imagem | Extensões jpg, jpeg, png - Máximo 15 MB |

## Response

_http status code 201_

```json
{
  "data": {
    "id": 1,
    "file": "/storage/uploads/{id}/imported/filename.ext"
  }
}
```

| Field | Description                                                    |
| ----- | -------------------------------------------------------------- |
| id    | Id do arquivo                                                  |
| file  | Caminha público do arquivo. {id} é um código interno (integer) |

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

**Erros nos dados enviados**

_Http status code 422_

```json
{
  "error": "Unprocessable Entity",
  "invalid_fields": {
    "field1": "Error message",
    "field2": "Error message",
    "field3": "Error message"
  }
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
