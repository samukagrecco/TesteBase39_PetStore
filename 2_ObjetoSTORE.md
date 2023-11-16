# Objeto `STORE`
Contém informações necessárias para gerenciamento básico de pedidos da loja, como _criação_, _leitura_, _atualização_ e _exclusão_. 
## Métodos e endpoints
Esta seção define todos os métodos e endpoints do objeto `STORE`.

### `GET`/store/inventory
Retorna um inventário dos pedidos da loja, contendo status e quantidade.

**Observação**_: Este endpoint não requer parâmetros._

#### Exemplo de request
Veja a seguir um exemplo de request do endpoint `/store/inventory`:
~~~
	curl -X 'GET' \
	  'https://petstore3.swagger.io/api/v3/store/inventory' \
	  -H 'accept: application/json'
~~~
#### Exemplo de resposta
Veja a seguir um exemplo de resposta do endpoint `/store/inventory`, em caso de sucesso:
~~~
	{
	  "32": 1,
	  "sold": 3,
	  "string": 521,
	  "unavailable": 1,
	  "available1": 5,
	  "pending": 4,
	  "available": 267,
	  "active": 47,
	  "epic": 15,
	  " sold": 1,
	  "peric": 44,
	  "nbmbm": 1,
	  "not available": 1
	}
~~~
#### Código de erro

| Código HTTP | Descrição                 |
| ----------- | ------------------------- |
| 500         | Conteúdo não documentado. |

### `POST`/store/order
Cria um pedido na loja.
#### Request body

| Parâmetro | Tipo                                 | Exemplo                  | Descrição                 |
| --------- | ------------------------------------ | ------------------------ | ------------------------- |
| id        | integer ($int64)                     | 10                       | ID do pedido              |
| petId     | integer ($int64)                     | 198772                   | ID do animal              |
| quantity  | integer ($int64)                     | 7                        | Quantidade                |
| shipDate  | string ($date-time)                  | 2023-09-04T17:46:41.158Z | Data de expedição         |
| status    | string (placed, approved, delivered) | approved                 | Status do pedido          |
| complete  | boolean                              | true                     | Se o pedido está completo |

#### Exemplo de request
Veja a seguir um exemplo de request do endpoint `/store/order`:
~~~
	curl -X 'POST' \
	  'https://petstore3.swagger.io/api/v3/store/order' \
	  -H 'accept: application/json' \
	  -H 'Content-Type: application/json' \
	  -d '{
	  "id": 10,
	  "petId": 198772,
	  "quantity": 7,
	  "shipDate": "2023-09-04T17:46:41.158Z",
	  "status": "approved",
	  "complete": true
	}'
~~~
#### Exemplo de resposta
Veja a seguir um exemplo de resposta do endpoint `/store/order`, em caso de sucesso:
~~~
	{
	  "id": 10,
	  "petId": 198772,
	  "quantity": 7,
	  "shipDate": "2023-09-04T17:46:41.158+00:00",
	  "status": "approved",
	  "complete": true
	}
~~~

**Observação**: As definições da resposta estão na tabela  _Request body_.

#### Códigos de erros

| Código HTTP | Descrição        |
| ----------- | ---------------- |
| 405         | Entrada inválida |

### `GET`/store/order/orderId
Acessa uma ordem de compra pelo número de ID do pedido.

**Observação**: _Use IDs com valores inteiros entre \<= 5 e \> 10 para retornar respostas válidas._

#### Path param

| Parâmetro | Tipo             | Obrigatório/Opcional | Descrição    |
| --------- | ---------------- | -------------------- | ------------ |
| orderId   | integer ($int64) | Obrigatório          | ID do pedido |

#### Exemplo de request
Veja a seguir um exemplo de request do endpoint `/store/order/orderId`:
~~~
	curl -X 'GET' \
	  'https://petstore3.swagger.io/api/v3/store/order/10' \
	  -H 'accept: application/xml'
~~~
#### Exemplo de resposta
Veja a seguir um exemplo de resposta do endpoint `/store/order/orderId`, em caso de sucesso:
~~~
	{
	  "id": 10,
	  "petId": 198772,
	  "quantity": 7,
	  "shipDate": "2023-09-05T12:35:54.602Z",
	  "status": "approved",
	  "complete": true
	}
~~~
#### Definições da resposta

| Item     | Tipo                                 | Exemplo                  | Descrição                 |
| -------- | ------------------------------------ | ------------------------ | ------------------------- |
| id       | integer ($int64)                     | 10                       | ID do pedido              |
| petId    | integer ($int64)                     | 198772                   | ID do animal              |
| quantity | integer ($int64)                     | 7                        | Quantidade                |
| shipDate | string ($date-time)                  | 2023-09-04T17:46:41.158Z | Data de expedição         |
| status   | string (placed, approved, delivered) | approved                 | Status do pedido          |
| complete | boolean                              | true                     | Se o pedido está completo |

#### Códigos de erros

| Código HTTP | Descrição             |
| ----------- | --------------------- |
| 400         | ID inválida           |
| 404         | Pedido não localizado |

### `DELETE`/store/order/orderId
Deleta uma ordem de compra pelo número de ID do pedido.

**Observação**: _Use IDs com valores inteiros \< 1000 para retornar respostas válidas._

#### Path param

| Parâmetro | Tipo             | Obrigatório/Opcional | Descrição    |
| --------- | ---------------- | -------------------- | ------------ |
| orderId   | integer ($int64) | Obrigatório          | ID do pedido |

#### Exemplo de request
Veja a seguir um exemplo de request do endpoint `/store/order/orderId`:
~~~
	curl -X 'DELETE' \
	  'https://petstore3.swagger.io/api/v3/store/order/2' \
	  -H 'accept: */*'
~~~
#### Exemplo de resposta
Veja a seguir um exemplo de resposta do endpoint `/store/order/orderId`, em caso de sucesso:
~~~
	{
	  "code": 200,
	  "type": "unknown",
	  "message": "2"
	}
~~~
#### Definições da resposta

| Item    | Tipo             | Exemplo       | Descrição                 |
| ------- | ---------------- | ------------- | ------------------------- |
| code    | integer ($int64) | 200 (sucesso) | Código de resposta        |
| type    | string           | -             | Não especificado          |
| message | integer          | 2             | Número do pedido deletado |

#### Códigos de erros

| Código HTTP | Descrição             |
| ----------- | --------------------- |
| 400         | ID inválido           |
| 404         | Pedido não localizado |
