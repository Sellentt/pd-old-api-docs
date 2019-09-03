Adiciona uma nova loja.

## Endpoint

```
PUT "https://app.pedidosdigitais.com.br/api/v2/stores/{id}"
```

| Params | Description |
|---|---|
| id | Id da loja que será alterada |

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

**Atenção:** Dependendo do `doc_type` enviado, o corpo do `json` pode mudar.

Na alteração de loja não é possível alterar o representante.

Quando o `doc_type` for `cpf`:

```json
{
	"company_id": "1",
	"doc_type" : "cpf",
	"pf_name": "Nome da pessoa", 
	"pf_doc_number": "07283570624", 
	"pf_reg_number": "325553555",
	"address_street": "Avenida 9 de Julho",
	"address_number": "2510",
	"address_more": "sala 12",
	"address_zipcode": "01234-567",
	"address_district": "Centro",
	"address_city": "São Paulo",
	"address_state": "SP",
	"address_street_delivery": "Avenida 9 de Julho",
	"address_number_delivery": "2510",
	"address_more_delivery": "sala 12",
	"address_zipcode_delivery": "01234-567",
	"address_district_delivery": "Centro",
	"address_city_delivery": "São Paulo",
	"address_state_delivery": "SP",
	"phone_number_1": "11912345678",
	"phone_number_2": "11912345678",
	"mobile_number_1" :"11912345678",
	"mobile_number_2" :"11912345678",
	"email_1": "email1@dominio.com",
	"email_2": "email2@dominio.com"
}
```

Quando o `doc_type` for `cnpj`:

```json
{
	"company_id": "1",
	"doc_type" : "cnpj",
	"pj_company_name": "Nome da empresa", 
	"pj_name": "Nome fantasia", 
	"pj_doc_number":"01144667000120", 
	"pj_reg_number": "001", 
	"address_street": "Avenida 9 de Julho",
	"address_number": "2510",
	"address_more": "sala 12",
	"address_zipcode": "01234-567",
	"address_district": "Centro",
	"address_city": "São Paulo",
	"address_state": "SP",
	"address_street_delivery": "Avenida 9 de Julho",
	"address_number_delivery": "2510",
	"address_more_delivery": "sala 12",
	"address_zipcode_delivery": "01234-567",
	"address_district_delivery": "Centro",
	"address_city_delivery": "São Paulo",
	"address_state_delivery": "SP",
	"phone_number_1": "11912345678",
	"phone_number_2": "11912345678",
	"mobile_number_1" :"11912345678",
	"mobile_number_2" :"11912345678",
	"email_1": "email1@dominio.com",
	"email_2": "email2@dominio.com"
}
```

| Field | Description | Rules |
|---|---|---|
| company_id (*required*) | Id do cliente/company | Obrigatório |
| doc_type | Tipo de documento | cpf ou cnpj |
| pf_name | Nome da loja | min 2, máx 100 |
| pf_doc_number | CPF | CPF válido |
| pf_doc_number | RG | min 2, máx 50 |
| pj_company_name | Razão social da loja | min 2, máx 100 |
| pj_name | Nome fantasia | min 2, máx 100 |
| pj_doc_number | CNPJ | CNPJ válido |
| pj_reg_number | Inscrição estadual | min 2, máx 50 |
| address_street | Endereço de cobrança | min 2, máx 100 |
| address_number | Número do endereço de cobrança | máx 20 |
| address_more | Complemento do endereço de cobrança | máx 100 |
| address_zipcode | Cep do endereço de cobrança | númérico, 99999-999 ou 99999999 |
| address_district | Bairro do endereço de cobrança | min 2, máx 100 |
| address_city | Cidade do endereço de cobrança | min 2, máx 100 |
| address_state | Estado do endereço de cobrança | Sigla UF |
| address_street_delivery | Endereço de entrega | min 2, máx 100 |
| address_number_delivery | Número do endereço de entrega | máx 20 |
| address_more_delivery | Complemento do endereço de entrega | máx 100 |
| address_zipcode_delivery | Cep do endereço de entrega | númérico, 99999-999 ou 99999999 |
| address_district_delivery | Bairro do endereço de entrega | min 2, máx 100 |
| address_city_delivery | Cidade do endereço de entrega | min 2, máx 100 |
| address_state_delivery | Estado do endereço de entrega | Sigla UF |
| phone_number_1 | Telefone 1 | min 9, máx 11 dígitos |
| phone_number_2 | Telefone 2 | min 9, máx 11 dígitos |
| mobile_number_1 | Celular 1 | min 9, máx 11 dígitos |
| mobile_number_2 | Celular 2 | min 9, máx 11 dígitos |
| email_1 | E-mail 1 | E-mail válido | 
| email_2 | E-mail 2 | E-mail válido | 

## Response

*http status code 201*

```json
{
  "data": {
    "doc_type": "cnpj",
    "name": "",
    "company_name": "",
    "doc_number": "",
    "reg_number": "",
    "address_street": "Avenida 9 de Julho",
    "address_number": "2510",
    "address_more": "sala 12",
    "address_zipcode": "01234-567",
    "address_district": "Centro",
    "address_city": "São Paulo",
    "address_state": "SP",
    "address_street_delivery": "Avenida 9 de Julho",
    "address_number_delivery": "2510",
    "address_more_delivery": "sala 12",
    "address_zipcode_delivery": "01234-567",
    "address_district_delivery": "Centro",
    "address_city_delivery": "São Paulo",
    "address_state_delivery": "SP",
    "phone_number_1": "11912345678",
    "phone_number_2": "11912345678",
    "mobile_number_1": "11912345678",
    "mobile_number_2": "11912345678",
    "email_1": "email1@dominio.com",
    "email_2": "email2@dominio.com",
    "updated_at": "2019-09-02 17:11:57",
    "created_at": "2019-09-02 17:11:57",
    "id": 7
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

**Erros nos dados enviados**

*Http status code 422*

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

*Http status code 500*

```json
{
  "error": "Internal Server Error"
}
```