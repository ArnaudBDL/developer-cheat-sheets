# OpenID Connect : Concepts

## Purpose

```text
OpenID Connect (OIDC) is an identity layer built on OAuth 2.0.
It lets a client verify an end user's authentication and obtain identity claims.
```

## Core Distinction

```text
OAuth 2.0 access token  Authorizes access to a protected resource
OpenID Connect ID token Communicates an authentication event to the client
```

## Core Artifacts

```text
ID Token
Authorization Code
Access Token
Refresh Token when issued
UserInfo response
Provider metadata
```

- Request the `openid` scope to initiate an OpenID Connect authentication request.
- Treat authentication and API authorization as separate decisions.
- Use maintained OIDC client libraries rather than implementing protocol validation manually.
- Keep redirect URIs, issuer identifiers and client registration explicit.
