# Event-Driven Architecture : Principles

## Core Principles

```text
Model events as immutable facts that have already happened.
Separate event production from event consumption.
Keep event contracts stable and evolvable.
Assume asynchronous processing and eventual consistency.
Design explicitly for duplication, retries, reordering and replay.
Make failures observable and recoverable.
Minimize coupling to broker-specific features.
```

## When Event-Driven Architecture Fits

- Multiple consumers react independently to the same business fact.
- Producers and consumers need independent deployment or scaling.
- Workloads benefit from asynchronous buffering.
- Replay, audit history or stream processing is required.
- Immediate synchronous completion is not required for every reaction.

## Design Checklist

```text
Event ownership
Schema ownership
Delivery semantics
Ordering boundary
Idempotency strategy
Retry policy
Dead-letter handling
Replay procedure
Observability
Security and data classification
```

