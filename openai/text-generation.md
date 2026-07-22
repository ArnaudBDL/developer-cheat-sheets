# OpenAI : Text Generation

## Responses API

```python
response = client.responses.create(
    model="YOUR_MODEL_ID",
    instructions="Answer concisely and distinguish facts from assumptions.",
    input="Explain idempotency in distributed systems.",
)

print(response.output_text)
```

## Conversation Input

```python
response = client.responses.create(
    model="YOUR_MODEL_ID",
    input=[
        {"role": "user", "content": "Draft a release note."},
    ],
)
```

## Rules

- Separate durable application instructions from user content.
- Set output limits appropriate to the task.
- Validate generated facts before consequential use.
- Preserve source attribution when grounding on retrieved content.
- Handle refusals, incomplete output and truncated responses explicitly.
- Do not treat generated text as executable instructions without validation.
