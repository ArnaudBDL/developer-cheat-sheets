# Retrieval-Augmented Generation : Embeddings

## Purpose

```text
An embedding maps content into a numeric vector.
Vector distance or similarity is used to retrieve semantically related chunks.
```

## Index Record

```json
{
  "chunk_id": "chunk_42",
  "source_id": "doc_7",
  "text": "Normalized chunk text",
  "embedding_model": "MODEL_VERSION",
  "permissions": ["group:engineering"]
}
```

- Use compatible models and dimensions for indexed chunks and queries.
- Normalize content consistently before embedding.
- Track embedding model and index version.
- Re-index when the model or preprocessing contract changes.
- Evaluate multilingual and domain-specific retrieval explicitly.
- Never rely on vector similarity as authorization.
