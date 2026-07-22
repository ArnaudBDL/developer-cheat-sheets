# OpenID Connect : Discovery

## Provider Metadata

```text
Issuer-based discovery retrieves an OpenID Provider metadata document.
```

```text
https://identity.example.com/.well-known/openid-configuration
```

## Common Metadata

```text
issuer
authorization_endpoint
token_endpoint
userinfo_endpoint
jwks_uri
end_session_endpoint
scopes_supported
response_types_supported
subject_types_supported
id_token_signing_alg_values_supported
```

## Validation Rules

- Retrieve metadata only from the configured issuer trust boundary.
- Require the metadata `issuer` to match the expected issuer exactly.
- Use HTTPS in production trust configurations.
- Cache metadata and keys with bounded freshness and rotation handling.
- Do not accept endpoints substituted by untrusted user input.
- Validate signing algorithms against the Relying Party policy.
