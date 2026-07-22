# Copilot Studio : Actions and Tools

## Tool Types

```text
Connectors
Agent flows and workflows
Prompts
HTTP or API integrations
MCP tools and resources where configured
Other agents where configured
```

## Execution Contract

```text
Clear name and description
Strict inputs
Typed outputs
Authentication context
Authorization rule
Timeout and retry behavior
Idempotency strategy
Error and user-cancellation behavior
Approval requirement
```

Treat every model-selected action as a proposal. Validate inputs and permissions in the executing system, require confirmation for destructive operations, and return structured results that distinguish success, rejection and failure.
