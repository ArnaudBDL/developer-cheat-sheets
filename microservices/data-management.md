# Microservices : Data Management

## Data Ownership

```text
Service A -> Database A
Service B -> Database B
Service C -> Database C
```

A service owns its private data model. Other services use its API or published events rather than reading or writing its tables directly.

## Cross-Service Workflows

```text
Saga
  Sequence of local transactions with compensating actions.

CQRS projection
  Read model built from service events.

API composition
  Query several owning services and combine results.

Transactional outbox
  Commit business state and an outgoing event atomically.
```

## Rules

- Define acceptable consistency and staleness.
- Avoid distributed transactions unless the platform and business requirement justify them.
- Make migrations backward compatible during rolling deployments.
- Test backup, restore, replay and reconciliation.
- Minimize duplicated sensitive data.
- Assign an owner to every derived read model.
