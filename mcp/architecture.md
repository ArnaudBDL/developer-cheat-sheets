# Model Context Protocol : Architecture

## Connection Model

```text
MCP Host
├── MCP Client A <-> MCP Server A
├── MCP Client B <-> MCP Server B
└── MCP Client C <-> MCP Server C
```

A host creates one MCP client for each connected server. Each client maintains a dedicated connection to its corresponding server.

## Protocol Layers

```text
Application features
  Tools, resources, prompts and sampling

Data layer
  JSON-RPC messages, lifecycle and capability negotiation

Transport layer
  Local standard input/output or remote Streamable HTTP
```

## Lifecycle

```text
Establish transport
Initialize connection
Negotiate protocol version and capabilities
Operate using supported features
Exchange notifications and progress
Shut down and release resources
```

Do not invoke a feature unless the relevant capability has been negotiated.
