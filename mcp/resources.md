# Model Context Protocol : Resources

## Resource Concept

```text
A resource exposes readable context identified by a URI.
```

## Example

```json
{
  "uri": "docs://architecture/current",
  "name": "Current architecture decisions",
  "description": "Approved architecture record",
  "mimeType": "text/markdown"
}
```

## Resource Templates

```text
orders://{orderId}
projects://{projectId}/status
files://{path}
```

## Rules

- Use stable, meaningful URIs.
- Enforce authorization on every read.
- Limit content size and supported media types.
- Preserve source and freshness metadata when relevant.
- Exclude secrets and unnecessary sensitive data.
- Validate every resource-template argument.
- Never assume that a discoverable resource is readable by every caller.
