# OpenAI : Structured Outputs

## Typed Output

```python
from pydantic import BaseModel

class Ticket(BaseModel):
    title: str
    priority: str
    tags: list[str]

response = client.responses.parse(
    model="YOUR_SUPPORTED_MODEL_ID",
    input="Create a ticket for a failed production deployment.",
    text_format=Ticket,
)

ticket = response.output_parsed
```

## Use Cases

```text
Data extraction
Typed application responses
UI generation
Classification
Workflow handoff
```

- Define narrow schemas with explicit required fields and enums.
- Reject unexpected properties where supported.
- Handle safety refusals as a distinct programmatic outcome.
- Validate business rules after schema parsing.
- Use tool calling when connecting the model to application functions.
- Use structured response formats when the model itself should return typed data.
