# Linux : Installation

## Identify the System

```bash
uname -a
cat /etc/os-release
hostnamectl
lscpu
free -h
lsblk
```

## Prepare Installation Media

```bash
sha256sum linux-image.iso
sudo dd if=linux-image.iso of=/dev/sdX bs=4M status=progress conv=fsync
```

Replace `/dev/sdX` with the complete target device. This operation overwrites the selected device.

## Post-Installation Checks

```bash
sudo systemctl status
ip address
ip route
df -h
lsblk -f
sudo journalctl -b -p warning
```

## Update the System

```bash
# Debian / Ubuntu
sudo apt update
sudo apt upgrade

# Fedora
sudo dnf upgrade

# Arch Linux
sudo pacman -Syu
```

## Reboot and Shutdown

```bash
sudo systemctl reboot
sudo systemctl poweroff
sudo shutdown -r now
sudo shutdown -h now
```
