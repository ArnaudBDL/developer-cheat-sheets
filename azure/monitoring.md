# Azure : Monitoring

```bash
az monitor metrics list-definitions --resource RESOURCE_ID --output table
az monitor metrics list --resource RESOURCE_ID --metric METRIC_NAME
az monitor activity-log list --resource-group application-rg --max-events 20 --output table
```

```bash
az monitor log-analytics workspace create   --resource-group application-rg   --workspace-name application-logs
az monitor log-analytics workspace show   --resource-group application-rg   --workspace-name application-logs
```

Use Azure Monitor metrics, logs, activity logs, alerts and diagnostic settings. Route the required resource logs to an approved destination.
