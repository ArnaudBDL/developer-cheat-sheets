# JWT : Payload

## Claims Set

```json
{
  "iss": "https://identity.example.com",
  "sub": "usr_42",
  "aud": "https://api.example.com",
  "exp": 1784718000,
  "iat": 1784717100,
  "jti": "tok_01J2ABCDEF",
  "scope": "orders:read"
}
```

## Payload Rules

- Include only claims required by the recipient.
- Minimize personal, confidential and mutable data.
- Namespace private claims to avoid collisions between systems.
- Do not trust payload values before signature and claim validation.
- Remember that signed payloads remain readable by anyone holding the token.
- Prefer identifiers over embedding complete user or authorization records.

