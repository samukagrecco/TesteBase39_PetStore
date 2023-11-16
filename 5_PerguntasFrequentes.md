# Perguntas frequentes

Todas perguntas importam! Por isso, selecionamos cinco perguntas recorrentes relacionadas à API Petstore.

---- 
**Pergunta**: Como faço para obter acesso à API Petstore?

**Resposta**: Para obter acesso à API Petstore, você precisa registrar sua loja em nossa plataforma. Isso fornecerá as credenciais de autenticação necessárias para começar a usar a API, como chaves de acesso e nome de usuário. Confira o tópico [Introdução > Primeiros passos](#Primeiros-passos).

---- 
**Pergunta**: Quais são os endpoints da API?

**Resposta**: 
Esta API contém três objetos com os seguintes endpoints:

`PET`

| Método | Endpoint                 |
| ------ | ------------------------ |
| PUT    | /pet                     |
| POST   | /pet                     |
| GET    | /pet/findByStatus        |
| GET    | /pet/findByTags          |
| GET    | /pet/{petId}             |
| POST   | /pet/{petId}             |
| DELETE | /pet/{petId}             |
| POST   | /pet/{petId}/uploadImage |

`STORE`

| Método | Endpoint               |
| ------ | ---------------------- |
| GET    | /store/inventory       |
| POST   | /store/order           |
| GET    | /store/order/{orderId} |
| DELETE | /store/order/{orderId} |

`USER`

| Método | Endpoint             |
| ------ | -------------------- |
| POST   | /user                |
| POST   | /user/createWithList |
| GET    | /user/login          |
| GET    | /user/logout         |
| GET    | /user/{username}     |
| PUT    | /user/{username}     |
| DELETE | /user/{username}     |


Confira o tópico [Introdução](#Introdução) para descrições detalhadas de cada objeto e endpoint.

---- 
**Pergunta**: Quais são os passos para iniciar um pedido para um cliente por meio da API?

**Resposta**: Para iniciar um pedido, você deve enviar uma solicitação `POST` para o endpoint `/store/order`, fornecendo os detalhes relevantes, como:
- ID do pedido
- ID do animal
- Quantidade
- Data de expedição
- Status do pedido
- Se o pedido está completo

Confira o tópico [Objeto STORE > POST/store/order](#POST-store-order).

---- 
**Pergunta**: Como é possível visualizar um pedido feito por meio da API?

**Resposta**: É possível visualizar os pedidos realizados fazendo uma solicitação `GET` para o endpoint `/store/order/orderId`, indicando o número do pedido. Isso retornará detalhes relevantes, como:
- ID do pedido
- ID do animal
- Quantidade
- Data de expedição
- Status do pedido
- Se o pedido está completo

Confira o tópico [Objeto STORE > GET/store/order/orderId](#GET-store-order-orderId).

---- 
**Pergunta**: O uso da API é gratuito?

**Resposta**: Existem duas opções de uso: gratuita e paga, com diferentes limitações e recursos. Confira o tópico [Taxas de limite](#Taxas-de-limite).
