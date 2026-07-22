# Networking : Troubleshooting

## Layered Workflow

```text
1. Define the exact source, destination, protocol and expected result.
2. Verify local interface state and addressing.
3. Verify local routes and selected next hop.
4. Verify neighbor resolution on the local link.
5. Test IP reachability without relying on DNS.
6. Test DNS separately.
7. Confirm the destination service is listening.
8. Check host and network firewall policy.
9. Inspect NAT, load balancer, proxy and VPN behavior.
10. Capture packets at the relevant boundaries.
11. Compare forward and return paths.
12. Check application and infrastructure logs.
```

## Fast Command Set

```bash
ip address show
ip route show
ip neigh show
ping -c 4 GATEWAY_IP
ping -c 4 DESTINATION_IP
dig DESTINATION_NAME
ss -lntup
curl -v https://DESTINATION_NAME
traceroute DESTINATION_IP
sudo tcpdump -ni any host DESTINATION_IP
```

## Symptom Mapping

```text
No link
  Interface, cable, radio, switch port or driver.

Self-assigned IPv4 address
  DHCP reachability, relay, scope or server.

IP works but name fails
  Resolver configuration, DNS records, delegation or filtering.

Connection refused
  Host reachable but no listener, or an active reject policy.

Connection timeout
  Routing, filtering, NAT, return path or silent service failure.

TLS failure
  Certificate, hostname, trust chain, protocol version or interception.

Intermittent failure
  Packet loss, MTU, load balancing, state exhaustion, roaming or unstable dependency.
```

Change one variable at a time and record timestamps, addresses, routes, commands and packet evidence before applying a fix.
