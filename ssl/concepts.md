# SSL and TLS : Concepts

## Terminology

```text
SSL           Obsolete predecessor of TLS
TLS           Protocol securing data in transit
HTTPS         HTTP transported over TLS
X.509         Certificate format used by TLS PKI
PKI           Public Key Infrastructure
CA            Certificate Authority
CSR           Certificate Signing Request
SAN           Subject Alternative Name
SNI           Server Name Indication
ALPN          Application-Layer Protocol Negotiation
```

## TLS Provides

```text
Confidentiality  Encrypts data in transit
Integrity        Detects unauthorized modification
Authentication   Verifies server identity and optionally client identity
```

## TLS Handshake

```text
Client                               Server
  | -------- ClientHello ----------> |
  | <------- ServerHello ----------- |
  | <------- Certificate ----------- |
  | <------- Key agreement --------- |
  | -------- Key agreement --------> |
  | ===== Encrypted traffic ======== |
```

## Certificate Validation

A client commonly checks:

```text
Certificate validity period
Requested hostname in the SAN extension
Signature chain to a trusted root
Permitted certificate purpose
Key usage and extended key usage
Revocation information when supported
```

## TLS Versions

```text
SSL 2.0 / 3.0  Obsolete
TLS 1.0 / 1.1  Deprecated and disabled in modern deployments
TLS 1.2        Widely supported
TLS 1.3        Current modern protocol version
```

## Inspect a Live Connection

```bash
openssl s_client   -connect example.com:443   -servername example.com   -brief
```
