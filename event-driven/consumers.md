# Event-Driven Architecture : Consumers

## Consumer Flow

```text
Receive event
Validate envelope and schema
Check authorization or source trust
Check duplicate-processing state
Execute the business reaction
Commit state and idempotency record
Acknowledge the message
```

## Consumer Rules

- Make handlers idempotent.
- Bound processing time and resource usage.
- Separate transient failures from permanent failures.
- Acknowledge only after the required state is durable.
- Preserve original event identifiers in downstream events.
- Stop poison messages from blocking the entire consumer indefinitely.

## Consumer Groups

```text
One logical consumer group receives one processing opportunity per event.
Different logical consumer groups can react independently to the same event.
Parallelism is constrained by the broker's partitioning or queue model.
```

