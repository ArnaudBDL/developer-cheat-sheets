# Event-Driven Architecture : Idempotency

## Idempotent Consumer

```sql
BEGIN;

INSERT INTO processed_events (consumer_name, event_id)
VALUES ('billing', 'evt_123')
ON CONFLICT DO NOTHING;

-- Apply the business update only when the insert succeeded.

COMMIT;
```

## Strategies

```text
Processed-event table keyed by consumer and event identifier
Natural unique business constraint
Entity version comparison
Idempotency key for an external side effect
Upsert or compare-and-set operation
```

## Rules

- Deduplicate within the same transaction as the business state change when possible.
- Scope idempotency records by logical consumer.
- Preserve identifiers across retries.
- Define retention for deduplication records.
- Test duplicate delivery before production.

