# AWS : RDS

## Database Instances

```bash
aws rds describe-db-engine-versions --engine postgres --output table

aws rds create-db-instance   --db-instance-identifier application-db   --engine postgres   --db-instance-class db.t4g.micro   --allocated-storage 20   --master-username dbadmin   --manage-master-user-password   --no-publicly-accessible

aws rds describe-db-instances --db-instance-identifier application-db
aws rds stop-db-instance --db-instance-identifier application-db
aws rds start-db-instance --db-instance-identifier application-db
```

## Snapshots

```bash
aws rds create-db-snapshot   --db-instance-identifier application-db   --db-snapshot-identifier application-db-manual

aws rds describe-db-snapshots --db-instance-identifier application-db
aws rds restore-db-instance-from-db-snapshot   --db-instance-identifier restored-db   --db-snapshot-identifier application-db-manual
```
