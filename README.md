# E-Commerce Microservices

This repository contains the microservices architecture that is replacing the legacy monolithic e-commerce platform as part of the E-Commerce Platform Modernization project.

## Project Overview

This project implements the microservices architecture described in the [E-Commerce Platform Overview](../confluence_samples/01_ecommerce_platform_overview.html) document.

## Related Jira Stories
- [ECOM-1001](../jira_stories/ECOM-1001.json): Implement product recommendation engine for e-commerce platform
- [ECOM-1002](../jira_stories/ECOM-1002.json): Implement recommendation service client

## Microservices Architecture

This repository contains the following microservices:

### Core Services
- **product-service**: Product catalog management
- **cart-service**: Shopping cart functionality
- **checkout-service**: Checkout and payment processing
- **user-service**: User account management
- **order-service**: Order management
- **inventory-service**: Inventory management
- **search-service**: Search functionality
- **recommendation-service**: Product recommendation engine

### Supporting Services
- **api-gateway**: API Gateway for service orchestration
- **discovery-service**: Service discovery (Eureka)
- **config-service**: Centralized configuration
- **auth-service**: Authentication and authorization

## Technology Stack

- Java 17
- Spring Boot 3.x
- Spring Cloud
- Spring Data JPA
- PostgreSQL
- MongoDB (for product catalog)
- Redis (for caching)
- RabbitMQ (for messaging)
- Docker & Kubernetes
- AWS Cloud Infrastructure

## Getting Started

### Prerequisites
- JDK 17
- Maven 3.8+
- Docker and Docker Compose
- Kubernetes CLI (kubectl)

### Build and Run Locally
```bash
# Build all services
./mvnw clean package

# Run with Docker Compose
docker-compose up
```

### Deploy to Kubernetes
```bash
# Apply Kubernetes configurations
kubectl apply -f k8s/
```

## Service Communication

Services communicate using:
1. Synchronous REST APIs
2. Asynchronous messaging via RabbitMQ
3. Event sourcing for critical workflows

## CI/CD Pipeline

This repository is integrated with our CI/CD pipeline:
- GitHub Actions for CI
- ArgoCD for CD to Kubernetes
- SonarQube for code quality analysis
- JFrog Artifactory for artifact management

## Monitoring and Observability

- Prometheus for metrics collection
- Grafana for visualization
- ELK stack for log aggregation
- Jaeger for distributed tracing
