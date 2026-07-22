# OpenAI : Errors

## Common Categories

```text
400  Malformed or unsupported request
401  Missing or invalid authentication
403  Permission, region or IP policy issue
404  Requested object or route not found
429  Rate limit or quota condition
500  Server processing error
503  Temporary overload or slowdown condition
```

## Handling

```text
Validate status and structured error body
Record the request identifier
Correct non-retryable client errors
Retry transient failures with bounded backoff and jitter
Preserve idempotency for side-effecting operations
Escalate persistent failures with sanitized evidence
```

- Distinguish rate limiting from exhausted billing quota.
- Do not retry invalid authentication or malformed requests unchanged.
- Set connection and application timeouts.
- Avoid logging prompts, tokens or files unless policy permits it.
- Preserve error code, model, endpoint, timestamp and request identifier.
