# OpenAI : Authentication

## Environment

```bash
export OPENAI_API_KEY="YOUR_API_KEY"
```

## Bearer Authentication

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

## Python Client

```python
from openai import OpenAI

client = OpenAI()
```

## Rules

- Keep API keys on trusted server-side infrastructure.
- Load credentials from an approved secret store or environment injection.
- Never embed keys in browser, mobile or distributed desktop code.
- Separate projects and credentials by environment.
- Rotate exposed keys immediately.
- Do not include keys in source control, logs, URLs or error reports.
