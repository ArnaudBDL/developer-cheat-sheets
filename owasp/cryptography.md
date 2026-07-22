# OWASP : Cryptography

## Data Classification

```text
Identify sensitive data.
Define retention and deletion requirements.
Determine protection in transit and at rest.
Minimize collection and storage.
```

## Controls

- Use maintained cryptographic libraries and approved algorithms.
- Enforce TLS for sensitive transport.
- Use authenticated encryption where confidentiality and integrity are required.
- Generate keys, tokens and nonces with a cryptographically secure random source.
- Store passwords using an adaptive password hashing function with unique salts.
- Keep keys separate from encrypted data and rotate them through a defined lifecycle.
- Never invent a cryptographic algorithm or protocol.
- Avoid sensitive data in URLs, logs, caches and error messages.

## Review Checklist

```text
Data inventory and classification
Transport encryption
Storage encryption
Password hashing
Key generation and storage
Rotation and revocation
Randomness
Certificate validation
Backup encryption
Sensitive-data deletion
```
