# Model Context Protocol : Clients

## Responsibilities

```text
Connect to one MCP server
Negotiate capabilities
Discover exposed features
Validate server responses
Present capabilities to the host
Route calls and results
Handle cancellation, progress and errors
Protect host and user boundaries
```

## Client State

```text
Disconnected
Connecting
Initializing
Ready
Closing
Closed
```

## Safety Rules

- Connect only to trusted or explicitly approved servers.
- Display clear provenance for tools, resources and prompts.
- Require user approval for sensitive or destructive operations.
- Validate capability schemas before exposing them to the host.
- Keep credentials scoped to the intended server.
- Do not merge data from distinct trust domains without preserving attribution.
- Terminate connections that violate protocol or policy.
