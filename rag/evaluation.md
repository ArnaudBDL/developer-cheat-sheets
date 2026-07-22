# Retrieval-Augmented Generation : Evaluation

## Retrieval Metrics

```text
Recall at k
Precision at k
Mean reciprocal rank
Normalized discounted cumulative gain
Permission-filter correctness
```

## Generation Metrics

```text
Answer correctness
Faithfulness to retrieved context
Citation correctness and completeness
Relevance
No-answer accuracy
Format compliance
```

## Process

```text
Create versioned questions and expected evidence
Evaluate retrieval separately from generation
Include missing-answer and adversarial cases
Review failures by pipeline stage
Compare against a fixed baseline
Block promotion on critical regressions
```

Use human review for subjective or high-impact outputs and automated checks for reproducible properties.
