Altera uma nova categoria.

**Endpoint**

```
PUT "https://app.pedidosdigitais.com.br/api/v2/categories/{id}"
```

| Params | Description |
|---|---|
| id | Id da categoria que será alterada |

**Headers**

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

**Body**

```json
{
	"parent_id": 3, 
	"name": "Minha categoria", 
	"is_active": 1
}
```

| Field | Description | Rules |
|---|---|---|
| parent_id | Id de uma categoria pai | |
| name (*required*) | Nome da categoria | Min 2, max 50 |
| is_active (*required*) | Status da categoria | 0 ou 1 |


**Response**

*http status code 200*


```json
{
  "data": {
    "id": 1,
    "parent_id": 3,
    "name": "Minha categoria pai",
    "is_active": 1
  }
}
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

Categoria não encontrada

*Http status code 404*

```json
{
  "error": "Category not found."
}
```

Erros nos dados enviados

*Http status code 422*


```json
{
  "error": "Unprocessable Entity",
  "invalid_fields": {
    "parent_id": "The selected parent id is invalid.",
    "name": "The name field is required.",
    "is_active": "The is active field is required."
  }
}
```

Erro interno do servidor

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
