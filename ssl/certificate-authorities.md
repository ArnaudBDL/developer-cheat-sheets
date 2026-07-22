# SSL and TLS : Certificate Authorities

## CA Roles

```text
Root CA          Trust anchor, usually self-signed and protected offline
Intermediate CA  Signs leaf certificates while isolating the root key
Issuing CA       Intermediate CA used for certificate issuance
Registration     Validates certificate request information
```

## Trust Stores

```text
Operating-system trust store
Browser-specific trust store
Application-specific trust store
Java trust store
Container image trust store
```

## Inspect a CA Certificate

```bash
openssl x509 -in ca-certificate.pem -noout -subject -issuer
openssl x509 -in ca-certificate.pem -noout -ext basicConstraints
openssl x509 -in ca-certificate.pem -noout -ext keyUsage
openssl x509 -in ca-certificate.pem -noout -fingerprint -sha256
```

## Verify Against a CA

```bash
openssl verify -CAfile root-ca.pem certificate.pem
openssl verify   -CAfile root-ca.pem   -untrusted intermediate-ca.pem   certificate.pem
```

## Local Trust Store

```bash
# Debian / Ubuntu
sudo cp private-root-ca.crt /usr/local/share/ca-certificates/
sudo update-ca-certificates

# Red Hat / Fedora
sudo cp private-root-ca.crt /etc/pki/ca-trust/source/anchors/
sudo update-ca-trust
```

## CA Security Principles

- Protect root and intermediate private keys.
- Keep the root CA offline where operationally possible.
- Limit CA certificate path length and permitted usages.
- Maintain issuance, revocation and audit procedures.
- Separate public trust from private organizational trust.
