# Retrieval-Augmented Generation : Reranking

## Purpose

```text
First-stage retrieval maximizes candidate recall.
Reranking applies a stronger relevance function to improve final precision.
```

## Pipeline

```text
Query
-> broad candidate retrieval
-> deduplication
-> permission check
-> reranker scoring
-> diversity and source rules
-> final context selection
```

## Checks

- Rerank only candidates the user is authorized to access.
- Preserve source and original retrieval scores for analysis.
- Control candidate count to bound latency and cost.
- Avoid selecting many near-duplicate chunks.
- Evaluate whether the answer-bearing chunk moves into the final context.
- Keep a fallback path if the reranker is unavailable.
