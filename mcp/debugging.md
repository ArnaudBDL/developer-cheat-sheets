# Model Context Protocol : Debugging

## Connection Checklist

```text
Executable or endpoint is correct
Transport matches client configuration
Protocol data is not mixed with logs
Initialization completes
Protocol versions are compatible
Capabilities are negotiated as expected
Authentication is valid
```

## Feature Checklist

```text
Tool or resource appears in discovery
Schema is valid
Arguments match the schema
Authorization permits the operation
Backend dependency is reachable
Timeout and cancellation behavior is visible
Error response preserves the request identifier
```

## Logging

```text
Timestamp
Server and client version
Transport
Session or correlation identifier
JSON-RPC method
Request identifier
Duration
Outcome and error category
```

## Practical Rules

- Use MCP Inspector or SDK-provided development tooling when available.
- Log stdio diagnostics to stderr only.
- Redact tokens, secrets and sensitive arguments.
- Compare the negotiated protocol version with the implementation target.
- Reproduce with the smallest single capability call.
- Test transport, protocol handling and backend behavior separately.
- Record exact request and response metadata without exposing confidential payloads.
