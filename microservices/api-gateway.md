# Microservices : API Gateway

## Responsibilities

```text
Client entry point
Request routing
Protocol termination
Authentication enforcement
Rate limiting
Request and response transformation
Aggregation when justified
Observability and correlation
```

## Flow

```text
Client -> API Gateway -> Domain Service
                    -> Composition Service
```

## Rules

- Keep domain business logic out of the gateway.
- Avoid a single gateway contract that must satisfy incompatible client needs.
- Use a Backend for Frontend when client-specific orchestration differs significantly.
- Protect the gateway as an internet-facing security boundary.
- Define gateway availability, scaling and timeout budgets.
- Do not treat the gateway as a substitute for service-level authorization.
