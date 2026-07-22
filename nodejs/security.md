# Node.js : Security

## Dependency Controls

```bash
npm audit
npm outdated
npm ci
npm explain PACKAGE
```

- Commit and review the lock file.
- Review install scripts and new transitive dependencies.
- Remove unused packages.
- Update Node.js and dependencies regularly.

## Input and Output

```javascript
const id = Number.parseInt(request.params.id, 10);
if (!Number.isSafeInteger(id) || id <= 0) {
  throw new Error('Invalid identifier');
}
```

Validate input at trust boundaries and encode output for its destination context.

## Child Processes

```javascript
import { execFile } from 'node:child_process';

execFile('tool', ['--input', validatedValue], callback);
```

Prefer argument arrays with `execFile()` or `spawn()` over constructing shell command strings from input.

## Secrets

- Keep credentials outside source control.
- Avoid printing tokens or complete environment contexts.
- Prefer short-lived credentials and dedicated secret stores.
- Rotate exposed credentials immediately.

## Operational Controls

- Run with the minimum required operating-system permissions.
- Set request, connection and operation timeouts.
- Limit request and payload sizes.
- Use supported TLS configurations.
- Handle errors without exposing internal details.
- Monitor crashes, rejected promises and resource usage.
