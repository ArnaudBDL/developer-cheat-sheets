# Linux : Troubleshooting

## System Overview

```bash
uname -a
cat /etc/os-release
uptime
hostnamectl
systemctl --failed
journalctl -b -p warning
```

## CPU and Memory

```bash
top
ps -eo pid,user,%cpu,%mem,command --sort=-%cpu | head
free -h
vmstat 1
cat /proc/meminfo
```

## Storage

```bash
lsblk -f
df -hT
df -i
du -xhd1 /var | sort -h
findmnt
sudo dmesg --level=err,warn | grep -iE 'disk|I/O|nvme|ata'
```

## Services

```bash
systemctl status service
journalctl -u service -n 100
systemctl cat service
systemctl show service
```

## Network

```bash
ip -brief address
ip route
resolvectl status
ping -c 4 GATEWAY
getent hosts example.com
curl -Iv https://example.com
ss -lntup
```

## Boot

```bash
systemd-analyze
systemd-analyze blame
journalctl -b
journalctl -b -1
```

## Diagnostic Order

```text
1. Reproduce and record the exact failure.
2. Check system, service and kernel logs.
3. Confirm disk, memory and process state.
4. Verify configuration and permissions.
5. Test network layers independently.
6. Compare recent package or configuration changes.
7. Apply the smallest reversible correction.
8. Validate the service after correction.
```
