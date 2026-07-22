# SSL and TLS : Certificate Chains

## Chain Structure

```text
Leaf certificate
      ↓ signed by
Intermediate CA certificate
      ↓ signed by
Root CA certificate
      ↓ trusted by
Client trust store
```

## Create a Full Chain File

```bash
cat certificate.pem intermediate-ca.pem > fullchain.pem
```

The server normally presents the leaf certificate followed by required intermediate certificates. The trusted root is normally supplied by the client trust store.

## Inspect the Presented Chain

```bash
openssl s_client   -connect example.com:443   -servername example.com   -showcerts </dev/null
```

## Verify a Chain

```bash
openssl verify   -CAfile root-ca.pem   -untrusted intermediate-ca.pem   certificate.pem
```

## Verify a Live Server

```bash
openssl s_client   -connect example.com:443   -servername example.com   -verify_hostname example.com   -verify_return_error </dev/null
```

## Inspect Issuer Relationships

```bash
openssl x509 -in certificate.pem -noout -subject -issuer
openssl x509 -in intermediate-ca.pem -noout -subject -issuer
openssl x509 -in root-ca.pem -noout -subject -issuer
```

## Common Chain Problems

```text
Missing intermediate certificate
Incorrect intermediate certificate
Wrong chain order
Untrusted private root
Expired leaf or intermediate certificate
Hostname absent from Subject Alternative Names
```
