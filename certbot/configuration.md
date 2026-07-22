# Certbot : Configuration

## Main Directories

```text
/etc/letsencrypt/              Main configuration and certificate data
/etc/letsencrypt/live/         Stable links to current certificate files
/etc/letsencrypt/archive/      Certificate versions
/etc/letsencrypt/renewal/      Renewal configuration files
/var/log/letsencrypt/          Logs
/var/lib/letsencrypt/          Working data
```

## CLI Configuration

```bash
certbot --help all
certbot plugins
certbot certificates
```

## Rules

- Treat `/etc/letsencrypt` as sensitive data.
- Do not edit renewal configuration files casually.
- Back up certificate configuration and account data securely.
- Keep credentials for DNS plugins outside source control.
- Verify permissions before allowing another service to read private keys.
- Prefer command-line options or documented configuration mechanisms over ad hoc file changes.
