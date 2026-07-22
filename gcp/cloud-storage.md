# GCP : Cloud Storage

## Buckets

```bash
gcloud storage buckets create gs://UNIQUE_BUCKET_NAME   --location=europe-west1   --uniform-bucket-level-access

gcloud storage buckets list
gcloud storage buckets describe gs://UNIQUE_BUCKET_NAME
gcloud storage buckets update gs://UNIQUE_BUCKET_NAME --public-access-prevention=enforced
```

## Objects

```bash
gcloud storage cp document.txt gs://UNIQUE_BUCKET_NAME/documents/document.txt
gcloud storage cp gs://UNIQUE_BUCKET_NAME/documents/document.txt .
gcloud storage rsync --recursive --delete-unmatched-destination-objects   ./dist gs://UNIQUE_BUCKET_NAME/site
gcloud storage ls --recursive gs://UNIQUE_BUCKET_NAME
gcloud storage rm gs://UNIQUE_BUCKET_NAME/documents/document.txt
```

## Lifecycle

```bash
gcloud storage buckets update gs://UNIQUE_BUCKET_NAME   --lifecycle-file=lifecycle.json
```

Use uniform bucket-level access, public access prevention, retention and lifecycle rules according to the data classification.
