# JWT : Validation

## Required Checks

```text
Compact serialization and JSON are well formed
Token type is expected
Algorithm is explicitly allowed
Key is trusted for this issuer and token type
Signature or authentication tag is valid
Issuer matches exactly
Audience contains this recipient
Expiration has not passed
Not-before time has been reached
Application-required claims are present and valid
Token is not revoked when revocation is supported
```

## Pseudocode

```typescript
const result = await joseLibrary.verify(token, trustedKeySet, {
  algorithms: ['RS256'],
  issuer: 'https://identity.example.com',
  audience: 'https://api.example.com',
  type: 'at+jwt',
  clockTolerance: configuredClockTolerance,
})
```

## Rules

- Complete authentication validation before authorization.
- Use exact values, not substring or partial matching.
- Keep key retrieval on trusted origins and validate cached key metadata.
- Fail closed on malformed, ambiguous or unverifiable tokens.
- Never decode a JWT and treat the decoded claims as validated.

