# Regular Expressions : Quick References

## Core syntax

```text
.        Any character
^ $      Start and end
* + ?    Quantifiers
{m,n}    Range quantifier
[...]    Character class
(...)    Capturing group
(?:...)  Non-capturing group
|        Alternation
```

## Common patterns

```regex
Email-like:       ^[^@\s]+@[^@\s]+\.[^@\s]+$
Integer:          ^-?\d+$
ISO date:         ^\d{4}-\d{2}-\d{2}$
Hex color:        ^#(?:[0-9a-fA-F]{3}){1,2}$
Slug:             ^[a-z0-9]+(?:-[a-z0-9]+)*$
```

## Lookarounds

```regex
Positive lookahead:  X(?=Y)
Negative lookahead:  X(?!Y)
Positive lookbehind: (?<=Y)X
Negative lookbehind: (?<!Y)X
```
