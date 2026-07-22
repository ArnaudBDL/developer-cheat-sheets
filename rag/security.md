# Retrieval-Augmented Generation : Security

## Threats

```text
Prompt injection inside retrieved documents
Cross-tenant data leakage
Stale or revoked permissions
Malicious files and parsers
Source poisoning
Sensitive data exposure in logs or embeddings
Unauthorized vector-store queries
Citation spoofing
Excessive query or generation cost
```

## Controls

- Authenticate users and enforce authorization before retrieval.
- Carry source permissions through ingestion and indexing.
- Treat retrieved content as untrusted data.
- Validate files, URLs, parsers and metadata.
- Isolate tenants and test filter bypass attempts.
- Propagate deletions and permission revocations promptly.
- Minimize sensitive data in prompts, vectors and logs.
- Validate citations against selected source chunks.
- Bound query expansion, candidate counts, tools, tokens and cost.
- Require human review for consequential answers.

RAG improves grounding but does not create a security boundary or guarantee correctness.
