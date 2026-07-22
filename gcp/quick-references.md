# GCP : Quick References

## Session

```bash
gcloud auth login
gcloud auth list
gcloud projects list
gcloud config set project PROJECT_ID
gcloud config list
```

## Compute

```bash
gcloud compute instances list
gcloud compute instances start INSTANCE --zone ZONE
gcloud compute instances stop INSTANCE --zone ZONE
gcloud compute ssh INSTANCE --zone ZONE
```

## Cloud Run

```bash
gcloud run services list
gcloud run deploy SERVICE --source . --region REGION
gcloud run services logs read SERVICE --region REGION
```
