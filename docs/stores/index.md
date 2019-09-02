Lista as lojas.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/stores"
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
      "id": 1,
      "name": "Cliente 1",
      "company_name": "",
      "doc_type": "cpf",
      "doc_number": "072.835.706-24",
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
        "name": "Cliente 1"
      },
      "agents": []
    }
  ],
  "links": {
    "first": "https://app.pedidosdigitais.com.br/stores?page=1",
    "last": "https://app.pedidosdigitais.com.br/stores?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "https://app.pedidosdigitais.com.br/stores",
    "per_page": 20,
    "to": 1,
    "total": 1
  }
}
```

# Errors

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