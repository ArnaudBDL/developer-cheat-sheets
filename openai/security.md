# OpenAI : Security

## Threats

```text
API key exposure
Prompt injection
Sensitive-data disclosure
Unsafe tool execution
Untrusted file processing
Cross-tenant retrieval
Generated misinformation
Dependency compromise
Denial of wallet or unbounded cost
```

## Controls

- Keep API keys server-side and least privileged.
- Separate trusted instructions from untrusted content.
- Authorize every tool call and retrieved object.
- Require approval for consequential actions.
- Validate files, URLs, schemas and model-produced arguments.
- Minimize data sent to the API.
- Apply retention and logging policy deliberately.
- Set token, request, concurrency and spending limits.
- Review model output before high-impact use.
- Maintain incident response for leaked credentials and unsafe actions.
