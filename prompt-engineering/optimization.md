# Prompt Engineering : Optimization

## Optimization Order

```text
Clarify the objective
Improve source context
Tighten output schema
Remove contradictions
Add targeted examples
Select the appropriate model
Reduce unnecessary tokens
Tune tool descriptions
Measure again
```

## Cost and Latency

- Remove repeated boilerplate and irrelevant context.
- Keep reusable static instructions stable where caching is supported.
- Cap output length.
- Use the smallest model meeting measured quality requirements.
- Avoid unnecessary multi-turn and tool loops.
- Batch eligible offline work.
- Track cost per successful business task, not only per request.

Optimize one variable at a time. Never declare an improvement without comparing evaluation results against the baseline.
