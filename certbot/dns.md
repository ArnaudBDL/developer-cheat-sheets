# Certbot : DNS Validation

## Purpose

```text
DNS validation proves control by publishing a TXT record beneath:
_acme-challenge.example.com
```

## Wildcard Certificate

```bash
sudo certbot certonly   --manual   --preferred-challenges dns   -d example.com   -d '*.example.com'
```

## Inspect TXT Record

```bash
dig TXT _acme-challenge.example.com
```

For unattended renewal, prefer a supported DNS provider plugin with narrowly scoped API credentials. Manual DNS validation is unsuitable for unattended renewal unless authentication hooks automate the record lifecycle. Wait for authoritative DNS visibility before continuing validation.
