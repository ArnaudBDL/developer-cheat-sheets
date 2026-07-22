# OpenID Connect : Troubleshooting

## Login Loop or Callback Failure

```text
Compare redirect_uri exactly with client registration.
Verify state storage and callback correlation.
Check browser cookie SameSite and Secure behavior.
Confirm authorization code is exchanged once.
Inspect provider and application clocks.
```

## ID Token Rejected

```text
Issuer mismatch
Audience or authorized-party mismatch
Expired token
Nonce mismatch
Unknown key identifier
Unsupported signing algorithm
Stale key-set cache during rotation
```

## UserInfo Failure

```text
Access token expired or wrong audience
Missing UserInfo scope or permission
UserInfo endpoint taken from incorrect metadata
Subject mismatch between ID token and UserInfo response
```

## Logout Failure

```text
Provider does not advertise end_session_endpoint
Post-logout redirect URI is not registered
ID-token hint does not match the session
Local session remains after provider logout
Provider session remains after local logout
```

## Safe Evidence

```text
Timestamp
Issuer
Client identifier
Flow and response type
Redirect URI identifier
HTTP status and protocol error
Token header algorithm and key identifier
Correlation identifier
```

Do not include complete tokens, codes, client secrets, session cookies or PKCE verifiers in logs and support tickets.
