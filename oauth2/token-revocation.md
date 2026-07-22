# OAuth 2.0 : Token Revocation

## Request

```http
POST /revoke HTTP/1.1
Authorization: Basic CLIENT_CREDENTIALS
Content-Type: application/x-www-form-urlencoded

token=TOKEN&token_type_hint=refresh_token
```

## Effects

```text
Revoke one access token
Revoke one refresh token
Revoke a refresh-token family
Revoke all tokens for a client grant or user session
```

## Rules

- Authenticate the client where required.
- Verify that the client is authorized to revoke the token.
- Define whether related tokens are revoked together.
- Keep the response non-disclosing for unknown or already invalid tokens.
- Propagate revocation to resource servers within the documented consistency window.
- Test revocation with cached introspection or distributed validation.
