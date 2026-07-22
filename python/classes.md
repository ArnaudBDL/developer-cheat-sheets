# Python : Classes

## Class

```python
class User:
    def __init__(self, identifier: int, name: str) -> None:
        self.identifier = identifier
        self.name = name

    def display_name(self) -> str:
        return self.name
```

## Inheritance

```python
class Administrator(User):
    def __init__(self, identifier: int, name: str, permissions: set[str]) -> None:
        super().__init__(identifier, name)
        self.permissions = permissions
```

Prefer composition for reusable behavior, keep invariants inside the class boundary, use properties deliberately, and implement special methods only when their semantics are natural.
