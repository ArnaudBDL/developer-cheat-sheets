# Regular Expressions : Replacement

## JavaScript

```javascript
const result = "BODEL, Arnaud".replace(
  /(?<last>[A-Za-z]+),\s*(?<first>[A-Za-z]+)/,
  "$<first> $<last>",
);
```

## Python

```python
result = re.sub(
    r"(?P<last>[A-Za-z]+),\s*(?P<first>[A-Za-z]+)",
    r"\g<first> \g<last>",
    value,
)
```

## Rules

Replacement token syntax differs between languages. Prefer callbacks for computed replacements. Test unmatched optional groups and keep untrusted replacement data away from executable contexts.

