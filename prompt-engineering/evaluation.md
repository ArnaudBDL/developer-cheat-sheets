# Prompt Engineering : Evaluation

## Evaluation Set

```text
Typical cases
Boundary cases
Ambiguous inputs
Missing-context cases
Adversarial instructions
Safety-sensitive cases
Previously observed failures
```

## Metrics

```text
Task accuracy
Schema validity
Constraint compliance
Groundedness
Citation correctness
Tool-selection accuracy
Safety behavior
Latency
Token usage and cost
```

## Process

```text
Define acceptance criteria
Build a versioned test set
Record a baseline
Change one variable
Run repeatable evaluations
Inspect regressions
Promote or reject the change
Monitor production failures
```

Use human review for subjective quality and automated checks for exact properties. Keep test data representative and separate from prompt examples.
