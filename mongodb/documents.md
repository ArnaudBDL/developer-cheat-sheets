# MongoDB : Documents

## Insert

```javascript
db.users.insertOne({
  email: "user@example.com",
  name: "User",
  active: true,
  roles: ["editor"],
  createdAt: new Date()
})

db.users.insertMany([
  { name: "Alice", active: true },
  { name: "Bob", active: false }
])
```

## BSON Values

```javascript
{
  _id: ObjectId(),
  text: "MongoDB",
  count: NumberInt(42),
  amount: Decimal128("19.95"),
  active: true,
  createdAt: new Date(),
  binary: BinData(0, "SGVsbG8=")
}
```

## Delete

```javascript
db.users.deleteOne({ _id: ObjectId("OBJECT_ID") })
db.users.deleteMany({ active: false })
```

