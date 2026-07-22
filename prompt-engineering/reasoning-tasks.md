# Prompt Engineering : Reasoning Tasks

## Task Decomposition

```text
Identify the decision.
Extract relevant facts.
Apply the stated criteria.
Check contradictions and missing data.
Return the conclusion with concise evidence.
```

## Verification Pattern

```text
Solve the task.
Check the result against every constraint.
List any unresolved uncertainty.
Return only the requested answer and concise justification.
```

- Give high-level goals to reasoning-capable models when appropriate.
- Split complex workflows into independently verifiable stages.
- Ask for evidence and checks rather than hidden internal reasoning.
- Use calculators, code or retrieval tools for externally verifiable steps.
- Do not rely on generated reasoning as proof of correctness.
- Evaluate final-answer accuracy and constraint compliance.
