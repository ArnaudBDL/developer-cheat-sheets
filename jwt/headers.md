# JWT : Headers

## JOSE Header

```json
{
  "alg": "RS256",
  "typ": "JWT",
  "kid": "2026-07-signing-key"
}
```

```text
alg  Cryptographic algorithm declared for the token
 typ  Media type hint, commonly JWT or a more explicit application type
 kid  Identifier used to select a verification key
 cty  Content type, useful for nested tokens
```

## Validation Rules

- Allow only algorithms configured for the token type.
- Do not choose verification behavior solely from the received `alg` value.
- Resolve `kid` only against trusted, configured key material.
- Reject duplicate or malformed header parameters.
- Use explicit token typing when different JWT kinds share infrastructure.
- Do not accept `alg: none` unless an explicitly designed unsecured-token profile requires it.

