# PHP : Installation

## Verify PHP

```bash
php --version
php --modules
php --ini
php --info
```

## macOS

```bash
brew install php
brew services start php
brew services info php
```

## Debian and Ubuntu

```bash
sudo apt update
sudo apt install php-cli php-fpm php-mbstring php-xml php-curl php-zip
php --version
```

## Fedora

```bash
sudo dnf install php-cli php-fpm php-mbstring php-xml php-curl php-zip
php --version
```

## Development Server

```bash
php -S 127.0.0.1:8000 -t public
```

## Configuration

```bash
php --ini
php -r 'echo php_ini_loaded_file(), PHP_EOL;'
php -i | grep memory_limit
php -d display_errors=1 script.php
```
