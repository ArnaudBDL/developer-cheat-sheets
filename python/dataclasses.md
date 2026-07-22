# Python : Dataclasses

## Data Class

```python
from dataclasses import dataclass, field

@dataclass(frozen=True, slots=True)
class Product:
    identifier: str
    name: str
    tags: tuple[str, ...] = field(default_factory=tuple)
```

## Guidance

`@dataclass` can generate initialization, representation and comparison methods. Use `default_factory` for mutable defaults, `frozen=True` for immutable-style records, and `slots=True` when its restrictions and memory behavior fit the design. Validate business invariants explicitly.
