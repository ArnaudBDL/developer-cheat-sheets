# SSL and TLS : Private Keys

## Generate an RSA Key

```bash
openssl genpkey   -algorithm RSA   -pkeyopt rsa_keygen_bits:3072   -out private-key.pem
```

## Generate an EC Key

```bash
openssl genpkey   -algorithm EC   -pkeyopt ec_paramgen_curve:P-256   -out private-key.pem
```

## Generate an Encrypted Key

```bash
openssl genpkey   -algorithm RSA   -aes-256-cbc   -pkeyopt rsa_keygen_bits:3072   -out private-key-encrypted.pem
```

## Inspect and Validate

```bash
openssl pkey -in private-key.pem -check -noout
openssl pkey -in private-key.pem -pubout
openssl pkey -in private-key.pem -text -noout
```

## File Permissions

```bash
chmod 600 private-key.pem
chown root:root private-key.pem
```

## Compare a Key and Certificate

```bash
openssl pkey -in private-key.pem -pubout -outform DER | openssl sha256
openssl x509 -in certificate.pem -pubkey -noout |   openssl pkey -pubin -outform DER | openssl sha256
```

The two SHA-256 values must match.

## Key Security

- Never commit private keys to source control.
- Restrict filesystem access to the service account that needs the key.
- Avoid transmitting unencrypted private keys.
- Use a secrets manager, HSM or managed key service when appropriate.
- Replace the certificate and key immediately after suspected compromise.
