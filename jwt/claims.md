# JWT : Claims

## Registered Claims

```text
iss  Issuer
sub  Subject
aud  Audience
exp  Expiration time
nbf  Not valid before
iat  Issued at
jti  JWT identifier
```

## Public and Private Claims

```json
{
  "scope": "orders:read orders:write",
  "https://example.com/tenant_id": "tenant_123",
  "https://example.com/roles": ["editor"]
}
```

## Rules

- Validate `iss` against an exact trusted issuer value.
- Require the intended recipient in `aud`.
- Apply `exp` and `nbf` according to the protocol profile.
- Treat `iat` as metadata, not proof of current validity by itself.
- Use `jti` only with a defined uniqueness, replay or revocation strategy.
- Do not equate possession of a claim with authorization unless the recipient validates that claim for the requested operation.

