# Redis : Troubleshooting

## Connectivity

```bash
redis-cli ping
redis-cli -h HOST -p 6379 ping
nc -vz HOST 6379
ss -lntp | grep 6379
```

## Server Information

```bash
redis-cli INFO
redis-cli INFO server
redis-cli INFO clients
redis-cli INFO memory
redis-cli INFO persistence
redis-cli INFO replication
redis-cli INFO stats
redis-cli INFO keyspace
```

## Latency and Slow Commands

```bash
redis-cli --latency
redis-cli --latency-history
redis-cli LATENCY DOCTOR
redis-cli LATENCY LATEST
redis-cli SLOWLOG GET 20
redis-cli SLOWLOG LEN
```

## Memory

```bash
redis-cli INFO memory
redis-cli MEMORY STATS
redis-cli MEMORY DOCTOR
redis-cli MEMORY USAGE KEY
redis-cli CONFIG GET maxmemory
redis-cli CONFIG GET maxmemory-policy
```

## Common Problems

```text
Connection refused
  Check service state, bind address, port, firewall and container publishing.

NOAUTH or NOPERM
  Check ACL user, password, key pattern and permitted command categories.

OOM command not allowed
  Check maxmemory, eviction policy, dataset growth and large keys.

MISCONF write failure
  Check persistence errors, disk space, permissions and logs.

READONLY replica error
  Confirm the client is connected to the intended writable primary.

Replication link down
  Check authentication, network reachability, logs and primary availability.
```

## Logs and Service

```bash
systemctl status redis-server
journalctl -u redis-server -n 200
journalctl -u redis-server -f
tail -f /var/log/redis/redis-server.log
```

## Large Keys

```bash
redis-cli --bigkeys
redis-cli --memkeys
redis-cli SCAN 0 COUNT 100
```
