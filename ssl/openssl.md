# SSL and TLS : OpenSSL

## Version and Capabilities

```bash
openssl version
openssl version -a
openssl list -commands
openssl list -cipher-algorithms
openssl list -digest-algorithms
```

## Inspect Certificates

```bash
openssl x509 -in certificate.pem -noout -text
openssl x509 -in certificate.pem -noout -subject -issuer -dates
openssl x509 -in certificate.pem -noout -ext subjectAltName
```

## Inspect Keys and CSRs

```bash
openssl pkey -in private-key.pem -check -noout
openssl pkey -in private-key.pem -pubout
openssl req -in request.csr -noout -text
openssl req -in request.csr -noout -verify
```

## Test a TLS Server

```bash
openssl s_client -connect example.com:443 -servername example.com
openssl s_client -connect example.com:443 -servername example.com -brief
openssl s_client -connect example.com:443 -servername example.com -showcerts
openssl s_client -connect example.com:443 -servername example.com -tls1_2
openssl s_client -connect example.com:443 -servername example.com -tls1_3
```

## STARTTLS

```bash
openssl s_client -connect mail.example.com:25 -starttls smtp
openssl s_client -connect mail.example.com:143 -starttls imap
openssl s_client -connect directory.example.com:389 -starttls ldap
```

## Verify Certificates

```bash
openssl verify -CAfile root-ca.pem certificate.pem
openssl verify -CAfile root-ca.pem -untrusted intermediate-ca.pem certificate.pem
```

## Hash and Random Data

```bash
openssl dgst -sha256 file.bin
openssl rand -hex 32
openssl rand -base64 32
```
