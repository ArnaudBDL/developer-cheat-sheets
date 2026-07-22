# Certbot : Standalone

## Obtain a Certificate

```bash
sudo certbot certonly --standalone -d example.com
```

## Port Check

```bash
sudo ss -lntp | grep ':80 '
```

## Service Interruption Pattern

```bash
sudo systemctl stop nginx
sudo certbot certonly --standalone -d example.com
sudo systemctl start nginx
```

The standalone authenticator starts a temporary server for validation and therefore requires the validation port to be available and reachable. Prefer a method that avoids downtime when operating a production service. Automate any required stop and start operations with tested hooks.
