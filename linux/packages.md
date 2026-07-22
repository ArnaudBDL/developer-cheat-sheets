# Linux : Packages

## Debian and Ubuntu

```bash
sudo apt update
sudo apt install package
sudo apt remove package
sudo apt purge package
sudo apt upgrade
apt search package
apt show package
dpkg -l
dpkg -S /path/to/file
```

## Fedora and Red Hat

```bash
sudo dnf install package
sudo dnf remove package
sudo dnf upgrade
dnf search package
dnf info package
rpm -qa
rpm -qf /path/to/file
```

## Arch Linux

```bash
sudo pacman -Syu
sudo pacman -S package
sudo pacman -R package
pacman -Ss package
pacman -Si package
pacman -Q
pacman -Qo /path/to/file
```

## Package Files

```bash
dpkg -L package
rpm -ql package
pacman -Ql package
```

## Cleanup

```bash
sudo apt autoremove
sudo dnf autoremove
sudo pacman -Sc
```
