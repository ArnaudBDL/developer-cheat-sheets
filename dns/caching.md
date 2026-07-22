# DNS : Caching

## TTL

TTL defines how long a resolver may cache a DNS record before it should query again.

```dns
www 300 IN A 192.0.2.20
```

## Positive and Negative Caching

```text
Positive cache  Stores successful record answers
Negative cache  Stores authenticated absence such as NXDOMAIN or NODATA
```

## Inspect TTL

```bash
dig example.com A
dig example.com A +noall +answer
watch -n 5 'dig example.com A +noall +answer'
```

## Flush Local Caches

```bash
# systemd-resolved
sudo resolvectl flush-caches

# dnsmasq
sudo systemctl restart dnsmasq

# macOS
sudo dscacheutil -flushcache
sudo killall -HUP mDNSResponder

# Windows
ipconfig /flushdns
```

## Change Planning

```text
1. Reduce TTL before a planned migration.
2. Wait for the previous TTL to expire.
3. Change the record.
4. Validate authoritative and recursive answers.
5. Restore the normal TTL after stabilization.
```

DNS has no universal instant purge. Caches expire according to TTL and resolver policy.
