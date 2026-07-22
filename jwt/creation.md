# JWT : Creation

## Creation Flow

```text
Authenticate or validate the issuing event
Determine token type and intended audience
Build a minimal claims set
Set issuer and temporal claims
Generate a unique token identifier when required
Select the configured signing key and algorithm
Sign with a maintained JOSE library
Return through a protected channel
```

## Pseudocode

```typescript
const claims = {
  iss: trustedIssuer,
  sub: user.id,
  aud: apiAudience,
  iat: now,
  exp: now + accessTokenLifetime,
  jti: crypto.randomUUID(),
}

const token = await joseLibrary.sign(claims, signingKey, {
  algorithm: configuredAlgorithm,
  type: 'at+jwt',
  keyId: activeKeyId,
})
```

The example is library-agnostic pseudocode. Use the exact API and secure defaults of the chosen maintained library.

