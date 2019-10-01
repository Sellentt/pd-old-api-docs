Listar os pedidos por padrão em ordem decrescente.

## Endpoint

```
GET "https://app.pedidosdigitais.com.br/api/v2/orders"
```

## Params

| Field | Description                                                                                                          |
| ----- | -------------------------------------------------------------------------------------------------------------------- |
| order | Campo para ordenação dos pedidos. Por data de criação (created) ou por data de atualização (updated)                 |
| sort  | Tipo de ordenação dos pedidos de acordo com a coluna passada acima (Pode ser `asc` e `desc`)                         |
| after | Data no padrão YYYY-MM-DDTHH:MM:SS. Exemplo: 2019-09-27T08:29:00. Busca pedidos alterados dessa data/hora em diante. |

## Headers

```
"Authorization": "Bearer TOKEN"
```

## Response

_http status code 200_

```json
{
  "data": [
    {
      "code": 2,
      "doc_type": "cpf",
      "doc_number": "72585412369",
      "reg_number": "322222222",
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
      "address_zipcode": "14000-123",
      "address_district": "Centro",
      "address_city": "Ribeirão Preto",
      "address_state": "SP",
      "address_street_delivery": "Avenida",
      "address_number_delivery": "11",
      "address_more_delivery": "10-12",
      "address_zipcode_delivery": "14000-123",
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
    },
    {
      "code": 1,
      "doc_type": "cpf",
      "doc_number": "",
      "reg_number": "",
      "amount": "2395.20",
      "tracking_code": null,
      "buyer_id": 48,
      "buyer_name": "Rodrigo / Nome do lojista 123",
      "buyer_email": "func_a2@livepixel.com.br",
      "buyer_phone_number": "55555555555",
      "buyer_mobile_number": "55555555555",
      "address_street": "Avenida Xpto",
      "address_number": "400",
      "address_more": "17-500",
      "address_zipcode": "14000-180",
      "address_district": "Ribeirânia",
      "address_city": "Ribeirão Preto",
      "address_state": "SP",
      "address_street_delivery": "Avenida Xpto",
      "address_number_delivery": "3905",
      "address_more_delivery": "17-500",
      "address_zipcode_delivery": "14000-180",
      "address_district_delivery": "Ribeirânia",
      "address_city_delivery": "Ribeirão Preto",
      "address_state_delivery": "SP",
      "phone_number": "",
      "mobile_number": "",
      "obs": "",
      "payment_method_id": null,
      "payment_method_rules": null,
      "payment_diff_price": "0.00",
      "created_at": "2019-09-27 08:29:02",
      "updated_at": "2019-09-27 08:29:02",
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
          "code": "CODE6",
          "name": "Produto CODE 6",
          "variations": [
            {
              "name": "a",
              "value": "Amarelo"
            },
            {
              "name": "b",
              "value": "Eclipse"
            },
            {
              "name": "c",
              "value": "te"
            },
            {
              "name": "d",
              "value": "x"
            }
          ],
          "quantity": 1,
          "unit_price": "521.45",
          "notes": ""
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Azul"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": ""
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Vermelho"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": ""
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Verde"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": ""
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Azul"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "a"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Azul"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "b"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Azul"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "c"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Azul"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "d"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Vermelho"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "a"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Vermelho"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "b"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Vermelho"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "c"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Vermelho"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "d"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Verde"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "a"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Verde"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "b"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Verde"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "c"
        },
        {
          "code": "1021",
          "name": "Produto Simples",
          "variations": [
            {
              "name": "Cor",
              "value": "Verde"
            }
          ],
          "quantity": 1,
          "unit_price": "19.52",
          "notes": "d"
        }
      ],
      "transport_company": null
    }
  ],
  "links": {
    "first": "https://app.pedidosdigitais.com.br/api/v2/orders?page=1",
    "last": "https://app.pedidosdigitais.com.br/api/v2/orders?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "https://app.pedidosdigitais.com.br/api/v2/orders",
    "per_page": 20,
    "to": 2,
    "total": 2
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

**Erro interno do servidor**

_Http status code 500_

```json
{
  "error": "Internal Server Error"
}
```
