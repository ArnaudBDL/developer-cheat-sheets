# Certbot : Nginx

## Validate Nginx

```bash
sudo nginx -t
```

## Obtain and Install

```bash
sudo certbot --nginx -d example.com -d www.example.com
```

## Obtain Only

```bash
sudo certbot certonly --nginx -d example.com
```

## Post-Operation Checks

```bash
sudo nginx -t
sudo systemctl reload nginx
openssl s_client -connect example.com:443 -servername example.com
```

Back up Nginx configuration before automatic modification. Confirm that the correct `server_name` exists, inspect the resulting TLS configuration, and test renewal without forcing production issuance.
