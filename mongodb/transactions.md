# MongoDB : Transactions

## Transaction

```javascript
const session = db.getMongo().startSession()
const database = session.getDatabase("application")

session.startTransaction()
try {
  database.accounts.updateOne({ _id: 1 }, { $inc: { balance: -100 } })
  database.accounts.updateOne({ _id: 2 }, { $inc: { balance: 100 } })
  session.commitTransaction()
} catch (error) {
  session.abortTransaction()
  throw error
} finally {
  session.endSession()
}
```

## Rules

```text
Transactions can span multiple operations, documents, collections and databases. Keep transactions short and implement retry handling for transient transaction errors in application code.
```

