# OAuth 2.0 : Security

## Primary Threats

```text
Authorization code interception or injection
Redirect URI manipulation
Cross-site request forgery
Token theft and replay
Open redirectors
Client impersonation
Scope escalation
Refresh-token reuse
Mix-up and issuer confusion
Credential leakage in logs or URLs
```

## Controls

- Use authorization code with PKCE for redirect-based clients.
- Match redirect URIs exactly against registered values.
- Bind authorization responses to the initiating transaction.
- Validate issuer and authorization-server identity.
- Use TLS for authorization, token and resource endpoints.
- Keep tokens audience restricted and short-lived.
- Use sender-constrained tokens where the risk profile requires them.
- Avoid the implicit grant and resource-owner password grant in new designs.
- Protect client credentials and refresh tokens.
- Apply least privilege, consent and object-level authorization.
- Redact tokens, codes and secrets from telemetry.
