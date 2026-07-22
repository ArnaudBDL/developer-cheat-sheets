# Python : Control Structures

## Conditions and Loops

```python
if score >= 80:
    grade = "A"
elif score >= 60:
    grade = "B"
else:
    grade = "C"

for item in items:
    process(item)

while queue:
    process(queue.pop())
```

## Pattern Matching

```python
match event:
    case {"type": "created", "id": identifier}:
        handle_created(identifier)
    case _:
        handle_unknown(event)
```

Use `break`, `continue`, loop `else`, and structural pattern matching only when they keep control flow clear and testable.
