# OpenAI : Streaming

## Responses Stream

```python
with client.responses.stream(
    model="YOUR_MODEL_ID",
    input="Write a concise deployment checklist.",
) as stream:
    for event in stream:
        print(event)
```

## Client Responsibilities

```text
Parse event types
Append text deltas in order
Handle structured or tool events separately
Detect completion and error events
Support cancellation
Persist only finalized content when required
```

- Do not assume every event contains user-visible text.
- Handle network interruption and partial output.
- Avoid retrying a side-effecting request without idempotency protection.
- Bound client buffers and connection lifetime.
- Moderate or validate content before exposing partial output when required.
- Record request identifiers for failed streams.
