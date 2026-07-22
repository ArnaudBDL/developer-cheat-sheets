# Power BI : Performance

## Optimization Areas

```text
Source-system queries
Power Query folding
Storage mode
Model cardinality and size
Relationships
DAX measures
Visual count and interactions
Custom visuals
Gateway capacity
Refresh design
```

## Checks

```text
Remove unused rows and columns.
Prefer star-schema models.
Reduce high-cardinality text where possible.
Optimize DAX using variables and focused filters.
Limit visuals per page.
Use Performance Analyzer for report interactions.
Monitor source and gateway latency.
Test with production-like data volume and concurrency.
```

Optimize after measurement. A fast model with incorrect relationships or security is not acceptable. Re-test performance after changing models, storage modes, measures, visuals or refresh behavior.
