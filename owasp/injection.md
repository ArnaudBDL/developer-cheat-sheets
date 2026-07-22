# OWASP : Injection

## Risk Sources

```text
SQL and NoSQL queries
Operating-system commands
LDAP queries
Template expressions
Regular expressions
XML and XPath
Dynamic code evaluation
```

## Controls

- Use parameterized queries and prepared statements.
- Keep commands and data separate.
- Avoid dynamic evaluation and interpreter construction.
- Apply allowlists for expected identifiers, operators and command options.
- Validate type, length, range, format and allowed values.
- Escape output for the exact destination context when required.
- Use least-privileged database and operating-system accounts.
- Return generic client errors while preserving safe diagnostic context internally.

## Safe Query Pattern

```typescript
const result = await database.query(
  'SELECT id, email FROM users WHERE id = $1',
  [userId],
);
```

Do not concatenate untrusted values into query or command strings.
