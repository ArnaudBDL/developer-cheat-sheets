# GCP : Troubleshooting

## Identity and Configuration

```bash
gcloud version
gcloud info
gcloud config list
gcloud auth list
gcloud auth application-default print-access-token
gcloud projects describe PROJECT_ID
gcloud services list --enabled --project=PROJECT_ID
```

## Diagnostics

```bash
gcloud COMMAND --verbosity=debug
gcloud logging read 'severity>=ERROR' --limit=50 --freshness=1h
gcloud compute operations list
gcloud run services describe application --region=europe-west1
gcloud functions describe application-handler --gen2 --region=europe-west1
gcloud container operations list --region=europe-west1
```

## Common Problems

```text
PERMISSION_DENIED
  Verify the active identity, IAM role, resource scope and deny policies.

API not enabled
  Confirm the required service API is enabled in the selected project.

Resource not found
  Verify project, region, zone, resource name and active configuration.

Quota exceeded
  Inspect project and regional quotas for the requested service.

Network timeout
  Inspect DNS, routes, firewall policies, private access and service endpoints.

Deployment failure
  Inspect service-specific operation status, revision events and logs.

Application Default Credentials failure
  Verify ADC separately from the active gcloud CLI user session.
```

Capture the exact command, project, region or zone, timestamp, operation identifier and error details before escalation.
