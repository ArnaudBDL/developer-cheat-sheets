# MongoDB : Troubleshooting

## Connectivity

```bash
mongosh "$MONGODB_URI" --eval 'db.runCommand({ ping: 1 })'
nc -vz HOST 27017
ss -lntp | grep 27017
```

## Service and Logs

```bash
systemctl status mongod
journalctl -u mongod -n 200
journalctl -u mongod -f
tail -f /var/log/mongodb/mongod.log
```

## Diagnostics

```javascript
db.serverStatus()
db.currentOp()
db.stats()
db.users.stats()
db.users.validate({ full: true })
rs.status()
```

## Common Problems

```text
Connection refused
  Check service state, bindIp, port, firewall and container publishing.

Authentication failed
  Check username, password, authentication database, mechanism and roles.

Not primary
  Check replica-set state and connect using a replica-set URI.

Duplicate key
  Inspect unique indexes and the conflicting field value.

Slow query
  Run explain("executionStats"), inspect indexes and review the profiler carefully.

Disk or storage errors
  Check free space, inode availability, permissions, logs and storage health.
```

