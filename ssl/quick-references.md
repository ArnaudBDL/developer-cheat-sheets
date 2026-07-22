# SSL and TLS : Quick References

## Certificates

```bash
openssl x509 -in certificate.pem -text -noout
openssl x509 -in certificate.pem -noout -dates
openssl x509 -in certificate.pem -noout -subject -issuer
```

## Remote server

```bash
openssl s_client -connect example.com:443 -servername example.com
curl -Iv https://example.com
```

## Keys and CSR

```bash
openssl genpkey -algorithm RSA -out private.key -pkeyopt rsa_keygen_bits:2048
openssl req -new -key private.key -out request.csr
```
