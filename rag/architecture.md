# Retrieval-Augmented Generation : Architecture

## Offline Indexing

```text
Sources
-> connectors
-> parsing and normalization
-> metadata and permissions
-> chunking
-> embeddings
-> searchable indexes
```

## Online Answering

```text
Query
-> authentication and authorization
-> query transformation
-> candidate retrieval
-> permission filtering
-> reranking
-> context construction
-> model generation
-> validation and citations
```

## Design Rules

- Keep indexing and online retrieval independently observable.
- Preserve stable source and chunk identifiers across the pipeline.
- Version parsers, chunkers, embedding models and indexes.
- Apply access control before context reaches the model.
- Support replay of retrieval and generation inputs for debugging.
- Make each stage replaceable behind a clear interface.
