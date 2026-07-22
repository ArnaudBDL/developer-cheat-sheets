# OWASP : Secure Design

## Design Activities

```text
Define security requirements.
Identify assets and trust boundaries.
Model threats and abuse cases.
Choose preventive and detective controls.
Review architecture before implementation.
Validate assumptions through testing.
```

## Design Principles

- Minimize attack surface and privileged functionality.
- Separate trusted and untrusted components.
- Apply least privilege and deny by default.
- Design safe failure behavior.
- Protect critical workflows against replay, concurrency and automation abuse.
- Define limits for payloads, rates, costs and resource consumption.
- Make security-relevant state transitions explicit.
- Design recovery, rollback and incident response paths.

## Review Questions

```text
What must be protected?
Who can perform each operation?
Which data crosses a trust boundary?
What happens when a dependency fails?
How can the workflow be abused?
Which assumptions require verification?
How is compromise detected and contained?
```
