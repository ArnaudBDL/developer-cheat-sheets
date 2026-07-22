# Model Context Protocol : Transports

## Standard Input and Output

```text
Host launches a local server process.
Client and server exchange protocol messages through stdin and stdout.
Diagnostic output belongs on stderr, not stdout.
```

## Streamable HTTP

```text
A remote MCP server exposes an HTTP endpoint.
Multiple clients can connect to a shared remote service.
Standard web authentication, authorization and transport security apply.
```

## Selection

```text
stdio
  Local, process-scoped integration controlled by the host.

Streamable HTTP
  Remote or shared integration requiring network and service hardening.
```

## Rules

- Preserve JSON-RPC message boundaries.
- Do not write logs to a stdio protocol channel.
- Use TLS for remote production connections.
- Apply request size, timeout and concurrency limits.
- Validate origins and network exposure according to deployment policy.
- Implement reconnect and session behavior according to the selected specification version.
