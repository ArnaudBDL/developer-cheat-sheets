# Prompt Engineering : Security

## Threats

```text
Prompt injection
Instruction hierarchy confusion
Sensitive-data disclosure
Unsafe tool invocation
Cross-tenant context leakage
Malicious retrieved documents
Untrusted output execution
Denial of wallet through excessive tokens or tools
```

## Controls

- Separate trusted instructions from untrusted content.
- Mark retrieved content as data, never as authority.
- Enforce authorization outside the model.
- Require approval for consequential actions.
- Validate tool arguments, URLs, files and generated code.
- Minimize secrets and personal data in context.
- Isolate tenants in retrieval and caching.
- Apply token, tool, time and spending limits.
- Log security outcomes without confidential prompt content.
- Test prompt-injection and exfiltration scenarios continuously.

A prompt is not a security boundary. Application controls must remain authoritative.
