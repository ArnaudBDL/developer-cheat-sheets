# OpenID Connect : Security

## Threats

```text
Authorization response injection
Redirect URI manipulation
State or nonce replay
Issuer mix-up
ID-token substitution
Signing-algorithm confusion
Access-token or refresh-token theft
Session fixation
Login CSRF
Excessive identity-data collection
Untrusted discovery metadata
```

## Controls

- Use Authorization Code Flow with PKCE.
- Validate issuer, audience, signature, expiry, state and nonce.
- Register exact redirect and logout URIs.
- Use TLS for provider and application endpoints.
- Protect cookies and rotate local sessions after authentication.
- Keep ID tokens, access tokens and authorization codes out of logs and URLs.
- Request minimum scopes and claims.
- Separate authentication claims from authorization policy.
- Restrict discovery to trusted issuers.
- Use maintained libraries and monitor protocol security updates.
