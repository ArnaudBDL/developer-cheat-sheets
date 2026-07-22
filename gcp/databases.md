# GCP : Databases

## Cloud SQL

```bash
gcloud sql instances create application-db   --database-version=POSTGRES_17   --tier=db-custom-2-7680   --region=europe-west1   --no-assign-ip

gcloud sql databases create application --instance=application-db
gcloud sql instances describe application-db
gcloud sql backups list --instance=application-db
gcloud sql connect application-db --user=postgres
```

## Firestore

```bash
gcloud firestore databases list
gcloud firestore databases describe --database='(default)'
```

## Database Selection

```text
Cloud SQL     Managed relational MySQL, PostgreSQL and SQL Server workloads
AlloyDB       PostgreSQL-compatible managed database for demanding workloads
Firestore     Document database for application data
Spanner       Horizontally scalable relational database
Bigtable      Wide-column database for high-throughput workloads
```

Use private connectivity, backups, point-in-time recovery, encryption and database-specific monitoring appropriate to the service.
