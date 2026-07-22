# Linux : Cron

## Edit and List Jobs

```bash
crontab -e
crontab -l
crontab -r
sudo crontab -u username -e
```

## Cron Format

```text
minute hour day-of-month month day-of-week command
```

```cron
# Every day at 02:30
30 2 * * * /usr/local/bin/backup.sh

# Every five minutes
*/5 * * * * /usr/local/bin/health-check.sh

# Monday to Friday at 08:00
0 8 * * 1-5 /usr/local/bin/report.sh
```

## Environment and Logging

```cron
SHELL=/bin/bash
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

0 3 * * * /usr/local/bin/job.sh >> /var/log/job.log 2>&1
```

## System Cron Locations

```text
/etc/crontab
/etc/cron.d/
/etc/cron.hourly/
/etc/cron.daily/
/etc/cron.weekly/
/etc/cron.monthly/
```

## Inspect the Service

```bash
systemctl status cron
systemctl status crond
journalctl -u cron
journalctl -u crond
```
