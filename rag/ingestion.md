# Retrieval-Augmented Generation : Ingestion

## Pipeline

```text
Discover source changes
Fetch authorized objects
Validate file and payload limits
Parse structure and content
Normalize encoding and whitespace
Extract metadata and permissions
Detect language and duplicates
Chunk and embed
Write index atomically
Record status and lineage
```

## Change Handling

```text
Create  Add source and chunks
Update  Replace or version affected chunks
Delete  Remove source, vectors and derived caches
Move    Preserve identity when possible
Revoke  Remove visibility immediately
```

- Make ingestion idempotent.
- Use checksums or source versions to avoid unnecessary reprocessing.
- Quarantine malformed or unsafe content.
- Keep raw source, parsed representation and indexed chunks traceable.
- Retry transient failures with bounded backoff.
- Monitor freshness lag and deletion propagation.
