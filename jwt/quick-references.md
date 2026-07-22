# JWT : Quick References

## Structure

```text
header.payload.signature

Registered claims:
iss  issuer
sub  subject
aud  audience
exp  expiration time
nbf  not before
iat  issued at
jti  token identifier
```

## Decode payload for inspection

```bash
TOKEN="HEADER.PAYLOAD.SIGNATURE"
echo "$TOKEN" | cut -d . -f 2 | base64 --decode
```

## Validation checklist

```text
Verify signature
Restrict accepted algorithms
Validate issuer and audience
Validate expiration and not-before
Use short-lived access tokens
Never store sensitive plaintext in payload
```
