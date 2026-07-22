# Retrieval-Augmented Generation : Retrieval

## Approaches

```text
Lexical search   Exact terms, identifiers and rare keywords
Dense retrieval Semantic similarity through embeddings
Hybrid search    Combines lexical and dense candidate sets
Filtered search  Restricts by tenant, source, type, date or permission
```

## Runtime Steps

```text
Normalize query
Apply authorization filters
Optionally rewrite or expand query
Retrieve a broad candidate set
Merge candidate lists
Deduplicate
Return scores and provenance
```

- Measure recall before optimizing generation.
- Preserve exact identifiers and quoted terms.
- Avoid query rewriting that changes user intent.
- Tune candidate count using evaluation data.
- Return no-answer evidence when retrieval confidence is insufficient.
- Keep raw retrieval results for diagnostics.
