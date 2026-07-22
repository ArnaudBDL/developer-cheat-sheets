# Power BI : Refresh

## Storage Modes

```text
Import models load source data and require source-data refresh.
DirectQuery models query the source during report interaction.
Direct Lake and live connections have different freshness behavior.
```

## Refresh Checklist

```text
Data-source credentials
Gateway mapping and availability
Source reachability
Privacy levels
Parameters
Scheduled refresh settings
Timeout and resource limits
Schema compatibility
Refresh history
```

## Troubleshooting

- Reproduce the query in Desktop where possible.
- Verify that the service uses the intended credentials.
- Confirm the correct gateway cluster and data-source mapping.
- Inspect refresh history and gateway logs.
- Test incremental-refresh partitions and date parameters.
- Avoid assuming a report display refresh performs a source-data refresh.
