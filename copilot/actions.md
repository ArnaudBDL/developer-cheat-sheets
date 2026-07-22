# Copilot : Actions

## Action Flow

```text
1. Interpret the user intent.
2. Select an approved tool.
3. Validate identity, permission and parameters.
4. Present confirmation when required.
5. Execute the operation.
6. Verify the result.
7. Record outcome and attribution.
```

## Action Contract

```json
{
  "name": "createSupportTicket",
  "description": "Create a ticket after user approval",
  "inputs": {
    "title": "string",
    "description": "string",
    "priority": "low | medium | high"
  },
  "result": {
    "ticketId": "string",
    "status": "string"
  }
}
```

## Safety Rules

- Grant the minimum required permissions.
- Separate read and write capabilities.
- Make destructive actions explicit.
- Use idempotency for retry-sensitive operations.
- Do not infer missing identifiers or recipients.
- Return a clear success or failure result.
