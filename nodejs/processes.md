# Node.js : Processes

## Process Information

```javascript
console.log(process.pid);
console.log(process.ppid);
console.log(process.cwd());
console.log(process.argv);
console.log(process.memoryUsage());
```

## Exit Codes

```javascript
process.exitCode = 1;
```

Prefer setting `process.exitCode` so pending asynchronous cleanup can complete.

## Signals

```javascript
process.on('SIGTERM', async () => {
  await server.close();
  process.exitCode = 0;
});

process.on('SIGINT', async () => {
  await server.close();
  process.exitCode = 130;
});
```

## Child Processes

```javascript
import { spawn } from 'node:child_process';

const child = spawn('node', ['worker.js'], {
  stdio: 'inherit',
  env: { ...process.env, WORKER_MODE: 'true' },
});

child.on('exit', code => console.log(`Exit: ${code}`));
```

## Promisified Execution

```javascript
import { execFile } from 'node:child_process';
import { promisify } from 'node:util';

const executeFile = promisify(execFile);
const { stdout } = await executeFile('node', ['--version']);
```
