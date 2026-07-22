# GCP : Cloud Run

## Deploy a Service

```bash
gcloud run deploy application   --source=.   --region=europe-west1   --service-account=application-runtime@PROJECT_ID.iam.gserviceaccount.com   --no-allow-unauthenticated

gcloud run services list --region=europe-west1
gcloud run services describe application --region=europe-west1
gcloud run services update application   --region=europe-west1   --set-env-vars=APPLICATION_ENV=production
```

## Revisions and Traffic

```bash
gcloud run revisions list --service=application --region=europe-west1
gcloud run services update-traffic application   --region=europe-west1   --to-latest
gcloud run services logs read application --region=europe-west1 --limit=100
```

Keep services authenticated unless public access is explicitly required. Use Secret Manager references rather than embedding secrets in images or environment files.
