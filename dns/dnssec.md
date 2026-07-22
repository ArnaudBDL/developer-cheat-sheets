# DNS : DNSSEC

## Purpose

DNSSEC adds origin authentication and integrity protection to DNS data. It does not encrypt DNS queries or responses.

## Core Records

```text
DNSKEY  Public key published in the signed zone
RRSIG   Signature over a resource-record set
DS      Digest of a child-zone key published in the parent
NSEC    Authenticated denial of existence
NSEC3   Hashed authenticated denial of existence
CDS     Child signal for DS automation
CDNSKEY Child DNSKEY signal for DS automation
```

## Chain of Trust

```text
Root trust anchor
      ↓ validates
TLD DS and DNSKEY
      ↓ validates
Child DS and DNSKEY
      ↓ validates
Signed resource records
```

## Query DNSSEC Data

```bash
dig example.com A +dnssec
dig example.com DNSKEY +dnssec
dig example.com DS +dnssec
dig example.com RRSIG +dnssec
dig +trace example.com +dnssec
```

## Validate

```bash
delv example.com A
kdig example.com A +dnssec
```

## Common Failure Causes

```text
Parent DS does not match the child DNSKEY
Expired or not-yet-valid RRSIG
Unsigned records in a signed zone
Incorrect denial-of-existence records
Clock skew on validators or signers
Broken key rollover
```

## Operational Checklist

- Monitor signature validity and expiration.
- Coordinate key rollover with parent DS updates.
- Confirm all authoritative servers serve consistent signed data.
- Preserve private signing keys securely.
- Test from validating recursive resolvers.
