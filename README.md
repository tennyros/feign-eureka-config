# Spring Cloud Config Repository

This repository contains external configuration files for microservices in the `feign-eureka` system. It is used by the [Spring Cloud Config Server](https://cloud.spring.io/spring-cloud-config/).

## Repository Structure

```text
├── application.yml     # Shared/default configuration for all services
├── user-service.yml    # Default config for user-service
├── order-service.yml   # Default config for order-service
├── user-service.yml    # Default profile for user-service
├── order-service.yml   # Default profile for order-service
```

## Naming Convention

Configuration file names follow the pattern:

`{application-name}[-{profile}].yml`

Examples:
- `user-service.yml` — default settings for `user-service`
- `user-service-dev.yml` — settings for `dev` profile of `user-service`
- `application.yml` — common settings shared by all services

## Usage

Each microservice must include the following in its `application.yml`:

```yaml
spring:
  application:
    name: user-service  # or order-service, etc.
  cloud:
    config:
      uri: http://localhost:8888
```