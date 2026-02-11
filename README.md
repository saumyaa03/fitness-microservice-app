![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/SpringBoot-3.x-brightgreen)
![Kafka](https://img.shields.io/badge/Kafka-Event--Driven-black)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue)

# Fitness Microservices Platform - Backend

A distributed microservices-based backend system built with Spring Boot.
The platform supports secure authentication via Keycloak, event-driven
communication using Kafka, centralized routing via API Gateway, and scalable service orchestration.




## Overview

This backend system follows a microservices architecture and includes:

-   User Service
-   Activity Service
-   AI Recommendation Service
-   Service Discovery (Eureka)
-   Secure Authentication via Keycloak (OIDC)
-   Event-driven communication using Kafka

The system demonstrates clean architecture, separation of concerns, and
scalable backend design.


## System Architecture

```text
Client (React)
        ↓
API Gateway
        ↓
| User | Activity | AI |
        ↓
Database (PostgreSQL / MongoDB)


Authentication: Keycloak
Service Discovery: Eureka
Event Streaming: Kafka
```


## Tech Stack

-   Java 17
-   Spring Boot
-   Spring Cloud Gateway
-   Spring Security
-   Spring Data JPA
-   REST APIs
-   Keycloak (OAuth2 / OIDC)
-   Kafka
-   Eureka
-   PostgreSQL / MongoDB
-   Docker
-   JUnit


## Authentication & Security

-   Keycloak handles authentication
-   JWT-based stateless authentication
-   Gateway forwards authenticated requests
-   Spring Security validates JWT in services
-   Role-based access control enforced at controller level

All protected endpoints require:

Authorization: Bearer `<access_token>`{=html}


## Event-Driven Flow

1. Activity Service persists new activity
2. Activity Service publishes event to Kafka topic
3. AI Service consumes event asynchronously
4. Recommendation is generated and stored
5. Frontend retrieves recommendation via secured REST endpoint


## How To Run

1️. Start Infrastructure

- PostgreSQL / MongoDB
- Kafka
- Keycloak
- Eureka Server

2️. Start Gateway and Services
For each service (including gateway):

```
mvn clean install 
mvn spring-boot:run
```


## Design Principles

-   Stateless JWT authentication
-   Centralized routing via API Gateway
-   Service decoupling via Kafka
-   Clean layered architecture
-   Container-ready services
-   Independent service deployment
