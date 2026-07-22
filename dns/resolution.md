# DNS : Resolution

## Recursive Resolution

```text
1. Client asks a recursive resolver.
2. Resolver checks its cache.
3. Resolver queries a root server.
4. Root refers it to the relevant TLD.
5. TLD refers it to the authoritative servers.
6. Authoritative server returns the requested data.
7. Resolver caches and returns the answer.
```

## Query Types

```text
Recursive query   Requests a final answer from a recursive resolver
Iterative query   Returns the best answer or referral available
Authoritative     Answer comes from a server authoritative for the zone
Non-authoritative Answer commonly comes from recursive cache
```

## Trace Resolution

```bash
dig +trace example.com
dig example.com A
dig @1.1.1.1 example.com A
dig @AUTHORITATIVE_SERVER example.com A +norecurse
```

## Response Flags

```text
qr  Query or response
aa  Authoritative answer
tc  Truncated response
rd  Recursion desired
ra  Recursion available
ad  Authenticated data
cd  Checking disabled
```

## Response Codes

```text
NOERROR   Query processed without DNS error
FORMERR   Malformed query
SERVFAIL  Server failed to complete resolution
NXDOMAIN  Queried name does not exist
NOTIMP    Operation not implemented
REFUSED   Server refused the operation
```

## TCP Fallback

```bash
dig example.com A +tcp
```
