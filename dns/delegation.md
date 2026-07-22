# DNS : Delegation

## Delegation Structure

```text
Parent zone
  ├── NS records for the child zone
  ├── DS record when DNSSEC is enabled
  └── Glue address records when required

Child zone
  ├── SOA record
  ├── Matching NS records
  └── Authoritative zone data
```

## Parent Delegation Example

```dns
sub.example.com. IN NS ns1.sub.example.com.
sub.example.com. IN NS ns2.provider.net.
ns1.sub.example.com. IN A 192.0.2.53
```

The address for `ns1.sub.example.com` is glue because that server name is inside the delegated child namespace.

## Child Zone Example

```dns
$ORIGIN sub.example.com.
@ IN SOA ns1.sub.example.com. hostmaster.sub.example.com. (
  2026072201 3600 900 1209600 300
)
@ IN NS ns1.sub.example.com.
@ IN NS ns2.provider.net.
```

## Inspect Delegation

```bash
dig sub.example.com NS
dig +trace sub.example.com
dig @PARENT_SERVER sub.example.com NS +norecurse
dig @CHILD_SERVER sub.example.com SOA +norecurse
```

## Delegation Checklist

- Parent and child NS sets should be consistent.
- Every authoritative server must answer for the child zone.
- Required glue records must be present and correct.
- Authoritative servers should be reachable over UDP and TCP port 53.
- DNSSEC requires a correct DS-to-DNSKEY chain.
