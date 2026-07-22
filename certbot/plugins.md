# Certbot : Plugins

## List Plugins

```bash
certbot plugins
```

## Plugin Roles

```text
Authenticator  Proves control of requested domain names
Installer      Configures a supported server to use the certificate
```

## Common Plugins

```text
apache
nginx
webroot
standalone
manual
dns-* provider plugins
```

Choose a plugin according to the web server, deployment architecture and available ACME challenge. Review third-party plugins before installation, pin approved versions where appropriate, and protect all DNS API credentials.
