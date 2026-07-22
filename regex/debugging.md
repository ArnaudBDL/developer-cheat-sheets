# Regular Expressions : Debugging

## Workflow

Identify the exact regex engine and version. Reduce the failing case. Add one construct at a time. Inspect captures. Test positive, negative, empty, long, multiline and Unicode inputs. Benchmark adversarial input.

## JavaScript inspection

```javascript
const regex = /(?<key>[A-Za-z_][A-Za-z0-9_]*)=(?<value>.*)/d;
const match = regex.exec("PORT=8080");
console.dir(match, { depth: null });
```

## Common failures

```text
Double escaping in string literals
Wrong alternation scope
Greedy overmatching
Unsupported lookbehind or backreference
ASCII-only classes on Unicode text
Stateful global or sticky regex reuse
Catastrophic backtracking
```
Automated tests using the production engine are the source of truth.

