# Redis : Replication

## Configure a Replica

```conf
replicaof 10.0.0.10 6379
masteruser replication-user
masterauth strong-password
replica-read-only yes
```

## Runtime Commands

```redis
REPLICAOF 10.0.0.10 6379
REPLICAOF NO ONE
ROLE
```

## Inspect Replication

```bash
redis-cli INFO replication
redis-cli ROLE
redis-cli INFO stats
```

## Wait for Replicas

```redis
WAIT 1 1000
WAITAOF 1 1 1000
```

## Operational Checks

```text
Primary and replica link state
Replication offset and lag
Full versus partial synchronization
Authentication credentials
Network reachability
Disk and memory capacity
Read-only replica policy
```

Redis replication is asynchronous by default. Replication does not replace backups or a high-availability design.
