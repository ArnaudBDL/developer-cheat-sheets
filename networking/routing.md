# Networking : Routing

## Route Components

```text
Destination prefix
Next hop or gateway
Outgoing interface
Metric or administrative preference
Route source
```

## Longest Prefix Match

```text
10.0.0.0/8 via gateway A
10.10.0.0/16 via gateway B
10.10.20.0/24 via gateway C

Destination 10.10.20.42 uses gateway C.
```

## Linux Commands

```bash
ip route show
ip -6 route show
ip route get 203.0.113.10
sudo ip route add 10.20.0.0/16 via 192.168.1.1
sudo ip route del 10.20.0.0/16 via 192.168.1.1
```

## Route Types

```text
Connected route  Derived from a configured local interface
Static route     Configured manually
Default route    Used when no more specific route exists
Dynamic route    Learned through a routing protocol
```

When troubleshooting, verify the forward path and return path. Asymmetric routing can affect stateful firewalls and NAT devices.
