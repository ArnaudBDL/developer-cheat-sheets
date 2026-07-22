# Python : Packages

## Layout

```text
project/
├── pyproject.toml
├── README.md
├── src/
│   └── application/
│       ├── __init__.py
│       └── main.py
└── tests/
```

## Build

```bash
python -m pip install --upgrade build
python -m build
```

Declare project metadata and build configuration in `pyproject.toml`, keep importable code in a package, test the built distribution, and avoid importing from the repository root by accident.
