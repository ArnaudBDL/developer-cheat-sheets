# OpenAI : Rate Limits

## Limit Dimensions

```text
RPM  Requests per minute
RPD  Requests per day
TPM  Tokens per minute
TPD  Tokens per day
IPM  Images per minute
Additional modality-specific limits may apply
```

## Controls

```text
Client-side concurrency limit
Queue and backpressure
Exponential backoff with jitter
Input and output token budgets
Batching where supported
Usage and saturation monitoring
```

- Limits can vary by model, project and organization.
- Observe current limits in the developer console and response metadata.
- Smooth bursts rather than immediately retrying every rejected request.
- Count failed attempts against throughput planning.
- Do not use unbounded retries.
- Separate user-facing latency objectives from background throughput workloads.
- Request higher limits only after measuring sustained demand.
