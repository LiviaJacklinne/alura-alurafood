# AluraFood

Aplicação desenvolvida para o estudo de Microsserviços e Mensageria;

### Cursos de referência:
- [Microsserviços na prática: implementando com Java e Spring](https://cursos.alura.com.br/course/microsservicos-implementando-java-spring)
- [Microsserviços na prática: mensageria com RabbitMQ](https://cursos.alura.com.br/course/microsservicos-pratica-mensageria-rabbitmq)

## Stack
> - Java 17
> - Spring 2.6.7
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
Quando o container estiver de pé, podemos acessar a aplicação pela url [localhost:15672](http://localhost:15672), sendo `Usuario e senha` = `guest`

### Microsserviços
Execute os microsserviços na seguinte ordem:
```bash
# 1º Serviço de descoberta (localhost:8081)
server 

# 2º
gateway

# 3º (tanto faz qual do dois será executado primeiro)
pedidos
pagamentos
```

### Endpoints
- Eureka = `localhost:8081`
- Serviço de pedidos = `localhost:8082/pedidos-ms/blabla`
- Serviço de pagamentos = `localhost:8082/pagamentos-ms/tandandan`

<br>

> O **Eureka Client** serve para registrar e descobrir serviços automaticamente em uma arquitetura de microserviços.<br>
> **OpenFeign** é usado para comunicação sícrona com os serviços.
>