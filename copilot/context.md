# Copilot : Context

## Context Sources

```text
Current conversation
Current document, presentation or workbook
Explicitly attached files
Microsoft 365 work data available to the user
Connected external systems
Agent instructions, knowledge and tools
Repository files and development environment
```

## Grounding Prompt

```text
Using only the attached architecture document, summarize the approved decisions.
Cite each source section.
Separate unresolved questions from confirmed decisions.
Do not add recommendations.
```

## Context Hygiene

- Provide only relevant material.
- State authoritative sources and precedence.
- Include exact dates when the period matters.
- Remove obsolete drafts and duplicated sources.
- Avoid placing secrets or unnecessary personal data in prompts.
- Ask for citations when verification matters.
