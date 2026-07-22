# Copilot : Security

## Threats

```text
Overshared source content
Prompt injection
Sensitive data disclosure
Excessive tool permissions
Unauthorized actions
Malicious connectors or dependencies
Inaccurate generated content
Missing attribution and audit evidence
```

## Controls

- Apply least privilege to users, agents, connectors and actions.
- Protect source data before grounding Copilot on it.
- Separate trusted instructions from retrieved content.
- Use authentication and data policies for agents.
- Require review for consequential outputs and actions.
- Enable auditing, monitoring, retention and incident response.
- Keep products, extensions and dependencies current.
- Test prompt injection and data-exfiltration scenarios.

## Release Gate

```text
Data sources approved
Permissions verified
Sensitive data reviewed
Actions constrained
Human approvals configured
Adversarial tests passed
Audit and alerting enabled
Owner and response process assigned
```
