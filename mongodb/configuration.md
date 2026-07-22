# MongoDB : Configuration

## Configuration File

```yaml
storage:
  dbPath: /var/lib/mongodb
systemLog:
  destination: file
  path: /var/log/mongodb/mongod.log
  logAppend: true
net:
  bindIp: 127.0.0.1
  port: 27017
processManagement:
  timeZoneInfo: /usr/share/zoneinfo
security:
  authorization: enabled
```

## Inspect

```bash
mongod --config /etc/mongod.conf
mongosh --eval 'db.adminCommand({ getCmdLineOpts: 1 })'
systemctl status mongod
journalctl -u mongod -n 100
```

