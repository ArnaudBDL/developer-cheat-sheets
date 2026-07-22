# Microservices : Communication

## Synchronous Communication

```text
HTTP or gRPC request -> immediate response
```

Use synchronous calls when the caller needs an immediate result. Define timeouts, cancellation, authentication, versioning and failure behavior.

## Asynchronous Communication

```text
Producer -> broker -> one or more consumers
```

Use messages or events when work can complete later or several services react independently.

## Rules

- Keep contracts explicit and backward compatible.
- Avoid long synchronous dependency chains.
- Propagate correlation and trace context.
- Apply deadlines rather than unlimited waits.
- Make retry-sensitive operations idempotent.
- Do not expose internal service models directly as public contracts.
