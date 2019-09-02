Detalhes de uma loja.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/stores/{id}"
```

| Params | Description |
|---|---|
| id | Id da loja |

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
    "name": "Apple Store NYC",
    "company_name": "",
    "doc_type": "cpf",
    "doc_number": "000.000.000-00",
    "reg_number": "",
    "address_street": "",
    "address_number": "",
    "address_more": "",
    "address_zipcode": "",
    "address_district": "",
    "address_city": "",
    "address_state": "",
    "address_street_delivery": "",
    "address_number_delivery": "",
    "address_more_delivery": "",
    "address_zipcode_delivery": "",
    "address_district_delivery": "",
    "address_city_delivery": "",
    "address_state_delivery": "",
    "phone_number_1": "",
    "phone_number_2": "",
    "mobile_number_1": "",
    "mobile_number_2": "",
    "email_1": "",
    "email_2": "",
    "created_at": "2019-08-26 08:36:57",
    "updated_at": "2019-08-26 10:37:58",
    "company": {
      "id": 1,
      "code": "1020",
      "name": "Apple Inc."
    },
    "agents": [
      {
        "id": 12 ,
        "name": "John Due"
      }
    ]
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

**Loja não encontrada**

*Http status code 404*

```json
{
  "error": "Store not found."
}
```

**Erro interno do servidor**

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```
