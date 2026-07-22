# GCP : Cost Management

## Billing

```bash
gcloud billing accounts list
gcloud billing projects list --billing-account=BILLING_ACCOUNT_ID
gcloud billing projects describe PROJECT_ID
gcloud billing budgets list --billing-account=BILLING_ACCOUNT_ID
```

## Labels and Inventory

```bash
gcloud projects update PROJECT_ID --update-labels=environment=production,owner=platform
gcloud asset search-all-resources --scope=projects/PROJECT_ID   --format='table(assetType,displayName,location)'
gcloud compute instances list --format='table(name,status,machineType.basename(),zone.basename())'
gcloud compute disks list --filter='-users:*' --format=table
```

## Cost Controls

- Create budgets and notification thresholds.
- Export billing data for detailed analysis.
- Apply consistent labels for application, owner, environment and cost center.
- Review idle compute, unattached disks, stale snapshots and storage lifecycle.
- Right-size services from measured utilization.
- Review committed use discounts only against stable demand.
- Monitor network egress and cross-region data transfer.
