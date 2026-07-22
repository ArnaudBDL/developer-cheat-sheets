# Microservices : Quick References

## Core patterns

```text
API Gateway
Service Discovery
Circuit Breaker
Bulkhead
Retry with backoff
Saga
Outbox
Dead Letter Queue
```

## Operational checklist

```text
Independent deployment
Explicit service ownership
Versioned contracts
Centralized observability
Timeouts on remote calls
Idempotent consumers
Automated health checks
```

## Health endpoints

```http
GET /health/live
GET /health/ready
GET /metrics
```
