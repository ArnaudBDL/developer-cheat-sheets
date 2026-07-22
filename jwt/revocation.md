# JWT : Revocation

## Revocation Options

```text
Short access-token lifetime
Server-side denylist keyed by jti or token digest
Per-user or per-session security version
Refresh-token record and family revocation
Signing-key removal after compromise
Reference or opaque tokens with introspection
```

## Denylist Example

```text
key: revocation:{issuer}:{jti}
value: revoked
expiry: token exp
```

## Rules

- Define which events revoke one token, one session, one token family or all user sessions.
- Keep revocation state available to every enforcing recipient.
- Expire denylist records when the token can no longer be accepted.
- Treat signing-key compromise as an incident, not ordinary logout.
- Test logout, password change, role change and compromise scenarios.

