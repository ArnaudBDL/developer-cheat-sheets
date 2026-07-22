# Python : Typing

## Annotations

```python
from collections.abc import Iterable
from typing import Protocol

class Writer(Protocol):
    def write(self, value: str) -> None: ...

def total(values: Iterable[float]) -> float:
    return sum(values)
```

## Union and Optional Values

```python
def find(identifier: str) -> User | None:
    ...
```

Type hints support tooling and static analysis but are not automatic runtime validation. Keep public interfaces annotated, prefer precise types, and run the project's configured type checker in CI.
