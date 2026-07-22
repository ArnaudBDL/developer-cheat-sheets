# OpenID Connect : ID Tokens

## Example Payload

```json
{
  "iss": "https://identity.example.com",
  "sub": "usr_42",
  "aud": "client_123",
  "exp": 1784718000,
  "iat": 1784717100,
  "nonce": "NONCE_VALUE",
  "auth_time": 1784717000
}
```

## Purpose

```text
An ID token is a signed authentication assertion intended for the Relying Party.
It is not an access token for calling arbitrary APIs.
```

## Rules

- Validate signature, issuer, audience, expiry and nonce where used.
- Validate `azp` when the token audience rules require it.
- Use `sub` with `iss` as the stable subject identity boundary.
- Do not use mutable claims such as email as the sole internal identity key.
- Do not send ID tokens to resource APIs unless a specific protocol explicitly requires it.
- Keep ID tokens out of URLs, logs and analytics.
