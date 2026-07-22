# OAuth 2.0 : Token Introspection

## Purpose

Token introspection lets an authorized protected resource query the authorization server about a token's active state and metadata.

## Request

```http
POST /introspect HTTP/1.1
Authorization: Basic RESOURCE_SERVER_CREDENTIALS
Content-Type: application/x-www-form-urlencoded

token=ACCESS_TOKEN&token_type_hint=access_token
```

## Response

```json
{
  "active": true,
  "scope": "orders:read",
  "client_id": "client-123",
  "token_type": "Bearer",
  "exp": 1784718000
}
```

## Rules

- Authenticate and authorize introspection callers.
- Return `active: false` for invalid or inactive tokens without unnecessary disclosure.
- Protect the endpoint with TLS.
- Cache results only within an explicitly accepted revocation and freshness window.
- Enforce authorization at the resource server after introspection.
