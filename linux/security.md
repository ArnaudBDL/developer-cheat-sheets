# Linux : Security

## Updates

```bash
sudo apt update && sudo apt upgrade
sudo dnf upgrade
sudo pacman -Syu
```

## Accounts and Privileges

```bash
getent passwd
getent group
sudo -l
sudo visudo
passwd
sudo passwd -l username
```

## Listening Services

```bash
sudo ss -lntup
systemctl --type=service --state=running
sudo lsof -nP -i
```

## Firewall

```bash
sudo nft list ruleset
sudo ufw status verbose
sudo firewall-cmd --list-all
```

## File Integrity and Permissions

```bash
find / -xdev -type f -perm -4000 -print 2>/dev/null
find / -xdev -type f -perm -2000 -print 2>/dev/null
find /etc -type f -writable -ls
stat /etc/passwd /etc/shadow
```

## MAC Systems

```bash
getenforce
sestatus
apparmor_status
```

## Checklist

- Apply supported security updates.
- Disable unused services and accounts.
- Use least privilege and audited `sudo` access.
- Restrict SSH and use key-based authentication where appropriate.
- Protect credentials, private keys and backups.
- Monitor authentication, service and kernel logs.
- Maintain tested recovery and backup procedures.
