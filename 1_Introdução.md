# Introdução
A API de serviços **Petstore** é uma API fictícia que simula o gerenciamento de uma loja de animais de estimação. Nesse contexto, foi projetada para permitir que donos de lojas de animais de estimação ofereçam uma variedade de serviços gerais para os animais de estimação dos clientes. Esses serviços podem incluir banho e tosa, cuidados de saúde, treinamento, produtos para animais e muito mais.

Esta API contém três objetos:

`PET`: Este grupo contém os endpoints necessários para gerenciar os registros dos animais de estimação: 

| Método | Endpoint                 | Descrição                       |
| ------ | ------------------------ | ------------------------------- |
| PUT    | /pet                     | Atualizar registro existente.   |
| POST   | /pet                     | Adicionar novo registro.        |
| GET    | /pet/findByStatus        | Localizar registro pelo status. |
| GET    | /pet/findByTags          | Localizar registro pela tag.    |
| GET    | /pet/{petId}             | Localizar registro pela ID.     |
| POST   | /pet/{petId}             | Atualizar registro.             |
| DELETE | /pet/{petId}             | Deletar registro.               |
| POST   | /pet/{petId}/uploadImage | Adicionar imagem ao registro.   |

`STORE`: Este grupo contém os endpoints necessários para gerenciar pedidos da loja: 

| Método | Endpoint               | Descrição                                                  |
| ------ | ---------------------- | ---------------------------------------------------------- |
| GET    | /store/inventory       | Retornar mapeamento do inventário por status e quantidade. |
| POST   | /store/order           | Criar um pedido.                                           |
| GET    | /store/order/{orderId} | Localizar uma ordem de compra pela ID.                     |
| DELETE | /store/order/{orderId} | Deletar uma ordem de compra pela ID.                       |

`USER`: Este grupo contém os endpoints necessários para gerenciar os registros dos clientes:

| Método | Endpoint             | Descrição                        |
| ------ | -------------------- | -------------------------------- |
| POST   | /user                | Criar cliente.                   |
| POST   | /user/createWithList | Criar lista de clientes.         |
| GET    | /user/login          | Fazer login de cliente.          |
| GET    | /user/logout         | Fazer logout de cliente.         |
| GET    | /user/{username}     | Localizar cliente pelo username. |
| PUT    | /user/{username}     | Atualizar cliente.               |
| DELETE | /user/{username}     | Deletar cliente.                 |

**Observação**: _Este documento irá detalhar exclusivamente o funcionamento do objeto `STORE`._

## Primeiros passos
Para acessar e configurar esta API, são necessários alguns passos iniciais.

### Servidor
O endereço do servidor padrão usado pela API é:

`https://petstore3.swagger.io/api/v3/`

### Identificação e autorização
Para receber permissões de utilização, são necessários dois tipos de verificação. 
1. ID do cliente e seleção de escopos;
2. Chave de acesso da API.

Na página principal da [API Petstore](https://petstore3.swagger.io), clique no botão `Authorization` e preencha as informações necessárias, conforme as imagens abaixo:

![Authorization](https://drive.google.com/uc?id=1jgrO6VN2QQhFtNqP6ppHyJ8fu7mA35lN)
![key](https://drive.google.com/uc?id=1zo9THY24ModUE3u4GmF0Qfm24q1BojIY)

**Observação**: _Como é um cenário de testes, pode-se escolher a ID de cliente  e a chave de acesso. Essa chave de acesso deve ser utilizada no header em todas utilizações._
#### Escopos
Os escopos controlam o nível de acesso que os usuários terão com a API. Estão disponíveis dois escopos:

| Escopo     | Descrição                 |
| ---------- | ------------------------- |
| read:pets  | Permite apenas leitura    |
| write:pets | Permite leitura e escrita |
