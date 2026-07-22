# Regular Expressions : Groups

## Groups

```regex
(abc)             capturing
(?:abc)           non-capturing
(?<name>abc)      named capture in JavaScript and several engines
```

## Backreferences

```regex
\b([A-Za-z]+)\s+\1\b
```
Matches an immediately repeated ASCII word in supporting engines.

## Rules

Prefer non-capturing groups when capture data is unnecessary. Named-group syntax differs by engine. Renumbering groups can break replacements. Go RE2 intentionally excludes backreferences and lookarounds.

