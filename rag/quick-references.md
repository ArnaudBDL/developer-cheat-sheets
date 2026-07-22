# Retrieval-Augmented Generation : Quick References

## Pipeline

```text
Ingest documents
Normalize content
Split into chunks
Create embeddings
Store vectors and metadata
Retrieve candidates
Rerank results
Construct grounded prompt
Generate answer with citations
```

## Chunk metadata

```json
{
  "source": "document-id",
  "title": "Document title",
  "section": "Section name",
  "updatedAt": "2026-01-01T00:00:00Z",
  "permissions": []
}
```

## Evaluation

```text
Retrieval precision
Retrieval recall
Answer faithfulness
Citation correctness
Latency
Cost
Permission filtering
```
