# JWT : Security

## Threats

```text
Weak signature validation
Algorithm confusion
Weak symmetric keys
Key identifier injection
Issuer or audience confusion
Cross-token substitution
Token theft and replay
Sensitive claim disclosure
Long-lived tokens
Untrusted remote key references
```

## Security Checklist

- Use HTTPS for issuance and transport.
- Allowlist algorithms and validate every cryptographic operation.
- Validate issuer, audience, expiration and token type.
- Use distinct validation rules for access, identity and refresh tokens.
- Keep claims minimal and non-secret unless encryption is applied.
- Protect signing keys and rotate them safely.
- Prevent tokens from entering logs, URLs and analytics.
- Use short access-token lifetimes and a defined revocation strategy.
- Test malformed tokens, duplicate fields and substitution attacks.
- Update JOSE libraries and monitor security advisories.

