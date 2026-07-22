# SSL and TLS : Let’s Encrypt

## Certbot Commands

```bash
certbot --version
sudo certbot certificates
sudo certbot plugins
```

## Nginx

```bash
sudo certbot --nginx   -d example.com   -d www.example.com
```

## Apache

```bash
sudo certbot --apache   -d example.com   -d www.example.com
```

## Webroot

```bash
sudo certbot certonly   --webroot   --webroot-path /var/www/example.com/public   -d example.com   -d www.example.com
```

## Standalone

```bash
sudo certbot certonly   --standalone   -d example.com
```

The standalone authenticator must bind the validation port, so an existing listener may need to be stopped temporarily.

## Certificate Paths

```text
/etc/letsencrypt/live/example.com/cert.pem
/etc/letsencrypt/live/example.com/chain.pem
/etc/letsencrypt/live/example.com/fullchain.pem
/etc/letsencrypt/live/example.com/privkey.pem
```

## Test with the Staging Environment

```bash
sudo certbot certonly   --staging   --webroot   --webroot-path /var/www/example.com/public   -d example.com
```

Use staging while validating automation to avoid production rate limits.
