# MongoDB : Collections

## Create

```javascript
db.createCollection("users")
db.createCollection("events", { capped: true, size: 10485760 })
```

## Inspect and Rename

```javascript
show collections
db.getCollectionInfos()
db.users.stats()
db.users.renameCollection("accounts")
```

## Drop

```javascript
db.accounts.drop()
```

