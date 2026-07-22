# Python : Troubleshooting

## Environment Checks

```bash
python --version
python -c "import sys; print(sys.executable); print(sys.path)"
python -m pip --version
python -m pip list
python -m pip check
```

## Diagnostics

```bash
python -X dev -m application
python -m trace --trace script.py
python -m pdb script.py
```

## Common Causes

```text
Wrong interpreter or inactive virtual environment
Package installed for another interpreter
Import shadowed by a local filename
Circular import
Incorrect working directory
Missing environment variable
Encoding or path difference
Unsupported Python or dependency version
Blocking call inside asynchronous code
```

Capture the exact command, interpreter path, traceback and minimal reproducer. Remove secrets and personal data before sharing diagnostics.
