# OAuth 2.0 : Refresh Tokens

## Refresh Request

```http
POST /token HTTP/1.1
Content-Type: application/x-www-form-urlencoded

grant_type=refresh_token&refresh_token=REFRESH_TOKEN&scope=orders%3Aread
```

## Rotation

```text
Validate refresh token and client binding
Invalidate or mark the presented token as used
Issue a new access token
Issue a new refresh token
Detect reuse of an older token
Revoke the affected token family when policy requires it
```

## Rules

- Protect refresh tokens as high-value credentials.
- Bind them to the intended client and grant.
- Apply absolute and inactivity lifetimes.
- Use rotation or sender-constraining where required.
- Do not increase scope during refresh.
- Revoke refresh tokens on compromise, logout or consent withdrawal according to policy.
