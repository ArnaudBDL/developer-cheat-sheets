# Retrieval-Augmented Generation : Vector Stores

## Capabilities

```text
Vector insertion and update
Approximate or exact nearest-neighbor search
Metadata filtering
Namespace or tenant isolation
Deletion
Backup and recovery
Index statistics
```

## Selection Criteria

```text
Corpus size and growth
Query latency and throughput
Filtering requirements
Consistency and freshness
Operational ownership
Regional placement
Backup and deletion guarantees
Cost
```

- Store stable IDs and sufficient metadata beside vectors.
- Enforce tenant and permission filters at query time.
- Verify that deletes remove vectors and dependent caches.
- Tune index parameters with recall and latency evaluations.
- Monitor index growth, write lag and failed updates.
- Keep a reproducible path to rebuild the index.
