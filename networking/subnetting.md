# Networking : Subnetting

## CIDR Basics

```text
/24 means 24 network bits and 8 host bits.
IPv4 address count = 2^(32 - prefix length).
```

## Common IPv4 Prefixes

```text
Prefix  Mask               Addresses  Traditional usable hosts
/24     255.255.255.0            256  254
/25     255.255.255.128          128  126
/26     255.255.255.192           64   62
/27     255.255.255.224           32   30
/28     255.255.255.240           16   14
/29     255.255.255.248            8    6
/30     255.255.255.252            4    2
/32     255.255.255.255            1    1 route
```

## Example

```text
Address:    192.168.10.70/26
Mask:       255.255.255.192
Block size: 64
Network:    192.168.10.64
Broadcast:  192.168.10.127
Hosts:      192.168.10.65 through 192.168.10.126
```

## Planning

```text
Required hosts
Growth allowance
Infrastructure addresses
Routing boundaries
Security zones
High availability
Cloud-provider reserved addresses
```

Point-to-point links, host routes and cloud networks can follow platform-specific allocation rules. Verify those rules before applying the traditional usable-host calculation.
