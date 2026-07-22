# MongoDB : Aggregation

## Pipeline

```javascript
db.orders.aggregate([
  { $match: { status: "paid" } },
  { $group: { _id: "$userId", total: { $sum: "$amount" }, count: { $sum: 1 } } },
  { $sort: { total: -1 } },
  { $limit: 10 }
])
```

## Lookup and Unwind

```javascript
db.orders.aggregate([
  { $unwind: "$lines" },
  { $lookup: {
      from: "users",
      localField: "userId",
      foreignField: "_id",
      as: "user"
  } },
  { $unwind: "$user" }
])
```

## Explain

```javascript
db.orders.explain("executionStats").aggregate([
  { $match: { status: "paid" } }
])
```

