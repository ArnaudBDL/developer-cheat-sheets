# Certbot : Webroot

## Obtain a Certificate

```bash
sudo certbot certonly   --webroot   --webroot-path /var/www/example/public   -d example.com   -d www.example.com
```

## Validation Path

```text
http://example.com/.well-known/acme-challenge/TOKEN
```

## Checks

```bash
curl -I http://example.com/.well-known/acme-challenge/test-file
```

The web server must serve files from the specified webroot and permit the ACME challenge path. Verify reverse proxies, redirects, access rules and container mounts before requesting the certificate. Use the correct webroot for every domain included in the request.
