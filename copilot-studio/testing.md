# Copilot Studio : Testing and Evaluation

## Test Layers

```text
Instructions
Topic routing
Knowledge retrieval
Grounded answers
Entities and variables
Tool selection and arguments
Authentication and authorization
Channel behavior
Safety and refusal
Load and reliability
```

## Evaluation Set

```text
Normal requests
Ambiguous requests
Missing evidence
Out-of-scope requests
Adversarial instructions
Unauthorized requests
Tool failures
Multilingual cases
Previously observed regressions
```

Use repeatable test sets and explicit pass criteria. Separate retrieval, orchestration, tool and final-answer failures. Test with realistic identities and production-like configuration before release.
