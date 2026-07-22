# Python : Comprehensions

## Forms

```python
squares = [number * number for number in numbers]
even = {number for number in numbers if number % 2 == 0}
index = {item.id: item for item in items}
generator = (transform(item) for item in items)
```

## Guidance

- Use comprehensions for compact transformations and filters.
- Prefer a normal loop when conditions, side effects or nesting become difficult to read.
- Use generator expressions for lazy iteration.
- Avoid hidden expensive work inside a comprehension.
- Do not use comprehensions only for side effects.
