# ADR-0001: Microservices Architecture and the Saga Pattern

- Status: Accepted
- Date: 2026-10-07

## Context

We need an order processing system that demonstrates microservices with
both synchronous (gRPC) and asynchronous (Kafka) communication.

## Decision

- Split the system into services by business capability.
- Each service owns its own database (database-per-service).
- Implement distributed business transactions with the Saga pattern
  (choreography over Kafka) and compensating actions.
- Use gRPC for internal synchronous calls and REST for the external API.

## Alternatives Considered

- **Modular monolith**: simpler to build and operate, but does not
  demonstrate the target stack.
- **Two-phase commit (2PC)**: does not scale well and does not fit
  an event-driven architecture built on Kafka.

## Consequences

- Eventual consistency between services.
- Consumers must be idempotent; the Transactional Outbox pattern is required.
- Higher operational and testing complexity.
