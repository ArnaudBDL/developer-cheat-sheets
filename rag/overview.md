# Retrieval-Augmented Generation : Overview

## Definition

```text
Retrieval-Augmented Generation (RAG) retrieves relevant external content
and supplies it as context to a generative model for grounded responses.
```

## Core Pipeline

```text
User query
-> query processing
-> retrieval
-> reranking
-> context assembly
-> generation
-> citations and response
```

## Use Cases

```text
Enterprise knowledge search
Document question answering
Policy and technical support
Knowledge assistants
Source-grounded summaries
```

- RAG supplies knowledge at runtime rather than changing model weights.
- Retrieval quality and source quality directly constrain the answer.
- A RAG response can still be incorrect or unsupported.
- Preserve source references so users can verify important claims.
- Define an explicit fallback when relevant evidence is absent.
