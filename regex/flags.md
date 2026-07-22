# Regular Expressions : Flags

## Common flags

```text
i case-insensitive
g global iteration in JavaScript
m multiline anchors
s dot-all
u Unicode-aware JavaScript mode
v Unicode sets in supporting JavaScript runtimes
y sticky JavaScript search
d JavaScript match indices
x verbose mode in supporting engines
```

## Usage

```javascript
const pattern = /example/gim;
```
```python
pattern = re.compile(r"^example$", re.IGNORECASE | re.MULTILINE)
```

## Rules

Flag availability varies. JavaScript global and sticky patterns can mutate `lastIndex`. Multiline and dot-all are independent.

