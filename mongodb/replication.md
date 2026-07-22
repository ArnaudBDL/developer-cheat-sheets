# MongoDB : Replication

## Replica Set Configuration

```yaml
replication:
  replSetName: rs0
```

## Initialize

```javascript
rs.initiate({
  _id: "rs0",
  members: [
    { _id: 0, host: "mongo1:27017" },
    { _id: 1, host: "mongo2:27017" },
    { _id: 2, host: "mongo3:27017" }
  ]
})
```

## Inspect

```javascript
rs.status()
rs.conf()
rs.printReplicationInfo()
rs.printSecondaryReplicationInfo()
db.hello()
```

