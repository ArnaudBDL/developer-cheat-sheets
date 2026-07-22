# Event-Driven Architecture : Delivery Semantics

## Common Semantics

```text
At-most-once
  A message may be lost but is not deliberately retried after delivery.

At-least-once
  A message is retried until acknowledged and may be delivered more than once.

Exactly-once effect
  The business outcome is applied once through coordinated broker, storage and idempotency mechanisms.
```

## Design Questions

```text
When is a message considered accepted?
When is it acknowledged?
What happens after consumer failure?
Can producer retries duplicate an event?
Which boundary claims exactly-once behavior?
How is the business effect deduplicated?
```

Document semantics end to end. A broker guarantee alone does not define the behavior of producer state, consumer state and external side effects.

