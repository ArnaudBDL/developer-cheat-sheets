# Power BI : Gateways

## Purpose

```text
The on-premises data gateway connects supported Microsoft cloud services to
on-premises or otherwise privately reachable data sources.
```

## Operational Areas

```text
Gateway installation and recovery key
Cluster membership and high availability
Data-source definitions
Credentials
Drivers and connectors
Service accounts
Network egress
Logs and monitoring
Version management
```

## Rules

- Install gateways on supported, always-available machines.
- Use clusters where availability requirements justify them.
- Keep drivers consistent across cluster members.
- Restrict administrative access.
- Protect the recovery key.
- Map semantic-model connections to the correct gateway data source.
- Monitor resource saturation, connectivity and refresh failures.
