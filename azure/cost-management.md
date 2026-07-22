# Azure : Cost Management

```bash
az consumption budget list --output table
az consumption usage list --start-date YYYY-MM-DD --end-date YYYY-MM-DD --output table
az advisor recommendation list --category Cost --output table
az resource list --tag environment=development --output table
```

Use consistent tags for owner, environment, application and cost center. Review idle resources, VM sizing, storage redundancy and retention, database tiers, outbound transfer and reservations against measured usage.
