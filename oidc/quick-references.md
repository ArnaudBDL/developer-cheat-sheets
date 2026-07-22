# OpenID Connect : Quick References

## Scopes and tokens

```text
openid   Required OIDC scope
profile  Standard profile claims
email    Email claims

ID token     Authentication information
Access token Authorization for APIs
```

## Discovery

```http
GET /.well-known/openid-configuration
```

## Validation checklist

```text
Verify signature against provider keys
Validate iss
Validate aud
Validate exp and nbf
Validate nonce when used
Do not use the ID token as an API access token
```
