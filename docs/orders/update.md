Altera alguns dados de um pedido.

## Endpoint

```
PUT "https://app.pedidosdigitais.com.br/api/v2/orders/{code}"
```

| Params | Description      |
| ------ | ---------------- |
| code   | Código do pedido |

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

```json
{
  "status_id": "1",
  "buyer_email": "func_a2@livepixel.com.br",
  "address_zipcode": "14096-180",
  "address_street": "Avenida",
  "address_number": "11",
  "address_more": "10-12",
  "address_district": "Centro",
  "address_city": "Ribeirão Preto",
  "address_state": "SP",
  "transport_company_id": "2",
  "address_zipcode_delivery": "14096-180",
  "address_street_delivery": "Avenida",
  "address_number_delivery": "11",
  "address_more_delivery": "10-12",
  "address_district_delivery": "Centro",
  "address_city_delivery": "Ribeirão Preto",
  "address_state_delivery": "SP",
  "tracking_code": "BR521452147",
  "obs": "Por favor confirmar se tem todos os produtos"
}
```

| Field                     | Description                              | Rules                                                                 |
| ------------------------- | ---------------------------------------- | --------------------------------------------------------------------- |
| status_id                 | Id de um status existente.               | Deve ser um id de status existente.                                   |
| buyer_email               | E-mail do comprador.                     | E-mail válido.                                                        |
| address_zipcode           | Cep do endereço de cobrança.             | Obrigatório, Padrão 99999-999                                         |
| address_street            | Logradouro do endereço de cobrança.      | Obrigatório, mín 2 e máx 100.                                         |
| address_number            | Número do endereço de cobrança.          | Obrigatório, máx 20.                                                  |
| address_more              | Complemento do endereço de cobrança.     | Máx 100.                                                              |
| address_district          | Bairro do endereço de cobrança.          | Mín 2, máx 100.                                                       |
| address_city              | Cidade do endereço de cobrança.          | Obrigatório. Mín 2 e máx 100.                                         |
| address_state             | Sigla do estado do endereço de cobrança. | Obrigatório, deve ser uma sigla válida.                               |
| transport_company_id      | Id de uma transportadora cadastrada.     | Obrigatório caso for configurado no painel. Deve ser um id existente. |
| address_zipcode_delivery  | Cep do endereço de entrega.              | Obrigatório, Padrão 99999-999                                         |
| address_street_delivery   | Logradouro do endereço de entrega.       | Obrigatório, mín 2 e máx 100.                                         |
| address_number_delivery   | Número do endereço de entrega.           | Obrigatório, máx 20.                                                  |
| address_more_delivery     | Complemento do endereço de entrega.      | Máx 100.                                                              |
| address_district_delivery | Bairro do endereço de cobrança.          | Mín 2, máx 100.                                                       |
| address_city_delivery     | Cidade do endereço de cobrança.          | Obrigatório. Mín 2 e máx 100.                                         |
| address_state_delivery    | Sigla do estado do endereço de cobrança. | Obrigatório, deve ser uma sigla válida.                               |
| tracking_code             | Código de rastreio da transportadora.    | Máx 50.                                                               |
| obs                       | Observações do pedido.                   | Máx 10.000.                                                           |

## Response

_http status code 200_

```json
{
  "data": {
    "code": 2,
    "doc_type": "cpf",
    "doc_number": "05248763854",
    "reg_number": "526685412",
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

**Status do pedido não encontrado**

_Http status code 404_

```json
{
  "error": "Order not found."
}
```

**Erros nos dados enviados**

_Http status code 422_

```json
{
  "error": "Unprocessable Entity",
  "invalid_fields": {
    "field1": "Error message 1.",
    "field1": "Error message 2.",
    "field1": "Error message 3."
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
