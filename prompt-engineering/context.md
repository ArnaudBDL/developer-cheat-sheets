# Prompt Engineering : Context

## Context Types

```text
Task background
Audience
Source documents
Conversation history
Domain terminology
Current application state
Tool results
Examples
```

## Delimited Context

```text
Answer using only the source below.

<source>
{{SOURCE_CONTENT}}
</source>

Question: {{QUESTION}}
```

## Context Hygiene

- Include the minimum sufficient context.
- Preserve source identity, date and authority where relevant.
- Remove duplicate, obsolete and contradictory material.
- Define precedence when several sources disagree.
- Keep secrets and unnecessary personal data out of prompts.
- Treat retrieved or user-provided content as untrusted data, not instructions.
