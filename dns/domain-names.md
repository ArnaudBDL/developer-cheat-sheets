# DNS : Domain Names

## Name Structure

```text
www.api.example.com.
│   │   │       │
│   │   │       └── Root label
│   │   └────────── Top-level domain
│   └────────────── Registered domain label
└────────────────── Subdomain or host label
```

## FQDN

```text
example.com.       Absolute fully qualified domain name
example.com        Common presentation without the final root dot
www.example.com.   Absolute host name
```

## Labels

```text
A name consists of labels separated by dots.
Each label is limited to 63 octets.
A complete domain name is limited to 255 octets in DNS wire format.
DNS names are case-insensitive for comparison.
```

## Internationalized Domain Names

```text
Unicode display form  café.example
ASCII DNS form        xn--caf-dma.example
```

```bash
idn2 'café.example'
idn2 --decode 'xn--caf-dma.example'
```

## Inspect Names

```bash
dig +short example.com
dig +short www.example.com
dig example.com ANY
host example.com
```

## Naming Guidelines

- Use stable, meaningful names.
- Avoid embedding short-lived infrastructure details in public names.
- Keep service and environment conventions consistent.
- Account for certificates, email, reverse DNS and delegated subdomains.
