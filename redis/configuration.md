# Redis : Configuration

## Common Configuration

```conf
bind 127.0.0.1 ::1
protected-mode yes
port 6379
timeout 0
tcp-keepalive 300
supervised systemd
dir /var/lib/redis
loglevel notice
logfile /var/log/redis/redis-server.log
```

## Memory Policy

```conf
maxmemory 1gb
maxmemory-policy allkeys-lru
```

## Inspect Runtime Configuration

```bash
redis-cli CONFIG GET '*'
redis-cli CONFIG GET maxmemory
redis-cli CONFIG GET maxmemory-policy
redis-cli INFO memory
```

## Change Runtime Configuration

```bash
redis-cli CONFIG SET maxmemory 1gb
redis-cli CONFIG SET maxmemory-policy allkeys-lru
redis-cli CONFIG REWRITE
```

## Validate and Restart

```bash
redis-server /etc/redis/redis.conf --test-memory 2
sudo systemctl restart redis-server
sudo journalctl -u redis-server -n 100
```
