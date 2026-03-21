# AluraFood

Aplicação desenvolvida para o estudo de Microsserviços e Mensageria;

### Cursos de referência:
- [Microsserviços na prática: implementando com Java e Spring](https://cursos.alura.com.br/course/microsservicos-implementando-java-spring)
- [Microsserviços na prática: mensageria com RabbitMQ](https://cursos.alura.com.br/course/microsservicos-pratica-mensageria-rabbitmq)

## Stack
> - Java 17
> - Spring 2.6.7
> - Swagger 1.7
> - Lombok
> - Microsserviço
> - Eureka
> - OpenFeign
> - Api Gateway
> - MySQL
> - Flyway


## Execução

### RabbitMQ
Para executar o RabbitMQ, usamos um container Docker; <br>
Quando o container estiver de pé, podemos acessar a aplicação pela url [localhost:15672](http://localhost:15672), sendo `Usuario e senha` = `guest`.
> Link útil, ele simula operações com fila: [RabbitMq Simulator](https://tryrabbitmq.com/)

### Microsserviços
Execute os microsserviços na seguinte ordem:
```bash
# 1º Dockercompose
rabbitmq

# 2º Serviço de descoberta (localhost:8081)
server 

# 3º
gateway

# 4º (tanto faz qual do dois será executado primeiro)
pedidos
pagamentos
```

### Endpoints
- Eureka = `localhost:8081`
- Serviço de pedidos = `localhost:8082/pedidos-ms/blabla`
- Serviço de pagamentos = `localhost:8082/pagamentos-ms/tandandan`
- Swagger: [http://localhost:8082/swagger-ui.html](http://localhost:8082/swagger-ui.html)

<br>

> - O **Eureka Client** serve para registrar e descobrir serviços automaticamente em uma arquitetura de microserviços;<br>
> -  **OpenFeign** é usado para comunicação sícrona com os serviços; <br>
> - Para o **Swagger** usamos duas dependencias: `springdoc-openapi-webflux-ui` para o gatawey e `springdoc-openapi-ui` para os demais MS; <br>
> - Uma **exchange** é o componente responsável por receber mensagens e decidir para qual fila (queue) elas devem ir ;
> -  Um **fanout exchange** envia a mensagem para TODAS as filas conectadas a ele. É tipo um anúncio em alto-falante, todo mundo que estiver ouvindo recebe a mensagem;