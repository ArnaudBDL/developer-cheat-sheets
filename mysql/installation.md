# MySQL : Installation

## Debian and Ubuntu

```bash
sudo apt update
sudo apt install mysql-server
sudo systemctl enable --now mysql
sudo systemctl status mysql
```

## Fedora

```bash
sudo dnf install community-mysql-server
sudo systemctl enable --now mysqld
sudo systemctl status mysqld
```

## macOS

```bash
brew install mysql
brew services start mysql
mysql --version
```

## Docker

```bash
docker run --name mysql --detach \
  --publish 127.0.0.1:3306:3306 \
  --env MYSQL_ROOT_PASSWORD='change-me' \
  --volume mysql-data:/var/lib/mysql \
  mysql:8.4
```

## Verify

```bash
mysql --version
mysqladmin --user=root --password ping
mysql --user=root --password
```
