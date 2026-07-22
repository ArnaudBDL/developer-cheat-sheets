# Networking : DNS

## Common Record Types

```text
A      Name to IPv4 address
AAAA   Name to IPv6 address
CNAME  Alias to another canonical name
MX     Mail exchanger
NS     Authoritative name server
TXT    Arbitrary text used by multiple protocols
SRV    Service location
PTR    Reverse lookup
SOA    Zone authority and timing information
CAA    Certificate authority authorization
```

## Resolution Path

```text
Application
-> local stub resolver and cache
-> recursive resolver
-> root servers
-> top-level-domain servers
-> authoritative server
```

## Tools

```bash
dig example.com A
dig example.com AAAA
dig example.com MX
dig +trace example.com
dig @1.1.1.1 example.com
host example.com
nslookup example.com
resolvectl query example.com
```

## Troubleshooting

- Distinguish authoritative failure from recursive resolver failure.
- Check record type, exact name and delegation.
- Inspect TTL and cached stale data.
- Compare answers from multiple resolvers only after identifying their roles.
- Verify DNSSEC validation where enabled.
- Test direct IP connectivity separately from name resolution.
