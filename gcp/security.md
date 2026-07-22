# GCP : Security

## Identity and Policy

```bash
gcloud projects get-iam-policy PROJECT_ID
gcloud org-policies list --project=PROJECT_ID
gcloud iam service-accounts list
gcloud asset search-all-iam-policies --scope=projects/PROJECT_ID
```

## Secrets and Encryption

```bash
gcloud secrets create application-secret --replication-policy=automatic
printf '%s' 'SECRET_VALUE' | gcloud secrets versions add application-secret --data-file=-
gcloud secrets versions access latest --secret=application-secret
gcloud kms keyrings list --location=global
gcloud kms keys list --keyring=KEYRING --location=global
```

## Controls

- Apply least privilege and separate administrative duties.
- Use organization policies and service perimeters where required.
- Prefer short-lived credentials and workload identity.
- Protect secrets and rotate credentials.
- Restrict public network exposure and review firewall rules.
- Enable audit logging, threat detection and vulnerability management.
- Classify data and enforce retention and deletion requirements.
