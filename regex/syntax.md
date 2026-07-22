# Regular Expressions : Syntax

## Pattern anatomy

```regex
^user-[0-9]+$
```
A pattern combines literals, metacharacters, groups, classes, quantifiers and assertions.

## Construction

```javascript
const literal = /^user-[0-9]+$/;
const dynamic = new RegExp(`^${prefix}-[0-9]+$`);
```
```python
import re
pattern = re.compile(r"^user-[0-9]+$")
```

## Rules

Escape metacharacters when matching them literally. Prefer raw strings where supported. Regex dialects differ between JavaScript, PCRE2, Python, Java, .NET, Go and POSIX, so test with the production engine.

