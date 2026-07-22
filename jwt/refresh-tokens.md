# JWT : Refresh Tokens

## Purpose

A refresh token is credential material used by an authorized client to obtain a new access token. Whether it is a JWT or opaque value is protocol and deployment specific.

## Rotation Flow

```text
Client presents refresh token
Authorization server validates client, grant and token state
Server invalidates or marks the presented token as used
Server issues a new access token and refresh token
Reuse of an old rotated token triggers the configured incident response
```

## Controls

- Store refresh tokens more securely than ordinary application data.
- Bind them to the intended client and grant.
- Use rotation or another replay-detection mechanism where required.
- Apply absolute and inactivity expiration policies.
- Revoke the token family on logout, compromise or detected reuse as defined by policy.
- Never send refresh tokens to resource APIs.
- Do not expose them to browser JavaScript when an HTTP-only cookie architecture can avoid it.

