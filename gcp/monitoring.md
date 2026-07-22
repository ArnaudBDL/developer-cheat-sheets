# GCP : Monitoring

## Logs

```bash
gcloud logging read   'resource.type="cloud_run_revision" AND resource.labels.service_name="application"'   --limit=50   --format=json

gcloud logging logs list
gcloud logging sinks list
gcloud logging metrics list
```

## Metrics and Policies

```bash
gcloud monitoring metrics-scopes list --project=PROJECT_ID
gcloud monitoring policies list
gcloud monitoring channels list
gcloud monitoring dashboards list
```

## Operational Signals

```text
Availability and request latency
Error rate
Resource saturation
Queue depth and backlog age
Deployment and revision health
Database connections and storage
Security and audit events
Cost and quota usage
```

Use structured logs, trace or correlation identifiers, service-level objectives and alerts tied to user or business impact.
