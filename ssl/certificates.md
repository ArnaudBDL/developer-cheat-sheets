# SSL and TLS : Certificates

## Certificate Contents

```text
Subject
Issuer
Serial number
Validity period
Public key
Signature algorithm
Subject Alternative Names
Key Usage
Extended Key Usage
Authority and Subject Key Identifiers
CA constraints
```

## Inspect a PEM Certificate

```bash
openssl x509 -in certificate.pem -noout -text
openssl x509 -in certificate.pem -noout -subject
openssl x509 -in certificate.pem -noout -issuer
openssl x509 -in certificate.pem -noout -serial
openssl x509 -in certificate.pem -noout -dates
openssl x509 -in certificate.pem -noout -fingerprint -sha256
```

## Inspect Subject Alternative Names

```bash
openssl x509 -in certificate.pem -noout -ext subjectAltName
```

## Check Expiration

```bash
openssl x509 -in certificate.pem -noout -enddate
openssl x509 -in certificate.pem -checkend 2592000 -noout
```

`2592000` represents 30 days in seconds.

## Certificate Formats

```text
PEM      Base64 text with BEGIN / END markers
DER      Binary ASN.1 representation
PKCS#12  Binary bundle for certificates and private keys
PKCS#7   Certificate and chain container without private keys
```

## Convert Formats

```bash
# DER to PEM
openssl x509 -inform DER -in certificate.der -out certificate.pem

# PEM to DER
openssl x509 -outform DER -in certificate.pem -out certificate.der

# PEM certificate and key to PKCS#12
openssl pkcs12 -export   -out identity.p12   -inkey private-key.pem   -in certificate.pem   -certfile chain.pem

# Inspect PKCS#12
openssl pkcs12 -in identity.p12 -info -noout
```
