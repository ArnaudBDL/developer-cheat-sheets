# JWT : Algorithms

## Algorithm Families

```text
HS256 / HS384 / HS512  HMAC with a shared symmetric secret
RS256 / RS384 / RS512  RSA PKCS #1 v1.5 signatures
PS256 / PS384 / PS512  RSA-PSS signatures
ES256 / ES384 / ES512  ECDSA signatures
EdDSA                 Edwards-curve signatures where supported
```

## Selection

```text
Symmetric signing
  Issuer and every verifier share the same secret.

Asymmetric signing
  Issuer holds the private key and recipients use public verification keys.
```

## Rules

- Configure an algorithm allowlist per token type.
- Do not mix symmetric and asymmetric expectations for the same validation path.
- Use algorithms and key sizes approved by the organization and protocol profile.
- Reject unsupported, weak or unexpected algorithms.
- Validate every cryptographic operation and input.
- Plan algorithm and key migration before expiration or deprecation.

