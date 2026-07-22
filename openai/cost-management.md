# OpenAI : Cost Management

## Primary Cost Drivers

```text
Selected model
Input tokens
Output tokens
Cached input behavior where supported
Image size and quantity
Audio duration and modality
Tool and retrieval loops
Retry volume
Storage and batch features where applicable
```

## Measurement

```text
Record model and endpoint
Record input and output usage metadata
Attribute usage to product, environment and tenant
Track cost per completed business task
Alert on anomalies and budget thresholds
```

## Optimization

- Choose the smallest model meeting measured quality requirements.
- Remove irrelevant context and duplicate instructions.
- Cap output length.
- Cache stable application results when safe.
- Batch appropriate background work.
- Prevent recursive tool and retry loops.
- Delete unused files and derived assets according to policy.
- Re-evaluate quality, latency and cost together after every model change.
