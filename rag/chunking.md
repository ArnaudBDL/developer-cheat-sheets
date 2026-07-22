# Retrieval-Augmented Generation : Chunking

## Strategies

```text
Fixed-size            Simple token or character windows
Recursive             Splits using ordered separators
Structure-aware       Respects headings, paragraphs, lists and tables
Semantic              Splits near topic boundaries
Parent-child          Retrieves small chunks and supplies broader parents
```

## Chunk Metadata

```text
chunk_id
source_id
parent_id
section_path
position
page or line range
version
permissions
```

## Rules

- Keep each chunk meaningful without excessive surrounding noise.
- Preserve headings with the content they qualify.
- Avoid splitting tables, code blocks and ordered procedures blindly.
- Use overlap only when it improves measured retrieval.
- Include source position for citations.
- Evaluate chunking against real questions, not only average chunk size.
