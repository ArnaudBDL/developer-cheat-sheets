# DNS : Security

## Primary Risks

```text
Cache poisoning
Spoofed DNS answers
Unauthorized zone transfer
Open-rec resolver abuse
DNS amplification
Domain hijacking
Misconfigured delegation
DNS tunnelling and exfiltration
Resolver privacy exposure
```

## Authoritative Server Controls

- Disable recursion on public authoritative-only servers.
- Restrict AXFR and IXFR to authorized secondary servers.
- Keep parent and child delegation consistent.
- Use separate infrastructure for recursive and authoritative roles.
- Apply response-rate limiting where operationally appropriate.
- Monitor record, delegation and registrar changes.

## Recursive Resolver Controls

- Restrict recursion to intended clients.
- Keep resolver software updated.
- Enable DNSSEC validation.
- Apply query logging with appropriate privacy and retention controls.
- Limit exposure of management interfaces.

## Domain Protection

```text
Strong registrar authentication
Registrar or registry lock where available
Controlled DNS-provider access
Change approval for critical records
Independent monitoring of NS, DS, MX and address records
Recovery contacts and documented ownership
```

## Inspect Exposure

```bash
dig @SERVER example.com AXFR
dig @SERVER unrelated-domain.example A
dig @SERVER version.bind CHAOS TXT
nmap -sU -sT -p 53 SERVER
```

Use inspection commands only on infrastructure you own or are authorized to assess.

## Encrypted DNS

DoT, DoH and DoQ protect DNS transport between supported clients and resolvers. They do not replace DNSSEC validation of DNS data authenticity.
