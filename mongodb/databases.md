# MongoDB : Databases

## Navigate

```javascript
show dbs
use application
db
db.stats()
db.getName()
```

## Create and Drop

```javascript
use application
db.settings.insertOne({ name: "initialized", value: true })
db.dropDatabase()
```

## Inspect

```javascript
db.adminCommand({ listDatabases: 1 })
db.getSiblingDB("admin").serverStatus()
```

