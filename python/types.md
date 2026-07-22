# Python : Types

## Built-in Types

```python
flag = True
count = 42
ratio = 3.14
value = 2 + 3j
text = "Python"
data = b"bytes"
missing = None
```

## Inspection and Conversion

```python
isinstance(count, int)
int("42")
float("3.14")
str(42)
bool(value)
```

Python is dynamically typed, but values still have concrete runtime types. Avoid relying on truthiness when `None`, zero and empty collections have different business meanings.
