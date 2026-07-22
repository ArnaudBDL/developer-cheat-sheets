# Linux : Logs

## Journal

```bash
journalctl
journalctl -b
journalctl -b -1
journalctl -f
journalctl -p warning
journalctl --since today
journalctl --since '1 hour ago'
```

## Service Logs

```bash
journalctl -u service
journalctl -u service -f
journalctl -u service --since today
```

## Kernel Logs

```bash
journalctl -k
dmesg
dmesg --level=err,warn
dmesg -T
```

## Traditional Log Files

```bash
sudo tail -f /var/log/syslog
sudo tail -f /var/log/messages
sudo tail -f /var/log/auth.log
sudo tail -f /var/log/secure
```

## Disk Usage

```bash
journalctl --disk-usage
sudo du -sh /var/log/*
sudo logrotate -d /etc/logrotate.conf
```

## Filter

```bash
journalctl -g 'pattern'
grep -Rni 'error' /var/log
zgrep 'pattern' /var/log/application.log.*.gz
```
