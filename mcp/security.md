# Model Context Protocol : Security

## Threats

```text
Malicious or compromised MCP server
Prompt injection in resources and tool results
Excessive tool permissions
Credential theft or confused-deputy behavior
Unauthorized resource access
Destructive or duplicate tool execution
Data exfiltration through sampling
Dependency or executable tampering
Denial of service through oversized or expensive requests
```

## Controls

- Approve and inventory servers before use.
- Apply least privilege to users, clients, servers and backend identities.
- Separate trusted instructions from untrusted retrieved content.
- Require confirmation for high-impact actions.
- Validate tool inputs, resource URIs and all returned content.
- Sandbox local servers where practical.
- Pin and verify server packages or executables.
- Use TLS and strong authentication for remote servers.
- Apply quotas, timeouts, output limits and cancellation.
- Audit capability discovery and execution.

MCP enables data access and code-execution paths, so security decisions must cover the complete host, client, server and backend chain.
