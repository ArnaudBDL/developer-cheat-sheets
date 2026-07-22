# Python : Security

## Core Controls

```text
Validate untrusted input
Use parameterized database queries
Avoid eval and exec on untrusted content
Avoid untrusted pickle and unsafe deserialization
Use secrets instead of random for security tokens
Keep credentials outside source code
Pin and scan dependencies
Restrict subprocess commands and file paths
Apply time, memory and payload limits
```

## Token

```python
import secrets

token = secrets.token_urlsafe(32)
```

Security controls must be enforced by the application and operating environment, not by comments, prompts or type hints.
