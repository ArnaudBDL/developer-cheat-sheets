# Python : Functions

## Definition

```python
def calculate_total(
    amounts: list[float],
    *,
    tax_rate: float = 0.0,
) -> float:
    subtotal = sum(amounts)
    return subtotal * (1 + tax_rate)
```

## Parameter Forms

```text
Positional parameters
Keyword parameters
Positional-only parameters with /
Keyword-only parameters after *
Variable positional arguments with *args
Variable keyword arguments with **kwargs
```

Avoid mutable default values. Keep functions focused, document externally visible contracts, validate boundary inputs, and return consistent types.
