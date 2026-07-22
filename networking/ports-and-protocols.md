# Networking : Ports and Protocols

## Transport Protocols

```text
TCP   Connection-oriented byte stream with ordered reliable delivery
UDP   Connectionless datagrams with application-managed reliability
QUIC  Secure multiplexed transport implemented over UDP
ICMP  Network control and diagnostic messages, without application ports
```

## Common Ports

```text
20/21 TCP   FTP data and control
22 TCP      SSH
25 TCP      SMTP
53 TCP/UDP  DNS
67/68 UDP   DHCPv4 server and client
80 TCP      HTTP
123 UDP     NTP
143 TCP     IMAP
161/162 UDP SNMP queries and traps
389 TCP/UDP LDAP
443 TCP     HTTPS
443 UDP     HTTP/3 over QUIC
445 TCP     SMB
465 TCP     Implicit TLS SMTP submission where supported
587 TCP     Message submission
636 TCP     LDAP over TLS
993 TCP     IMAP over TLS
995 TCP     POP3 over TLS
3306 TCP    MySQL
5432 TCP    PostgreSQL
6379 TCP    Redis
```

## Port Ranges

```text
0-1023       System or well-known ports
1024-49151   User or registered ports
49152-65535  Dynamic or private ports
```

A port identifies a transport endpoint on a host. Firewall policy should consider protocol, source, destination, direction and state, not only the port number.
