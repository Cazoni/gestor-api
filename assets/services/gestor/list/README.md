# API do gestor/list
Descrição das funcionalidades do serviço

## Dados Gerais
O usuário deve estar logada para usar a funcionalidade.<br>
Máximo de resultados retornado é sempre 50 ($MAX_RESULTS)<br>
Há uma variável de $DEBUG, que permite que sejam retornados os erros na tela

## Serviços 

| serviço | descrição | 
| --- | --- |
| /setUrgency | Definir um pedido como urgente |
| /listOrders | Buscar listas de pedidos de acordo com os status definidos |

## Service "setUrgency"

### Função
Usado para definir um pedido com urgente, deve ser passado como parametros o serviço (service=setUrgency) e o Id do pedido (order=NS-xxxxx)<br>
Caso ocorra um erro, será retornado o status 500 com uma menagen de erro. Caso contrário, será retornado um código de status 200, indicando que o pedido foi definido como urgente, caso já esteja definido como urgente, retornará 200 novamente. 

## Service "listOrders"

### Função 
Retornar os pedidos no db, junto a seus produtos<br>
objeto AllowedStatuses indica os status que são permitidos de retornarem um uma consulta sem que seja pessado a chave **serach**<br>
objeto productionStatuses é usado para definir o que é um pedido em produção a partir do seu status, isso é usado para mostrar quantos pedidos estão em produção

### Request
Para realizar a chamada ao endpoint
