# Eureka Server

Servidor de descoberta de serviços desenvolvido com Spring Boot e Spring Cloud Netflix Eureka para arquiteturas de microsserviços.

Este projeto é responsável por centralizar o registro e a descoberta dinâmica dos serviços da aplicação, permitindo comunicação desacoplada entre microsserviços, escalabilidade e integração com API Gateway.

## Tecnologias utilizadas

- Java 17+
- Spring Boot
- Spring Cloud Netflix Eureka
- Maven

## Funcionalidades

- Registro automático de microsserviços
- Descoberta dinâmica de serviços
- Centralização das instâncias da arquitetura
- Suporte a escalabilidade horizontal
- Integração com API Gateway e demais microsserviços

## Estrutura do projeto

```bash
src
 └── main
     ├── java
     │    └── ...EurekaServerApplication.java
     └── resources
          └── application.yml
```

## Configuração

O servidor roda na porta `8761`.

Exemplo de configuração:

```yaml
server:
  port: 8761

spring:
  application:
    name: eureka-server

eureka:
  client:
    register-with-eureka: false
    fetch-registry: false
```

## Como executar o projeto

### Clone o repositório

```bash
git clone <url-do-repositorio>
```

### Acesse a pasta do projeto

```bash
cd eureka-server
```

### Execute a aplicação

```bash
./mvnw spring-boot:run
```

Ou execute pela sua IDE.

## Dashboard Eureka

Após iniciar o projeto, acesse:

http://localhost:8761

No dashboard será possível visualizar todos os microsserviços registrados.

## Integração com outros microsserviços

Para registrar um serviço neste Eureka Server, configure o microsserviço cliente:

```yaml
spring:
  application:
    name: auth-service

eureka:
  client:
    service-url:
      defaultZone: http://localhost:8761/eureka
```

Após iniciar o serviço, ele aparecerá automaticamente no dashboard.

## Arquitetura

```text
                    +----------------+
                    |  Eureka Server |
                    |      :8761     |
                    +----------------+
                             |
        -----------------------------------------------
        |                    |                         |
        |                    |                         |
+---------------+   +----------------+      +----------------+
| Gateway       |   | Auth Service   |      | Product Service|
+---------------+   +----------------+      +----------------+
```

## Objetivo do projeto

Este projeto faz parte de uma arquitetura baseada em microsserviços, garantindo descoberta automática, desacoplamento entre serviços e facilidade de manutenção e escalabilidade do sistema.

---

# 👩‍💻 Desenvolvedora

## Helen Cristina Batista

Back-End Developer • Java • Spring Boot • Microsservices • RabbitMQ

<p align="left">
  <a href="https://gith
