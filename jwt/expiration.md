# JWT : Expiration

## Temporal Claims

```json
{
  "iat": 1784717100,
  "nbf": 1784717100,
  "exp": 1784718000
}
```

JWT NumericDate values represent seconds from the Unix epoch.

## Validation

```text
Reject when current time is at or after exp.
Reject before nbf, subject to the configured clock tolerance.
Check iat when the application profile requires issuance-time constraints.
Keep clock tolerance small and explicitly configured.
```

## Lifecycle Rules

- Use short access-token lifetimes based on risk and user experience.
- Synchronize clocks on issuers and recipients.
- Do not extend a signed token by editing its payload.
- Issue a new token through the approved renewal flow.
- Consider key rotation and revocation windows when selecting token lifetime.

