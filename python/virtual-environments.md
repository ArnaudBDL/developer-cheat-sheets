# Python : Virtual Environments

## Create and Activate

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
```

## Deactivate

```bash
deactivate
```

A virtual environment isolates an interpreter and project packages from other applications. Recreate it from declared dependencies rather than committing `.venv/` to source control.
