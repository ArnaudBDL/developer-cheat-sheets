# OpenID Connect : UserInfo

## Request

```http
GET /userinfo HTTP/1.1
Host: identity.example.com
Authorization: Bearer ACCESS_TOKEN
Accept: application/json
```

## Response

```json
{
  "sub": "usr_42",
  "name": "User",
  "email": "user@example.com",
  "email_verified": true
}
```

## Rules

- Present an access token issued for the UserInfo endpoint.
- Validate the protected transport and expected response format.
- Require the UserInfo `sub` to match the subject in the validated ID token.
- Request and retain only necessary claims.
- Do not expose the UserInfo access token to browser logs or URLs.
- Apply application authorization independently of UserInfo profile data.
