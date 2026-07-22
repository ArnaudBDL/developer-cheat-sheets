# OpenAI : Embeddings

## Create an Embedding

```python
response = client.embeddings.create(
    model="text-embedding-3-small",
    input="A concise description of the document.",
    encoding_format="float",
)

vector = response.data[0].embedding
```

## Use Cases

```text
Semantic search
Clustering
Recommendations
Anomaly detection
Classification
```

## Pipeline

```text
Normalize source content
Split into meaningful chunks
Create embeddings
Store vector plus source metadata
Embed the query
Rank by vector similarity
Apply authorization filters
Return source-grounded results
```

- Use the same embedding model and dimensionality for indexed items and queries.
- Preserve document identity, version and permissions with each vector.
- Re-index content when chunking or embedding strategy changes.
- Evaluate retrieval quality with representative queries.
- Apply access control before returning retrieved content.
