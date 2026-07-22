# OpenAI : Tool Calling

## Tool Definition

```python
tools = [{
    "type": "function",
    "name": "get_order",
    "description": "Return one order visible to the current user.",
    "parameters": {
        "type": "object",
        "properties": {"order_id": {"type": "string"}},
        "required": ["order_id"],
        "additionalProperties": False,
    },
    "strict": True,
}]

response = client.responses.create(
    model="YOUR_TOOL_CAPABLE_MODEL_ID",
    input="Find order ord_123.",
    tools=tools,
)
```

## Execution Loop

```text
Model requests a tool
Application validates name and arguments
Application authorizes the user and target object
Application executes the function
Application returns the tool result
Model produces the final response
```

- Treat model-provided arguments as untrusted input.
- Use strict schemas and an explicit tool allowlist.
- Require approval for destructive or consequential actions.
- Make retries idempotent where possible.
- Never give a tool broader backend permissions than necessary.
- Log tool outcome and correlation data without secrets.
