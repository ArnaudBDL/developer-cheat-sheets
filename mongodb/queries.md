# MongoDB : Queries

## Find

```javascript
db.users.find({ active: true })
db.users.findOne({ email: "user@example.com" })
db.users.find({ age: { $gte: 18, $lt: 65 } })
db.users.find({ roles: "editor" })
```

## Projection and Sort

```javascript
db.users.find(
  { active: true },
  { name: 1, email: 1, _id: 0 }
).sort({ createdAt: -1 }).limit(20).skip(0)
```

## Operators

```javascript
db.users.find({
  $and: [
    { active: true },
    { $or: [{ role: "admin" }, { role: "editor" }] }
  ]
})

db.users.countDocuments({ active: true })
db.users.distinct("role")
```

