# Prompt Engineering : Output Formats

## Human-Readable Output

```text
Return Markdown with these headings:
## Summary
## Evidence
## Open Questions
```

## Machine-Readable Output

```json
{
  "summary": "string",
  "risk": "low | medium | high",
  "evidence": ["string"],
  "missing_information": ["string"]
}
```

## Rules

- Use Structured Outputs or schema validation when available.
- Define required fields, enums and null behavior.
- Separate result data from explanations.
- Avoid parsing unconstrained prose for automated workflows.
- Handle refusals and incomplete output explicitly.
- Validate business rules after syntactic parsing.
- Keep human-facing formats readable and accessible.
