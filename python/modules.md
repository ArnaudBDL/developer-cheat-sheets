# Python : Modules

## Imports

```python
import pathlib
from collections import Counter
from application.services import calculate_total
```

## Executable Module

```python
def main() -> int:
    print("Application started")
    return 0

if __name__ == "__main__":
    raise SystemExit(main())
```

Use absolute imports for clarity, avoid wildcard imports, keep import-time side effects minimal, and run modules with `python -m package.module` when package import context matters.
