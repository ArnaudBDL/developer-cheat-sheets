# Prompt Engineering : Constraints

## Constraint Categories

```text
Scope          What the model may use or discuss
Length         Maximum words, sections or records
Format         Markdown, JSON Schema, table or code
Style          Tone, audience and terminology
Evidence       Citation and source requirements
Safety         Forbidden content or actions
Fallback       Behavior when information is missing
```

## Example

```text
Use only the supplied policy.
Return at most five bullet points.
Each bullet must contain one claim and one source reference.
Do not infer dates, owners or requirements.
If the policy is silent, state that explicitly.
```

- Make constraints observable in evaluation.
- Avoid impossible combinations.
- State priorities when constraints can conflict.
- Prefer positive requirements plus explicit exclusions.
- Validate constraints outside the model when correctness matters.
