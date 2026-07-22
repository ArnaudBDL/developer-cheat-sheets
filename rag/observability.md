# Retrieval-Augmented Generation : Observability

## Trace Fields

```text
request_id
user and tenant identifiers in approved form
query hash or redacted query
retriever and index version
candidate IDs and scores
reranker version and scores
selected chunk IDs
model and prompt version
latency by stage
usage and cost
response status
```

## Operational Metrics

```text
Ingestion freshness and failure rate
Index write lag
Retrieval latency and empty-result rate
Reranker latency
Generation latency and errors
Citation failure rate
No-answer rate
User feedback and escalation rate
```

- Redact sensitive content from logs.
- Trace each answer back to source versions.
- Alert on freshness, authorization and deletion failures.
- Keep enough evidence to replay failures safely.
- Segment metrics by pipeline version to detect regressions.
