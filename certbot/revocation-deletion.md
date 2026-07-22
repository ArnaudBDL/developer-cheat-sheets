# Certbot : Revocation and Deletion

## Revoke

```bash
sudo certbot revoke   --cert-path /etc/letsencrypt/live/example.com/cert.pem
```

## Delete a Managed Lineage

```bash
sudo certbot delete --cert-name example.com
```

## Inspect Before Deletion

```bash
sudo certbot certificates
grep -R '/etc/letsencrypt/live/example.com' /etc/nginx /etc/apache2 2>/dev/null
```

Revocation tells the certificate authority that a certificate should no longer be trusted. Deletion removes the Certbot-managed certificate lineage locally. Remove or replace all server references before deletion. Revoke promptly after confirmed private-key compromise, then issue new keys and certificates.
