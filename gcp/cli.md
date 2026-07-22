# GCP : CLI

## Initialize and Authenticate

```bash
gcloud version
gcloud init
gcloud auth login
gcloud auth list
gcloud auth application-default login
gcloud auth revoke ACCOUNT
```

## Configuration

```bash
gcloud config list
gcloud config set project PROJECT_ID
gcloud config set compute/region europe-west1
gcloud config set compute/zone europe-west1-b
gcloud config configurations create production
gcloud config configurations activate production
gcloud config configurations list
```

## Discovery and Output

```bash
gcloud help
gcloud compute instances --help
gcloud components list
gcloud info
gcloud projects list --format='table(projectId,name,lifecycleState)'
gcloud compute instances list --filter='status=RUNNING' --format=json
```

Prefer user federation, workload identity or attached service accounts over long-lived service account keys.
