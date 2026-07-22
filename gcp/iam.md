# GCP : IAM

## Inspect Policies

```bash
gcloud projects get-iam-policy PROJECT_ID
gcloud projects get-iam-policy PROJECT_ID   --flatten='bindings[].members'   --format='table(bindings.role,bindings.members)'
gcloud iam roles list --project=PROJECT_ID
gcloud iam service-accounts list --project=PROJECT_ID
```

## Service Accounts

```bash
gcloud iam service-accounts create application-runtime   --display-name='Application runtime'

gcloud projects add-iam-policy-binding PROJECT_ID   --member='serviceAccount:application-runtime@PROJECT_ID.iam.gserviceaccount.com'   --role='roles/storage.objectViewer'

gcloud iam service-accounts get-iam-policy   application-runtime@PROJECT_ID.iam.gserviceaccount.com
```

## Rules

- Grant the narrowest predefined or custom role at the smallest practical scope.
- Separate human administration from workload identities.
- Avoid basic Owner, Editor and Viewer roles for routine workload access.
- Review service account impersonation and key creation rights.
- Enable and review IAM audit logs where required.
