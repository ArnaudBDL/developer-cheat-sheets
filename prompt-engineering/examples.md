# Prompt Engineering : Examples

## Few-Shot Pattern

```text
Input: Payment failed after three retries.
Output: {"category":"payment","severity":"high"}

Input: User requested a password reset.
Output: {"category":"account","severity":"medium"}

Input: {{NEW_INPUT}}
Output:
```

## Example Selection

```text
Representative normal case
Boundary case
Ambiguous case
Correct refusal or missing-data case
Expected formatting edge case
```

- Keep examples consistent with instructions and schemas.
- Prefer a small diverse set over many repetitive examples.
- Avoid examples containing accidental confidential data.
- Include correct outputs only unless errors are clearly labelled.
- Re-test whether examples still improve results after model changes.
- Do not let examples silently redefine the requested task.
