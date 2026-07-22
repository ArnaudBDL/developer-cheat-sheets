# GCP : Projects

## Manage Projects

```bash
gcloud projects list
gcloud projects create PROJECT_ID --name='Application Production'
gcloud projects describe PROJECT_ID
gcloud config set project PROJECT_ID
gcloud projects delete PROJECT_ID
```

## APIs and Billing

```bash
gcloud services list --available
gcloud services enable compute.googleapis.com run.googleapis.com   cloudfunctions.googleapis.com storage.googleapis.com
gcloud services list --enabled
gcloud billing projects describe PROJECT_ID
gcloud billing projects link PROJECT_ID --billing-account=BILLING_ACCOUNT_ID
```

## Organization Context

```bash
gcloud organizations list
gcloud resource-manager folders list --organization=ORGANIZATION_ID
gcloud resource-manager tags bindings list --parent=PROJECT_RESOURCE_NAME
```

Use projects as clear lifecycle, billing, quota and policy boundaries. Apply consistent labels and ownership metadata.
