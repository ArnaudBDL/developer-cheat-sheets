# Certbot : Renewal

## Renew Due Certificates

```bash
sudo certbot renew
```

## Dry Run

```bash
sudo certbot renew --dry-run
```

## Automation Inspection

```bash
systemctl list-timers | grep certbot
systemctl status certbot.timer
```

## Checks

```bash
sudo certbot certificates
sudo journalctl -u certbot.service
```

Certbot reuses saved renewal configuration for managed certificate lineages. Test renewal after changing plugins, credentials, webroots, server configuration or hooks. Do not use forced renewal as a routine monitoring check because certificate authorities apply issuance limits.
