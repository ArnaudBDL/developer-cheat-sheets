# OpenID Connect : Claims

## Common Claims

```text
iss             Issuer identifier
sub             Subject identifier
aud             Intended audience
exp             Expiration time
iat             Issued-at time
auth_time       Time of End-User authentication
nonce           Value binding response to the initiating request
acr             Authentication Context Class Reference
amr             Authentication Methods References
azp             Authorized party
```

## Profile Claims

```text
name
family_name
given_name
preferred_username
email
email_verified
phone_number
address
```

- Request only claims required by the application.
- Treat claims as issuer assertions within their documented semantics.
- Distinguish absent claims from false or empty values.
- Do not infer authorization from profile claims alone.
- Apply privacy, minimization, retention and display rules to identity data.
