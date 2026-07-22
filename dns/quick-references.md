# DNS : Quick References

## Lookup

```bash
dig example.com
dig example.com A
dig example.com MX
dig example.com TXT
dig +short example.com
dig @1.1.1.1 example.com
```

## Diagnostics

```bash
nslookup example.com
host example.com
dig +trace example.com
dig -x 192.0.2.1
```

## Common records

```text
A      example.com -> IPv4
AAAA   example.com -> IPv6
CNAME  alias -> canonical name
MX     mail exchanger
TXT    verification and policy
NS     authoritative name server
```
