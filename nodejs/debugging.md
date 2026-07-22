# Node.js : Debugging

## Inspector

```bash
node --inspect app.js
node --inspect-brk app.js
node --inspect=127.0.0.1:9229 app.js
```

## Built-In Debugger

```bash
node inspect app.js
```

```text
cont       Continue execution
next       Step over
step       Step into
out        Step out
repl       Open evaluation prompt
watch()    Watch an expression
```

## Warnings and Traces

```bash
node --trace-warnings app.js
node --trace-uncaught app.js
node --enable-source-maps app.js
NODE_DEBUG=http,net node app.js
```

## Diagnostic Report

```bash
node --report-on-fatalerror app.js
node --report-on-signal app.js
```

## Debug Output

```javascript
console.log(value);
console.error(error);
console.trace('Trace point');
console.time('operation');
console.timeEnd('operation');
```
