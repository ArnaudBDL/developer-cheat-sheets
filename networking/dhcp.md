# Networking : DHCP

## DHCPv4 DORA

```text
Discover  Client locates DHCP servers
Offer     Server proposes configuration
Request   Client requests one offered lease
Acknowledge Server confirms the lease
```

## Typical Lease Data

```text
IPv4 address
Subnet mask or prefix
Default gateway
DNS servers
Lease duration
Domain search information
NTP or other supported options
```

## Linux Commands

```bash
ip address show
ip route show
resolvectl status
networkctl status
journalctl -u NetworkManager
journalctl -u systemd-networkd
```

## Troubleshooting

```text
Verify physical or wireless link.
Confirm the client broadcasts reach a DHCP server or relay.
Check scope exhaustion and exclusions.
Check reservations and duplicate addresses.
Verify relay configuration and VLAN association.
Inspect lease time and server logs.
```

DHCPv6 and IPv6 Router Advertisements have different responsibilities depending on the deployment. Do not assume the IPv4 DORA process applies unchanged to IPv6.
