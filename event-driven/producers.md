# Event-Driven Architecture : Producers

## Responsibilities

```text
Validate the business operation.
Commit the authoritative state change.
Create the corresponding event.
Publish reliably.
Expose publish failures and lag.
Preserve event identity across retries.
```

## Transactional Outbox

```text
Application transaction
  1. Update business state.
  2. Insert the event into an outbox table.
  3. Commit both changes atomically.

Publisher
  4. Read unpublished outbox records.
  5. Publish them to the broker.
  6. Mark them as published.
```

## Producer Checklist

- Define the source of truth for each event.
- Do not publish before the authoritative transaction succeeds.
- Use stable partition or routing keys.
- Treat publish retries as duplicates unless proven otherwise.
- Monitor outbox backlog and publishing failures.

