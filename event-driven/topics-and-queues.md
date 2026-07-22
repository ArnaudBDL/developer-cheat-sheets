# Event-Driven Architecture : Topics and Queues

## Queue

```text
A message is processed by one worker from the competing consumer set.
Typical use: background jobs and work distribution.
```

## Topic or Publication

```text
Multiple independent subscriptions can receive the same event.
Typical use: multiple business reactions to a published fact.
```

## Durable Stream

```text
Events are retained and consumers track their positions.
Typical use: replay, stream processing and historical reconstruction.
```

## Naming Examples

```text
orders.events.v1
payments.events.v1
notifications.email.commands.v1
billing.invoice-generation.requests.v1
```

Avoid mixing unrelated domains, commands and events in one undifferentiated channel.

