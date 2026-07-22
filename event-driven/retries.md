# Event-Driven Architecture : Retries

## Retry Classification

```text
Transient
  Network timeout, temporary dependency outage, throttling

Permanent
  Invalid schema, missing required business data, forbidden operation

Unknown
  Treat cautiously, retain evidence and limit attempts
```

## Backoff

```text
attempt 1: short delay
attempt 2: longer delay
attempt 3: longer delay plus jitter
maximum attempts: bounded
final outcome: dead-letter or explicit failure workflow
```

## Rules

- Retry only operations safe to repeat.
- Use exponential backoff with jitter for transient failures.
- Bound attempts, total age and concurrent retries.
- Respect downstream throttling signals.
- Avoid synchronized retry storms.
- Preserve the original event and failure history.

