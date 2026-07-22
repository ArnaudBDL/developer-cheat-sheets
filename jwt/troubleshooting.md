# JWT : Troubleshooting

## Signature Verification Failed

```text
Confirm issuer and environment.
Confirm the allowed algorithm.
Confirm kid resolves to the expected trusted key.
Check key rotation and cache age.
Compare the token bytes without trimming or rewriting them.
```

## Token Expired or Not Yet Valid

```text
Inspect exp, nbf and iat as NumericDate seconds.
Check issuer and recipient clock synchronization.
Review the explicitly configured clock tolerance.
Use the refresh or reauthentication flow rather than editing the token.
```

## Audience or Issuer Rejected

```text
Compare exact configured issuer values.
Confirm the current API is included in aud.
Do not reuse a token issued for another application or environment.
```

## 401 versus 403

```text
401  Token is missing, invalid, expired or otherwise unauthenticated.
403  Token is valid but the subject lacks permission for the operation.
```

## Safe Diagnostic Evidence

```text
Timestamp
Issuer
Audience
Algorithm
Key identifier
Validation stage
Error category
Correlation identifier
```

Do not place complete tokens, signatures, refresh tokens or private claims in tickets and logs. Redact or hash identifiers according to policy.

