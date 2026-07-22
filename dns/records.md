# DNS : Records

## Common Record Types

```text
A       IPv4 address
AAAA    IPv6 address
CNAME   Alias to a canonical name
MX      Mail exchanger with preference
NS      Authoritative name server
TXT     Text, validation and policy data
PTR     Reverse mapping
SOA     Zone authority and timing data
SRV     Service location
CAA     Permitted certificate authorities
DNSKEY  DNSSEC public key
DS      Delegation signer in the parent zone
RRSIG   DNSSEC signature
NSEC    Authenticated denial of existence
NSEC3   Hashed authenticated denial of existence
```

## Record Examples

```dns
@      3600 IN A     192.0.2.10
@      3600 IN AAAA  2001:db8::10
www    3600 IN CNAME example.com.
@      3600 IN MX 10 mail.example.com.
@      3600 IN TXT   "v=spf1 mx -all"
_sip._tcp 3600 IN SRV 10 5 5060 sip.example.com.
@      3600 IN CAA 0 issue "letsencrypt.org"
```

## Query Records

```bash
dig example.com A
dig example.com AAAA
dig example.com MX
dig example.com TXT
dig example.com CAA
dig _sip._tcp.example.com SRV
```

## Record Fields

```text
Owner name   Name to which the record belongs
TTL          Cache lifetime in seconds
Class        Usually IN for Internet
Type         Record type such as A or MX
RDATA        Type-specific record data
```

## CNAME Constraints

A CNAME owner normally must not have other data at the same name. Use the zone apex records supported by the authoritative provider rather than placing a conventional CNAME at the apex.
