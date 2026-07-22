# Model Context Protocol : Tools

## Tool Definition

```json
{
  "name": "get_order",
  "description": "Return one order visible to the current user",
  "inputSchema": {
    "type": "object",
    "required": ["orderId"],
    "properties": {
      "orderId": { "type": "string" }
    },
    "additionalProperties": false
  }
}
```

## Execution Flow

```text
Discover tool
Select tool
Validate arguments
Authorize caller and target object
Request approval when required
Execute with bounded resources
Return structured result
Record outcome and attribution
```

## Design Rules

- Use specific names and precise descriptions.
- Define strict input schemas.
- Disclose side effects in the description and product UI.
- Make retries safe or document non-idempotent behavior.
- Return actionable errors without leaking internals.
- Separate high-risk actions into narrowly scoped tools.
- Never grant a tool more backend permission than it requires.
