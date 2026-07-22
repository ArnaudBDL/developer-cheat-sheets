# Apache : Installation

## Debian and Ubuntu

```bash
sudo apt update
sudo apt install apache2
sudo systemctl enable --now apache2
sudo systemctl status apache2
```

## Red Hat, Fedora and Rocky Linux

```bash
sudo dnf install httpd
sudo systemctl enable --now httpd
sudo systemctl status httpd
```

## macOS

```bash
brew install httpd
brew services start httpd
brew services info httpd
```

## Verify Installation

```bash
apachectl -v
apachectl -V
apachectl configtest
curl -I http://localhost
```

## Service Management

```bash
sudo systemctl start apache2
sudo systemctl stop apache2
sudo systemctl restart apache2
sudo systemctl reload apache2

sudo systemctl start httpd
sudo systemctl stop httpd
sudo systemctl restart httpd
sudo systemctl reload httpd
```

## Common Paths

```text
Debian / Ubuntu
  Configuration: /etc/apache2/
  Sites:         /etc/apache2/sites-available/
  Logs:          /var/log/apache2/
  Document root: /var/www/html/

Red Hat family
  Configuration: /etc/httpd/
  Includes:      /etc/httpd/conf.d/
  Logs:          /var/log/httpd/
  Document root: /var/www/html/
```
