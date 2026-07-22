# Prompt Engineering : Tool Use

## Tool Instruction Pattern

```text
Use the customer lookup tool only when a customer identifier is present.
Use the order tool only for orders visible to the authenticated user.
Never invent tool arguments.
Ask for approval before cancellation or payment actions.
```

## Execution Loop

```text
Model selects a tool
Application validates tool name and arguments
Application authorizes user and target resource
Application requests approval when required
Application executes the tool
Application returns structured results
Model produces the final response
```

- Describe tools precisely and narrowly.
- Use strict argument schemas.
- Treat tool calls as untrusted proposals.
- Enforce permissions outside the model.
- Make side effects explicit and retries safe.
- Preserve result provenance.
- Bound recursive calls, latency, cost and output size.
