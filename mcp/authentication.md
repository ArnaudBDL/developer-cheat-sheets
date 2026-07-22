# Model Context Protocol : Authentication

## Trust Boundaries

```text
Local stdio server
  Trust is established through executable configuration, process launch and local permissions.

Remote HTTP server
  Trust requires server identity, protected transport and an explicit authorization flow.
```

## Authentication Checklist

```text
Verify server identity
Authenticate the user or workload
Bind credentials to the intended server
Request minimum scopes
Protect tokens at rest and in transit
Rotate and revoke credentials
Reauthenticate for sensitive operations when required
Audit grant and use
```

## Rules

- Follow the authentication profile of the negotiated MCP specification version.
- Do not forward one server's credentials to another server.
- Do not expose tokens in model context, tool results or logs.
- Enforce authorization server-side for every capability invocation.
- Treat local process execution as a meaningful security boundary, not as automatic trust.
