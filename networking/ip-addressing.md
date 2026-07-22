# Networking : IP Addressing

## IPv4

```text
Address length: 32 bits
Notation:       192.0.2.10
Prefix:         192.0.2.0/24
```

## Common IPv4 Ranges

```text
10.0.0.0/8        Private
172.16.0.0/12     Private
192.168.0.0/16    Private
127.0.0.0/8       Loopback
169.254.0.0/16    Link-local
224.0.0.0/4       Multicast
0.0.0.0/0         Default route or any IPv4 network
```

## IPv6

```text
Address length: 128 bits
Notation:       2001:db8:10::42
Prefix:         2001:db8:10::/64
Loopback:       ::1/128
Unspecified:    ::/128
Link-local:     fe80::/10
Unique local:   fc00::/7
Multicast:      ff00::/8
Default route:  ::/0
```

## IPv6 Compression

```text
2001:0db8:0000:0000:0000:0000:0000:0042
2001:db8::42
```

Use the prefix length with the address. An IP address alone does not identify the subnet boundary.
