# DNS : Zones

## Zone Concepts

```text
Zone apex       Top name of the zone
Primary server  Source of writable zone data
Secondary       Receives zone data through transfer or provisioning
SOA record      Identifies zone authority and timing parameters
Zone transfer   Replicates zone data using AXFR or IXFR
```

A zone is an administrative portion of the namespace. A delegated child zone is managed separately from its parent.

## Minimal Zone File

```dns
$ORIGIN example.com.
$TTL 3600

@ IN SOA ns1.example.net. hostmaster.example.com. (
    2026072201 ; serial
    3600       ; refresh
    900        ; retry
    1209600    ; expire
    300        ; negative cache TTL
)

@    IN NS    ns1.example.net.
@    IN NS    ns2.example.net.
@    IN A     192.0.2.10
www  IN A     192.0.2.20
mail IN A     192.0.2.30
@    IN MX 10 mail.example.com.
```

## Validate a BIND Zone

```bash
named-checkzone example.com /etc/bind/zones/db.example.com
named-checkconf
```

## Inspect Zone Authority

```bash
dig example.com SOA
dig example.com NS
dig @ns1.example.net example.com SOA +norecurse
```

## Zone Transfer

```bash
dig @ns1.example.net example.com AXFR
dig @ns1.example.net example.com IXFR=2026072200
```

Zone transfers must be restricted to authorized secondary servers.
