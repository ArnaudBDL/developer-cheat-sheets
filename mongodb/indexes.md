# MongoDB : Indexes

## Create

```javascript
db.users.createIndex({ email: 1 }, { unique: true })
db.orders.createIndex({ userId: 1, createdAt: -1 })
db.users.createIndex({ active: 1 }, { partialFilterExpression: { active: true } })
```

## Inspect

```javascript
db.users.getIndexes()
db.users.totalIndexSize()
db.users.find({ email: "user@example.com" }).explain("executionStats")
```

## Drop

```javascript
db.users.dropIndex("email_1")
db.users.dropIndexes()
```

