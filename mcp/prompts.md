# Model Context Protocol : Prompts

## Prompt Definition

```json
{
  "name": "review_architecture",
  "description": "Review an architecture decision record",
  "arguments": [
    {
      "name": "documentUri",
      "description": "URI of the architecture record",
      "required": true
    }
  ]
}
```

## Purpose

```text
Prompts expose reusable, server-provided interaction templates.
They can standardize common workflows while remaining visible to the client and user.
```

## Rules

- Name prompts by user intent.
- Keep arguments explicit and validated.
- Preserve the distinction between server-provided template content and user instructions.
- Do not hide consequential actions inside a prompt template.
- Treat external content inserted into prompts as untrusted data.
- Review prompt changes as contract changes.
