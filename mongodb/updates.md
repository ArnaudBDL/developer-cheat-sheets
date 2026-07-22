# MongoDB : Updates

## Update Documents

```javascript
db.users.updateOne(
  { email: "user@example.com" },
  { $set: { active: true }, $inc: { loginCount: 1 } }
)

db.users.updateMany(
  { active: false },
  { $set: { archived: true } }
)
```

## Arrays

```javascript
db.users.updateOne(
  { _id: ObjectId("OBJECT_ID") },
  { $addToSet: { roles: "reviewer" } }
)

db.users.updateOne(
  { _id: ObjectId("OBJECT_ID") },
  { $pull: { roles: "obsolete" } }
)
```

## Replace and Upsert

```javascript
db.users.replaceOne({ _id: id }, replacement)
db.settings.updateOne(
  { name: "theme" },
  { $set: { value: "dark" } },
  { upsert: true }
)
```

