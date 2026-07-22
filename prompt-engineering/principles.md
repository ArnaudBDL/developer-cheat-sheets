# Prompt Engineering : Principles

## Core Principles

```text
State one clear primary objective.
Provide only relevant context.
Make constraints explicit and testable.
Define the expected output format.
Use examples when they clarify the pattern.
Separate trusted instructions from untrusted content.
Evaluate prompts systematically on representative cases.
```

## Production Mindset

```text
Prompt + model + tools + context + decoding settings = behavior under evaluation
```

- Treat prompts as versioned application assets.
- Optimize for task success, not eloquence alone.
- Prefer deterministic schemas for machine-consumed output.
- Mark missing information instead of encouraging invention.
- Re-evaluate after model, context or tool changes.
- Keep human review for consequential decisions.
