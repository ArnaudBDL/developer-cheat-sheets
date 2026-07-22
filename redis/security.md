# Redis : Security

## Network Exposure

```conf
bind 127.0.0.1 ::1
protected-mode yes
port 6379
```

Do not expose Redis directly to untrusted networks. Restrict access with network controls and host firewalls.

## ACL User

```redis
ACL SETUSER application on >strong-password ~application:* +@read +@write -@dangerous
ACL GETUSER application
ACL LIST
ACL WHOAMI
ACL DELUSER application
```

## Authenticate

```bash
redis-cli --user application --askpass
```

Avoid passing passwords directly on the command line because they may be exposed in shell history or process listings.

## TLS Connection

```bash
redis-cli --tls   --cacert /path/to/ca.crt   --cert /path/to/client.crt   --key /path/to/client.key
```

## Security Checklist

- Use ACL users with least-privilege key patterns and command categories.
- Protect configuration, persistence files and TLS private keys.
- Disable or restrict dangerous administrative commands through ACLs.
- Keep Redis and the operating system updated.
- Monitor authentication failures and configuration changes.
- Separate application, replication and administration credentials.
