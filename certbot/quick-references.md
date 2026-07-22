# Certbot : Quick References

## Certificates

```bash
sudo certbot certificates
sudo certbot --nginx -d example.com -d www.example.com
sudo certbot --apache -d example.com -d www.example.com
sudo certbot certonly --webroot -w /var/www/example/public -d example.com
sudo certbot certonly --standalone -d example.com
```

## Renewal

```bash
sudo certbot renew
sudo certbot renew --dry-run
systemctl status certbot.timer
```

## Management

```bash
sudo certbot plugins
sudo certbot revoke --cert-path /etc/letsencrypt/live/example.com/cert.pem
sudo certbot delete --cert-name example.com
```

## Files

```text
/etc/letsencrypt/live/CERT_NAME/fullchain.pem
/etc/letsencrypt/live/CERT_NAME/privkey.pem
/etc/letsencrypt/renewal/CERT_NAME.conf
/var/log/letsencrypt/letsencrypt.log
```
