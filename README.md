# Eureka Server

Servidor de Service Discovery construído com Spring Boot + Spring Cloud Netflix Eureka, preparado para arquiteturas distribuídas com foco em:

- Descoberta de serviços
- Segurança
- Observabilidade
- Monitoramento em tempo real

---

# Tecnologias utilizadas

- Java 17
- Spring Boot
- Spring Cloud Netflix Eureka
- Spring Security
- Spring Boot Actuator
- Micrometer
- Prometheus
- Grafana
- Maven

---

# Funcionalidades

✅ Service Discovery  
✅ Dashboard Eureka protegido  
✅ Basic Authentication  
✅ Health Checks  
✅ Métricas de aplicação  
✅ Endpoint Prometheus  
✅ Integração com Grafana  
✅ Monitoramento em tempo real  

---

# Arquitetura

```text
                        +----------------------+
                        |    Eureka Server     |
                        |       :8761          |
                        +----------------------+
                                  |
                                  |
                     /actuator/prometheus
                                  |
                                  |
                        +----------------------+
                        |     Prometheus       |
                        |       :9090          |
                        +----------------------+
                                  |
                                  |
                        +----------------------+
                        |       Grafana        |
                        |       :3000          |
                        +----------------------+
```

---

# Estrutura do projeto

```bash
eureka-server/
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── config/
│   │   │   │   └── SecurityConfig.java
│   │   │   │
│   │   │   └── EurekaServerApplication.java
│   │   │
│   │   └── resources/
|   |   ├── observability/
│   |   |   └── prometheus.yml
│   │   └── application.properties
│   │   └── application.yml
│   │
│   └── test/

│
├── pom.xml
└── README.md
```

---

# Configuração principal

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

---

# Segurança

O dashboard do Eureka está protegido via Basic Authentication.

## Acesso

```txt
http://localhost:8761
```

## Credenciais

```txt
username: admin
password: 123456
```

---

# Observabilidade

Este projeto possui integração com:

- Spring Boot Actuator
- Micrometer
- Prometheus
- Grafana

As métricas são expostas pelo endpoint:

```bash
GET /actuator/prometheus
```

E consumidas por Prometheus para visualização no Grafana.

---

# Endpoints disponíveis

## Health Check

```bash
GET /actuator/health
```

## Métricas

```bash
GET /actuator/metrics
```

## Prometheus

```bash
GET /actuator/prometheus
```

---

# Como executar

## Clonar repositório

```bash
git clone <url-do-repositorio>
```

---

## Entrar na pasta

```bash
cd eureka-server
```

---

## Executar aplicação

```bash
./mvnw spring-boot:run
```

ou execute pela IDE.

---

# Executando Prometheus

Utilizando a configuração do projeto:

```bash
prometheus.exe --config.file=observability/prometheus.yml
```

Acesso:

```txt
http://localhost:9090
```

---

# Visualizando métricas no Grafana

Após configurar o Prometheus como datasource no Grafana:

```txt
http://localhost:3000
```

As métricas do Eureka Server podem ser acompanhadas em tempo real através de dashboards.

---

# Melhorias futuras

- Docker
- Eureka Cluster
- Profiles por ambiente
- Logs distribuídos
- CI/CD
- Testes de integração

---

# Objetivo do projeto

Demonstrar implementação prática de componentes essenciais em arquiteturas distribuídas:

- Service Discovery
- Segurança
- Observabilidade
- Monitoramento
- Escalabilidade

---

# Desenvolvedora

## Helen Cristina Batista

Back-End Developer  
Java • Spring Boot • Microservices • RabbitMQ • Observability
