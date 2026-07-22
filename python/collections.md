# Python : Collections

## Core Collections

```python
numbers = [1, 2, 3]
point = (10, 20)
unique = {"a", "b"}
user = {"id": 42, "name": "Arnaud"}
immutable = frozenset({"read", "write"})
```

## Common Operations

```python
numbers.append(4)
first, *middle, last = numbers
user.get("email")
unique.add("c")
for key, value in user.items():
    print(key, value)
```

Choose collections by semantics, not convenience. Do not mutate a collection while directly iterating over it unless the behavior is deliberate and safe.
