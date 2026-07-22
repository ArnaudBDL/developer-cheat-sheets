# Model Context Protocol : Quick References

## Core concepts

```text
Host    AI application
Client  Connection maintained by the host
Server  Exposes capabilities
Tools   Callable actions
Resources Contextual data
Prompts Reusable prompt templates
```

## Server checklist

```text
Declare capabilities explicitly
Validate every tool input
Return structured errors
Apply least-privilege access
Avoid exposing secrets
Log calls without sensitive payloads
```

## JSON-RPC shape

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "method": "METHOD_NAME",
  "params": {}
}
```
