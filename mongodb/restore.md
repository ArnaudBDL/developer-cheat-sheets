# MongoDB : Restore

## Restore Directory

```bash
mongorestore --uri="$MONGODB_URI" \
  --drop \
  /backups/mongodb/application
```

## Restore Archive

```bash
mongorestore --uri="$MONGODB_URI" \
  --archive=backup.archive \
  --gzip \
  --drop
```

## Namespace Mapping

```bash
mongorestore --uri="$MONGODB_URI" \
  --archive=backup.archive \
  --gzip \
  --nsFrom='application.*' \
  --nsTo='restored_application.*' \
  --dryRun
```

## Validate

```bash
mongosh "$MONGODB_URI" --eval 'db.runCommand({ validate: "users", full: true })' 
```

