# OAuth 2.0 : Tokens

## Token Types

```text
Access token   Credential presented to a resource server
Refresh token  Credential used at the authorization server to obtain new access tokens
ID token       OpenID Connect identity assertion, not an OAuth access token
```

## Bearer Token

```http
Authorization: Bearer ACCESS_TOKEN
```

Anyone possessing a bearer token can use it within its validity and authorization limits.

## Rules

- Use TLS for token transport.
- Keep access tokens short-lived and audience restricted.
- Never place tokens in URLs when avoidable.
- Do not log complete tokens.
- Validate token type, issuer, audience, expiry and authorization data.
- Do not send refresh tokens to resource servers.
