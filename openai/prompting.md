# OpenAI : Prompting

## Prompt Structure

```text
Goal        Exact task to perform
Context     Relevant background and source material
Constraints Required and forbidden behavior
Output      Format, fields, tone and length
Quality     Checks the response must satisfy
```

## Template

```text
Create [deliverable] for [audience].
Use only [sources].
Include [requirements].
Exclude [constraints].
Return [format].
Mark missing information instead of inventing it.
```

- Put stable application instructions in the appropriate instruction layer.
- Delimit untrusted source content clearly.
- Provide examples only when they clarify the desired pattern.
- Ask for citations when grounding matters.
- Prefer structured outputs over prose parsing for machine consumers.
- Evaluate prompts against normal, ambiguous and adversarial inputs.
- Version prompts used in production.
