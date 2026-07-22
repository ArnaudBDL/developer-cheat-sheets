# Nginx : Installation

## Debian and Ubuntu

```bash
sudo apt update
sudo apt install nginx
sudo systemctl enable --now nginx
sudo systemctl status nginx
```

## Red Hat and Fedora

```bash
sudo dnf install nginx
sudo systemctl enable --now nginx
sudo systemctl status nginx
```

## macOS

```bash
brew install nginx
brew services start nginx
brew services info nginx
```

## Verify

```bash
nginx -v
nginx -V
sudo nginx -t
curl -I http://localhost
```

## Service Management

```bash
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl reload nginx
```
