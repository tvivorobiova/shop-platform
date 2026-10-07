# Shop Platform

A learning project: an order processing system built with microservices.

## Tech Stack

Java 21, Spring Boot 3, gRPC, Kafka, REST, PostgreSQL, DynamoDB,
Docker, Kubernetes, Testcontainers.

## Services

| Service | Responsibility |
|---|---|
| api-gateway | Single entry point, authentication, rate limiting |
| order-service | Order creation and lifecycle |
| inventory-service | Stock levels and reservations |
| payment-service | Payment processing |
| notification-service | User notifications |
| catalog-service | Product catalog |

## Quick Start

_To be added once the local infrastructure is set up._

## Repository Structure

- `contracts/` - Protobuf, Avro schemas, OpenAPI specs
- `libs/` - shared libraries
- `services/` - microservices
- `deploy/` - Docker Compose, Helm, Kubernetes manifests
- `docs/adr/` - architecture decision records
