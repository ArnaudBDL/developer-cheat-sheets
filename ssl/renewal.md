# SSL and TLS : Renewal

## Inspect Managed Certificates

```bash
sudo certbot certificates
```

## Test Renewal

```bash
sudo certbot renew --dry-run
```

## Run Renewal

```bash
sudo certbot renew
```

## Deployment Hooks

```bash
sudo certbot renew   --deploy-hook 'systemctl reload nginx'
```

```bash
sudo certbot renew   --pre-hook 'systemctl stop application'   --post-hook 'systemctl start application'
```

## Automated Renewal

```bash
systemctl list-timers | grep certbot
systemctl status certbot.timer
journalctl -u certbot.service
```

## Check Expiration

```bash
openssl x509   -in /etc/letsencrypt/live/example.com/cert.pem   -noout   -dates

openssl x509   -in /etc/letsencrypt/live/example.com/cert.pem   -checkend 2592000   -noout
```

## Renewal Checklist

- Test renewal before relying on automation.
- Confirm the validation method still works.
- Reload the service only after a successful renewal.
- Monitor expiration independently of the renewal job.
- Verify the live endpoint after deployment.
