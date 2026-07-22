# Networking : Firewalls

## Firewall Models

```text
Stateless filtering  Evaluates packets independently
Stateful filtering   Tracks connection state and return traffic
Host firewall        Protects one operating system
Network firewall     Filters traffic between networks or zones
Application firewall Applies application-aware policy
```

## Rule Fields

```text
Direction
Source address or zone
Destination address or zone
Protocol
Source and destination ports
Connection state
Action
Logging
Priority
```

## Linux Tools

```bash
sudo nft list ruleset
sudo iptables -L -n -v
sudo ufw status verbose
sudo firewall-cmd --list-all
```

## Rules

- Deny by default where operationally appropriate.
- Allow only required sources, destinations and services.
- Keep administrative interfaces on controlled paths.
- Log important denies without creating unusable noise.
- Review shadowed, duplicate and expired rules.
- Test both ingress and egress policy.
- Remember that an allowed port does not guarantee that an application is listening or healthy.
