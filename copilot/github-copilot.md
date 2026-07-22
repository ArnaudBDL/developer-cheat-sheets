# Copilot : GitHub Copilot

## Development Uses

```text
Explain unfamiliar code
Generate focused code changes
Write tests
Review changes
Investigate issues
Refactor implementation
Draft documentation
Operate in agent-assisted workflows
```

## Repository Prompt

```text
Implement the requested change only in the authentication module.
Preserve the public API.
Follow the repository conventions.
Add unit tests for success and failure paths.
Run the relevant tests and report changed files.
Do not modify generated files or dependencies.
```

## Review Checklist

- Inspect every generated diff.
- Run tests, linters and security checks.
- Check authentication, authorization and input boundaries.
- Reject hardcoded secrets and unapproved dependencies.
- Preserve human review before merging agent-generated changes.
- Review agent session logs when available.
