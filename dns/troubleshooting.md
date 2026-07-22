# DNS : Troubleshooting

## Diagnostic Order

```text
1. Confirm network reachability.
2. Inspect local resolver configuration.
3. Query the configured recursive resolver.
4. Compare with another resolver.
5. Trace delegation from the root.
6. Query authoritative servers directly.
7. Check record values and TTLs.
8. Validate DNSSEC when enabled.
9. Inspect server logs and packet captures.
```

## Local Resolver

```bash
cat /etc/resolv.conf
resolvectl status
scutil --dns
ipconfig /all
```

## Compare Answers

```bash
dig example.com A
dig @1.1.1.1 example.com A
dig @8.8.8.8 example.com A
dig @AUTHORITATIVE_SERVER example.com A +norecurse
```

## Trace Delegation

```bash
dig +trace example.com
dig example.com NS
dig example.com SOA
dig @PARENT_SERVER example.com NS +norecurse
```

## Check UDP and TCP

```bash
dig @DNS_SERVER example.com A
dig @DNS_SERVER example.com A +tcp
nc -vz DNS_SERVER 53
nc -vzu DNS_SERVER 53
```

## Common Responses

```text
NXDOMAIN  The queried name does not exist.
NODATA    The name exists but has no record of the requested type.
SERVFAIL  Resolution failed, often because of upstream or DNSSEC issues.
REFUSED   The server policy refuses the query or operation.
Timeout   Reachability, firewall, overload or server availability issue.
```

## DNSSEC Diagnostics

```bash
dig example.com A +dnssec
dig example.com DS +dnssec
dig example.com DNSKEY +dnssec
delv example.com A
```

## Packet Capture

```bash
sudo tcpdump -ni any 'udp port 53 or tcp port 53'
sudo tcpdump -ni INTERFACE host DNS_SERVER and port 53
```

## Typical Problems

```text
Stale answer              Cached record has not expired.
Inconsistent answer       Authoritative servers serve different zone data.
Missing child delegation  Parent NS records are absent or incorrect.
Lame delegation           Listed server is not authoritative for the zone.
Missing glue              In-bailiwick server address cannot be discovered.
Broken DNSSEC             DS, DNSKEY or signatures do not validate.
UDP works, TCP fails      Firewall blocks TCP port 53.
```
