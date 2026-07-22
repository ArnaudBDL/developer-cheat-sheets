# Microservices : Messaging

## Message Types

```text
Command  Request for one capability to perform work
Event    Immutable fact that has already occurred
Reply    Result correlated to a previous request when required
```

## Delivery Concerns

```text
At-least-once delivery
Duplicate messages
Ordering boundaries
Retry policy
Dead-letter handling
Schema evolution
Consumer lag
Replay
```

## Rules

- Give messages unique identifiers.
- Make consumers idempotent.
- Use stable partition or routing keys where order matters.
- Separate transient and permanent failures.
- Preserve correlation and causation identifiers.
- Limit payload size and sensitive data.
- Monitor backlog age, retries and dead-letter queues.
- Never replay messages blindly into an unrepaired consumer.
