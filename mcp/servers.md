# Model Context Protocol : Servers

## Responsibilities

```text
Declare server capabilities
Expose focused tools, resources and prompts
Validate all inputs
Enforce authorization
Return structured results and errors
Support cancellation where applicable
Log security-relevant activity
Release resources when connections close
```

## Server Boundary

```text
MCP protocol handler
  -> authentication and authorization
  -> schema validation
  -> domain service
  -> external API, database or local system
```

## Design Rules

- Give each server a clear domain and trust boundary.
- Keep exposed capabilities narrow and well described.
- Separate read-only operations from side-effecting operations.
- Isolate credentials from model-visible content.
- Apply timeouts, quotas and resource limits.
- Never assume that client-supplied arguments are safe.
- Treat reference servers and examples as learning material unless explicitly hardened for production.
