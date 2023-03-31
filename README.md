# Sample Spring Boot Configuration

## Introduction

This is a sample configuration file for a Spring Boot application. The file is written in YAML format and contains
settings for the server, database, logging, and more.

## Server

```yaml
server:
  port: 8080
```

The server section specifies the port on which the Spring Boot application will run. In this case, it is set to 8080.

## PostgreSQL

```yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/db_name
    username: postgres
    password: 1234
    driver-class-name: org.postgresql.Driver
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
    properties:
      hibernate:
        format_sql: true
    database: postgresql
    database-platform: org.hibernate.dialect.PostgreSQLDialect
```

The spring.datasource section specifies the configuration details for the Postgres SQL database, including the URL,
username, password, and driver class name. The spring.jpa section configures the Hibernate JPA implementation, including
the DDL auto, SQL show, and database and dialect settings.

## Resilience4j

```yaml
resilience4j:
  ratelimiter:
    instances:
      basic:
        limit-for-period: 10
        limit-refresh-period: 1m
        timeout-duration: 10s
```

The resilience4j section configures the rate limiter for the application. The instances section specifies the rate
limiter instance, including the limit for period, limit refresh period, and timeout duration.

## Swagger

```yaml
springdoc:
  api-docs:
    path: /api-docs
    enabled: true
```

The springdoc section configures the Swagger UI and OpenAPI documentation. The api-docs section specifies the path and
enables the documentation.

## Prometheus

```yaml
management:
  endpoints:
    web:
      exposure:
        include:
          - "*"
          - prometheus
```

The management section configures the Prometheus monitoring endpoint for the application. The endpoints section
specifies the exposure and includes the Prometheus endpoint.

## RabbitMQ

```yaml
spring:
  rabbitmq:
    host: localhost
    port: 5672
    username: guest
    password: guest
```

The rabbitmq section configures the RabbitMQ message broker, including the host, port, username, and password.

## Logging

```yaml
logging:
  level:
    root: info
    com.example.mypackage: debug
  file:
    name: /var/log/myapp.log
```

The logging section configures the logging level and file output. The level section sets the root logging level to info
and the logging level for the com.example.mypackage package to debug. The file section specifies the output file name
and location.

For more information on configuring a Spring Boot application using application.yml files, refer to
the _[official
documentation.](https://docs.spring.io/spring-boot/docs/current/reference/html/application-properties.html)_