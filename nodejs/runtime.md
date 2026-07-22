# Node.js : Runtime

## Execution Model

```text
JavaScript execution
Event loop
Asynchronous I/O
Worker pool for selected native operations
Callbacks, promises and async functions
```

## Run Scripts

```bash
node app.js
node --watch app.js
node --env-file=.env app.js
node --enable-source-maps app.js
node --trace-warnings app.js
```

## Event Loop Scheduling

```javascript
process.nextTick(() => console.log('next tick'));
queueMicrotask(() => console.log('microtask'));
setImmediate(() => console.log('immediate'));
setTimeout(() => console.log('timeout'), 0);
```

## Async Function

```javascript
async function loadData() {
  const response = await fetch('https://example.com/data.json');
  if (!response.ok) {
    throw new Error(`HTTP ${response.status}`);
  }

  return response.json();
}
```

## Runtime Information

```javascript
console.log(process.version);
console.log(process.versions);
console.log(process.platform);
console.log(process.arch);
console.log(process.uptime());
```
