# Prompt Engineering : Prompt Templates

## General Template

```text
# Goal
{{GOAL}}

# Context
{{CONTEXT}}

# Requirements
{{REQUIREMENTS}}

# Constraints
{{CONSTRAINTS}}

# Output
{{OUTPUT_FORMAT}}

# Source
<SOURCE>
{{SOURCE_CONTENT}}
</SOURCE>
```

## Extraction Template

```text
Extract {{FIELDS}} from the source.
Use only explicit information.
Return {{SCHEMA}}.
Use null for an absent optional value.
Do not infer missing values.
```

- Name every placeholder clearly.
- Validate template variables before rendering.
- Delimit inserted content.
- Escape or isolate untrusted variables.
- Version templates and record model compatibility.
- Keep one template focused on one stable task.
- Store evaluation cases with the template.
