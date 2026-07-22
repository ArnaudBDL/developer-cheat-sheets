# Redis : Installation

## Debian and Ubuntu

```bash
sudo apt update
sudo apt install redis-server
sudo systemctl enable --now redis-server
sudo systemctl status redis-server
```

## Fedora

```bash
sudo dnf install redis
sudo systemctl enable --now redis
sudo systemctl status redis
```

## macOS

```bash
brew install redis
brew services start redis
brew services info redis
```

## Docker

```bash
docker run --name redis   --detach   --publish 127.0.0.1:6379:6379   redis:latest
```

## Verify

```bash
redis-server --version
redis-cli --version
redis-cli ping
redis-cli INFO server
```
