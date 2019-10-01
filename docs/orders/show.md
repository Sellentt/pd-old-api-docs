Detalhes de um pedido.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/orders/{code}"
```

| Params | Description       |
| ------ | ----------------- |
| code   | Código do pedido. |

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

_http status code 200_

```json
{
  "data": {
    "code": 2,
    "doc_type": "cpf",
    "doc_number": "01452365874",
    "reg_number": "359825741",
    "amount": "1580.95",
    "tracking_code": "BR521452147",
    "buyer_id": 48,
    "buyer_name": "Rodrigo / Nome do lojista 123",
    "buyer_email": "func_a2@livepixel.com.br",
    "buyer_phone_number": "55555555555",
    "buyer_mobile_number": "55555555555",
    "address_street": "Avenida",
    "address_number": "11",
    "address_more": "10-12",
    "address_zipcode": "14096-180",
    "address_district": "Centro",
    "address_city": "Ribeirão Preto",
    "address_state": "SP",
    "address_street_delivery": "Avenida",
    "address_number_delivery": "11",
    "address_more_delivery": "10-12",
    "address_zipcode_delivery": "14096-180",
    "address_district_delivery": "Centro",
    "address_city_delivery": "Ribeirão Preto",
    "address_state_delivery": "SP",
    "phone_number": "6434112386",
    "mobile_number": "",
    "obs": "Por favor confirmar se tem todos os produtos",
    "payment_method_id": 1,
    "payment_method_rules": {
      "id": 1,
      "client_id": 1,
      "group_id": null,
      "name": "Pagamento Padrão",
      "description": "Forma de pagamento padrão para os pedidos em geral.",
      "type_diff_price": "none",
      "diff_price_percent": null,
      "is_default": 1,
      "is_active": true,
      "created_at": "2019-09-30 15:53:35",
      "updated_at": "2019-09-30 15:53:35",
      "deleted_at": null
    },
    "payment_diff_price": "0.00",
    "created_at": "2019-09-30 15:54:39",
    "updated_at": "2019-10-01 14:22:48",
    "deleted_at": null,
    "status": {
      "id": 1,
      "name": "Aguardando Pagto.",
      "color": "#087835"
    },
    "company": {
      "id": 1,
      "name": " BETÂNIA KELLY MARTINS PEREIRA"
    },
    "products": [
      {
        "code": "1234",
        "name": "Nome do produto",
        "variations": [
          {
            "name": "Cor",
            "value": "Amarelo"
          },
          {
            "name": "Tamanho",
            "value": "Pequeno"
          },
          {
            "name": "Gravura",
            "value": "teste"
          },
          {
            "name": "Textura",
            "value": "Textura 3"
          }
        ],
        "quantity": 1,
        "unit_price": "1580.95",
        "notes": ""
      }
    ],
    "transport_company": {
      "id": 2,
      "code": "5225",
      "name": "Jadlog"
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

**Pedido não encontrado**

_Http status code 404_

```json
{
  "error": "Order not found."
}
```

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
