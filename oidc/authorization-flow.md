# OpenID Connect : Authorization Flow

## Authorization Code Flow

```text
Relying Party redirects the browser to the authorization endpoint
OpenID Provider authenticates the End-User
Provider returns a short-lived authorization code
Relying Party exchanges the code at the token endpoint
Provider returns an ID token and access token
Relying Party validates the ID token
Relying Party creates its local authenticated session
```

## Authorization Request

```http
GET /authorize?response_type=code&client_id=client_123&redirect_uri=CALLBACK&scope=openid%20profile&state=STATE&nonce=NONCE&code_challenge=CHALLENGE&code_challenge_method=S256 HTTP/1.1
Host: identity.example.com
```

## Rules

- Use Authorization Code Flow with PKCE for redirect-based clients.
- Match redirect URIs exactly against registration.
- Validate `state` and bind the response to the browser transaction.
- Validate `nonce` in the ID token when sent.
- Exchange each authorization code only once.
- Do not create an authenticated session until token validation succeeds.
