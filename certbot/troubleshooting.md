# Certbot : Troubleshooting

## Baseline

```bash
certbot --version
sudo certbot plugins
sudo certbot certificates
sudo certbot renew --dry-run
```

## Logs

```bash
sudo less /var/log/letsencrypt/letsencrypt.log
sudo journalctl -u certbot.service
sudo journalctl -u certbot.timer
```

## HTTP Validation Checks

```bash
dig A example.com
dig AAAA example.com
curl -I http://example.com/.well-known/acme-challenge/test
sudo ss -lntp | grep ':80 '
```

## Common Causes

```text
DNS does not point to the validating server
IPv6 reaches a different or misconfigured server
Port 80 is blocked or redirected incorrectly
The webroot does not match the served document root
A standalone validation port is already in use
DNS TXT records are absent or stale
Plugin credentials are missing or insufficient
Web-server configuration cannot be reloaded
Renewal configuration references an obsolete plugin or path
```

Do not expose full DNS API credentials, private keys or ACME account data in support logs.
