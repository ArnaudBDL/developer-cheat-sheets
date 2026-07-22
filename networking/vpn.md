# Networking : VPN

## VPN Models

```text
Remote access  Connects an individual device to a private network
Site-to-site   Connects two network domains
Overlay VPN    Builds a logical private network over another network
```

## Common Technologies

```text
IPsec / IKEv2
WireGuard
OpenVPN
TLS-based enterprise VPNs
```

## Routing Modes

```text
Full tunnel   All client traffic uses the VPN
Split tunnel  Only selected prefixes use the VPN
```

## Checks

```text
Peer identity and authentication
Encryption and integrity algorithms
Allowed networks and traffic selectors
Routes installed on both ends
DNS behavior
MTU and fragmentation
NAT traversal
Firewall rules
Rekey and lifetime settings
```

A tunnel can be established while application traffic still fails because of routing, DNS, policy or MTU issues.
