# JWT : Structure

## Signed JWT

```text
BASE64URL(UTF8(header)).BASE64URL(payload).BASE64URL(signature)
```

```text
eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9
eyJzdWIiOiJ1c3JfNDIiLCJhdWQiOiJhcGkifQ
SIGNATURE
```

A signed JWT is commonly represented as three dot-separated parts: JOSE header, claims payload and signature. Base64url encoding is not encryption.

## Encrypted JWT

```text
protected-header.encrypted-key.initialization-vector.ciphertext.authentication-tag
```

A JWE compact serialization has five parts and provides confidentiality plus integrity when implemented correctly.

## Rules

- Treat a token as untrusted until all required validation succeeds.
- Do not place secrets in an ordinary signed JWT payload.
- Keep access tokens short-lived and purpose-specific.
- Use maintained JOSE libraries rather than implementing parsing or cryptography manually.

