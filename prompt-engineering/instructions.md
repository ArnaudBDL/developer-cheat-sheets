# Prompt Engineering : Instructions

## Instruction Structure

```text
Role or operating mode
Primary task
Required procedure
Quality criteria
Prohibited behavior
Fallback behavior
```

## Example

```text
Summarize the supplied incident report for an engineering manager.
Include impact, timeline, root cause and corrective actions.
Use only the supplied report.
If an item is absent, write "Not stated".
Return concise Markdown headings and bullet points.
```

- Put important instructions before the source material.
- Use direct verbs and precise nouns.
- Resolve conflicting requirements before deployment.
- Avoid vague goals such as “make it better”.
- Distinguish mandatory requirements from preferences.
- Do not repeat instructions unless repetition serves a measured purpose.
