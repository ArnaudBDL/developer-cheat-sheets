# Certbot : Security

## Protect

```text
Private keys
ACME account data
DNS API credentials
Renewal configuration
Hook scripts
Logs containing domain and path information
```

## Permissions

```bash
sudo find /etc/letsencrypt -maxdepth 2 -type d -ls
sudo stat /etc/letsencrypt/live/example.com/privkey.pem
```

## Controls

- Run Certbot with only the privileges required by the selected method.
- Restrict DNS credentials to the required zones and record operations.
- Keep private keys and ACME data out of repositories and images.
- Protect backups with encryption and access control.
- Review third-party plugins and their dependencies.
- Use tested deploy hooks and validate web-server configuration before reload.
- Revoke certificates after confirmed key compromise.
