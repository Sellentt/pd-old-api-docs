Adiciona um novo usuário.

## Endpoint

```
POST "https://app.pedidosdigitais.com.br/api/v2/users/{id}"
```

| Params | Description   |
| ------ | ------------- |
| id     | Id do usuário |

## Headers

```
"Authorization": "Bearer TOKEN"
"Content-Type": "application/json"
```

## Body

Existem 3 tipos de usuários que você pode alterar no Pedidos Digitais. Na tabela abaixo você encontra cada um destes tipos e uma explicação sobre cada um deles.

| Type    | Description                                                                                                   |
| ------- | ------------------------------------------------------------------------------------------------------------- |
| regular | Usuário padrão que terá acesso ao painel de controle                                                          |
| agent   | Usuário representante, terá acesso ao painel como um usuário regular e também tem acesso via app para celular |
| seller  | Usuário lojista que terá acesso a loja virtual                                                                |

Existe uma pequena diferença no `payload` enviado dependendo do `type` que você enviar.

**Para usuários com type: regular | agent**

```json
{
  "type": "regular",
  "name": "John Due",
  "group_id": 17,
  "phone_number": "11555555555",
  "mobile_number": "11555555555",
  "email": "email@domain.com",
  "change_password": 1,
  "password": "secret",
  "send_credentials": 1,
  "is_active": 1
}
```

| Field                 | Description               | Rules                                                                                |
| --------------------- | ------------------------- | ------------------------------------------------------------------------------------ |
| type (_required_)     | Tipo de usuário           | regular, agent, seller                                                               |
| name (_required_)     | Nome do usuário           | min 2, máx 50                                                                        |
| group_id (_required_) | Id do grupo deste usuário | Numérico e deve ser o id de um grupo existente e do mesmo tipo do usuário cadastrado |
| phone_number          | Telefone do usuário       | min 10, máx 11                                                                       |
| mobile_number         | Celular do usuário        | min 10, máx 11                                                                       |
| email (_required_)    | E-mail / Login do usuário | Deve ser um e-mail válido e único                                                    |
| change_password       | Se quer mudar a senha     | 0 = Não, 1 = Sim                                                                     |
| password              | Senha                     | min 6, máx 20 - Obrigatório se change_password for 1                                 |
| send_credentials      | Enviar credencias?        | 0 = Não, 1 = Sim                                                                     |
| is_active             | Usuário ativado?          | 0 = Não, 1 = Sim                                                                     |

**Para usuários com type: seller**

```json
{
  "type": "seller",
  "name": "John Due",
  "company_id": 85,
  "phone_number": "11555555555",
  "mobile_number": "11555555555",
  "email": "email@domain.com",
  "change_password": 1,
  "password": "secret",
  "send_credentials": 1,
  "automation_subscribe": 1,
  "is_active": 1
}
```

| Field                   | Description                        | Rules                                                |
| ----------------------- | ---------------------------------- | ---------------------------------------------------- |
| type (_required_)       | Tipo de usuário                    | regular, agent, seller                               |
| name (_required_)       | Nome do usuário                    | min 2, máx 50                                        |
| company_id (_required_) | Id do cliente                      | Numérico e deve ser o id de um cliente existente     |
| phone_number            | Telefone do usuário                | min 10, máx 11                                       |
| mobile_number           | Celular do usuário                 | min 10, máx 11                                       |
| email (_required_)      | E-mail / Login do usuário          | Deve ser um e-mail válido e único                    |
| change_password         | Se quer mudar a senha              | 0 = Não, 1 = Sim                                     |
| password                | Senha                              | min 6, máx 20 - Obrigatório se change_password for 1 |
| send_credentials        | Enviar credencias?                 | 0 = Não, 1 = Sim                                     |
| automation_subscribe    | Receberá automatizações de e-mail? | 0 = Não, 1 = Sim                                     |
| is_active               | Usuário ativado?                   | 0 = Não, 1 = Sim                                     |

## Response

_http status code 201_

```json
{
  "data": {
    "id": 38,
    "name": "John Due",
    "type": "regular",
    "is_active": null,
    "created_at": "2019-09-06 15:49:46",
    "updated_at": "2019-09-06 15:49:46",
    "group": {
      "id": 123,
      "name": "Group Name"
    },
    "company": {
      "id": 456,
      "name": "Company Name"
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

**Número máximo de usuários**

_Http status code 401_

```json
{
  "error": "Max users exceeded."
}
```

**O usuário não foi encontrado**

_Http status code 401_

```json
{
  "error": "User not found."
}
```

**O grupo do usuário não foi encontrado**

_Http status code 401_

```json
{
  "error": "User group not found."
}
```

**Erros nos dados enviados**

_Http status code 422_

```json
{
  "error": "Unprocessable Entity",
  "invalid_fields": {
    "field1": "Error message.",
    "field2": "Error message.",
    "field3": "Error message."
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
