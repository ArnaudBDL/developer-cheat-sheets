# GCP : Cloud Functions

## Deploy an HTTP Function

```bash
gcloud functions deploy application-handler   --gen2   --runtime=nodejs22   --region=europe-west1   --source=.   --entry-point=applicationHandler   --trigger-http   --no-allow-unauthenticated   --service-account=application-runtime@PROJECT_ID.iam.gserviceaccount.com
```

## Inspect and Operate

```bash
gcloud functions list --gen2 --region=europe-west1
gcloud functions describe application-handler --gen2 --region=europe-west1
gcloud functions logs read application-handler --gen2 --region=europe-west1 --limit=100
gcloud functions delete application-handler --gen2 --region=europe-west1
```

## Event Trigger

```bash
gcloud functions deploy storage-handler   --gen2   --runtime=nodejs22   --region=europe-west1   --source=.   --entry-point=storageHandler   --trigger-bucket=UNIQUE_BUCKET_NAME
```

Apply least privilege to the runtime identity and define retry and idempotency behavior for event-triggered functions.
