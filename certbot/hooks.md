# Certbot : Hooks

## Hook Types

```text
pre-hook     Runs before renewal attempts that require action
post-hook    Runs after renewal processing
renew-hook   Alias retained for deploy-hook behavior
 deploy-hook Runs only after a successful certificate deployment or renewal
```

## Reload Nginx After Success

```bash
sudo certbot renew   --deploy-hook 'systemctl reload nginx'
```

## Executable Hook Directories

```text
/etc/letsencrypt/renewal-hooks/pre/
/etc/letsencrypt/renewal-hooks/deploy/
/etc/letsencrypt/renewal-hooks/post/
```

Hooks execute with elevated privileges in many deployments. Use root-owned executable files, absolute paths, strict permissions and idempotent commands. Never construct hooks from untrusted domain names or environment values.
