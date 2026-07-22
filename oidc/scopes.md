# OpenID Connect : Scopes

## Standard Scopes

```text
openid   Required to identify the request as OpenID Connect
profile  Requests common profile claims
email    Requests email and email_verified claims
address  Requests the address claim
phone    Requests phone_number and phone_number_verified claims
offline_access Requests conditions for offline access and refresh-token issuance
```

## Example

```text
scope=openid profile email
```

## Rules

- Always include `openid` for an OIDC request.
- Request the minimum identity information needed.
- Keep API authorization scopes distinct from identity scopes.
- Do not assume every requested claim will be returned.
- Apply consent and organizational policy to sensitive claims.
- Treat `offline_access` as a high-value capability requiring appropriate controls.
