# OpenID Connect : Token Validation

## ID Token Validation

```text
Parse JOSE structure
Allow only configured signing algorithms
Resolve trusted keys for the exact issuer
Verify the cryptographic signature
Match issuer exactly
Require the client identifier in audience
Validate authorized party when required
Validate expiration and issued-at constraints
Validate nonce when used
Validate authentication context when the application requires it
```

## Key Retrieval

```text
Discovery metadata -> jwks_uri -> trusted signing keys
```

## Rules

- Never treat decoded claims as validated claims.
- Keep validation rules distinct for ID tokens and access tokens.
- Fail closed on unknown issuers, algorithms or keys.
- Handle signing-key rotation with bounded caching.
- Use exact string comparisons where the specification requires them.
- Complete token validation before creating or restoring an authenticated session.
