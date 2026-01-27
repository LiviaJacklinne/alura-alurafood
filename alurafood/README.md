# Microsserviços

Aprofuncando o conhecimento em arquitetura de microsserviços.

### Tecnologias
> - Java 17
> - Spring 2.6.7
> - Lombok
> - Flyway
> - MySQL
> - Eureka
> - Api Gateway
> - OpenFeign

### Subindo novas instâncias
```
& "c:\alura-food\pedidos\mvnw.cmd" spring-boot:run -f "c:\alura-food\pedidos\pom.xml"
```

### Endpoints
- Eureka = `localhost:8081`
- Serviço de pedidos = `localhost:8082/pedidos-ms/blabla`
- Serviço de pagamentos = `localhost:8082/pagamentos-ms/tandandan`

> O *Eureka Client* serve para registrar e descobrir serviços automaticamente em uma arquitetura de microserviços.
> *OpenFeign* é usado para comunicação sícrona com o servidor 
> 