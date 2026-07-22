# MongoDB : Quick References

## Shell

```javascript
show dbs
use app
show collections
db.users.find({ active: true }).limit(20)
db.users.findOne({ email: "user@example.com" })
```

## CRUD

```javascript
db.users.insertOne({ name: "Ada", active: true })
db.users.updateOne({ _id: id }, { $set: { active: false } })
db.users.deleteOne({ _id: id })
```

## Indexes and aggregation

```javascript
db.users.createIndex({ email: 1 }, { unique: true })
db.orders.aggregate([
  { $group: { _id: "$status", total: { $sum: 1 } } }
])
```
