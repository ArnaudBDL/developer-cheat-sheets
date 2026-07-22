# MongoDB : Backup

## mongodump

```bash
mongodump --uri="mongodb://USER@HOST:27017/application" \
  --authenticationDatabase=admin \
  --out=/backups/mongodb

mongodump --uri="$MONGODB_URI" --archive=backup.archive --gzip
```

## Single Collection

```bash
mongodump --uri="$MONGODB_URI" \
  --db=application \
  --collection=users \
  --archive=users.archive \
  --gzip
```

## Verify

```bash
find /backups/mongodb -type f -ls
sha256sum backup.archive
```

