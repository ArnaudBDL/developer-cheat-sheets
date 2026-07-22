# JWT : Signatures

## Signing Input

```text
BASE64URL(UTF8(protected-header)) + "." + BASE64URL(payload)
```

The signature protects integrity and authenticates the signer according to the selected algorithm and trusted key. It does not encrypt the claims.

## Verification Flow

```text
Parse compact serialization
Validate protected header
Select an explicitly allowed algorithm
Resolve a trusted verification key
Verify the cryptographic signature
Validate issuer, audience, time and application claims
Authorize the requested operation
```

## Key Management

- Generate keys with sufficient entropy.
- Separate signing keys by environment and trust domain.
- Rotate keys with an overlap period for still-valid tokens.
- Protect private and symmetric signing keys in an approved key-management service.
- Remove compromised keys and invalidate affected tokens through the incident process.

