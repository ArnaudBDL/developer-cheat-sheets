# Networking : NAT

## NAT Types

```text
SNAT  Changes the source address, commonly for outbound traffic
DNAT  Changes the destination address, commonly for inbound publishing
PAT   Translates addresses and transport ports for many-to-one sharing
Static NAT   Fixed one-to-one mapping
Dynamic NAT  Mapping selected from an address pool
```

## Flow Example

```text
Before SNAT
192.168.10.42:53000 -> 198.51.100.20:443

After SNAT
203.0.113.5:61042 -> 198.51.100.20:443
```

## Linux Inspection

```bash
sudo nft list ruleset
sudo iptables -t nat -L -n -v
sudo conntrack -L
```

## Rules

- NAT is address translation, not a complete security policy.
- Preserve state capacity for concurrent translations.
- Document inbound mappings and outbound egress addresses.
- Verify return routing through the translating device.
- Prefer native IPv6 connectivity and security policy rather than reproducing IPv4 address scarcity patterns unnecessarily.
