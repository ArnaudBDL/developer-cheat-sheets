# DNS : Reverse DNS

## Purpose

Reverse DNS maps an IP address to a domain name using PTR records.

## Reverse Namespaces

```text
IPv4  in-addr.arpa.
IPv6  ip6.arpa.
```

## IPv4 Example

```text
Address:      192.0.2.25
Reverse name: 25.2.0.192.in-addr.arpa.
```

```dns
25 IN PTR mail.example.com.
```

## Query Reverse DNS

```bash
dig -x 192.0.2.25
host 192.0.2.25
nslookup 192.0.2.25
```

## Forward-Confirmed Reverse DNS

```bash
ptr_name="$(dig +short -x 192.0.2.25 | sed 's/\.$//')"
dig +short "$ptr_name" A
```

The PTR target should resolve forward to the expected address when forward-confirmed reverse DNS is required.

## Delegation

Reverse zones are normally controlled by the address-space provider. For public addresses, request PTR management or delegation from the hosting or network provider.
