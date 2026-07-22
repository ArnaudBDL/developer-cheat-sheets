# Certbot : Apache

## Validate Apache

```bash
sudo apachectl configtest
```

## Obtain and Install

```bash
sudo certbot --apache -d example.com -d www.example.com
```

## Obtain Only

```bash
sudo certbot certonly --apache -d example.com
```

## Post-Operation Checks

```bash
sudo apachectl configtest
sudo systemctl reload apache2
openssl s_client -connect example.com:443 -servername example.com
```

Back up Apache configuration before automatic modification. Verify the matching VirtualHost, inspect the resulting certificate paths, and confirm that renewal reloads the correct service.
