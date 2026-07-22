# OAuth 2.0 : Troubleshooting

## Authorization Request Fails

```text
Verify client_id.
Compare redirect_uri exactly with registration.
Check response_type and requested scopes.
Confirm state and PKCE values are preserved.
Inspect authorization-server error parameters safely.
```

## Token Exchange Fails

```text
invalid_grant
  Code expired, reused, issued to another client, redirect mismatch or PKCE failure.

invalid_client
  Client authentication missing or rejected.

invalid_scope
  Requested scope is unknown, malformed or not allowed.

unauthorized_client
  Client is not allowed to use the requested grant.
```

## Resource Server Returns 401 or 403

```text
401  Token missing, malformed, expired, inactive or invalid for this resource.
403  Token valid but insufficient permission for the operation or object.
```

## Safe Evidence

```text
Timestamp
Client identifier
Grant type
Authorization-server issuer
Redirect URI identifier without sensitive query values
Requested and granted scopes
HTTP status and OAuth error code
Correlation identifier
```

Never include complete access tokens, refresh tokens, authorization codes, client secrets or PKCE verifiers in logs or support tickets.
