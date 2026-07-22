# Networking : Models

## OSI Model

```text
7  Application   User-facing network protocols and services
6  Presentation  Encoding, serialization, compression, encryption
5  Session       Session establishment, maintenance and termination
4  Transport     End-to-end delivery, ports, reliability and flow control
3  Network       Logical addressing and routing between networks
2  Data Link     Frames, MAC addressing and local network delivery
1  Physical      Signals, cables, radio and physical interfaces
```

## TCP/IP Model

```text
Application  HTTP, DNS, DHCP, SSH, SMTP
Transport    TCP, UDP, QUIC
Internet     IPv4, IPv6, ICMP, IPsec
Link         Ethernet, Wi-Fi, ARP, NDP
```

## Encapsulation

```text
Application data
-> Transport segment or datagram
-> IP packet
-> Link-layer frame
-> Physical signal
```

The models are conceptual tools for locating responsibilities and troubleshooting network paths. Real protocols can span or blur model boundaries.
