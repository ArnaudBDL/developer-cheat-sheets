# Python : Installation

## Verify

```bash
python --version
python -m pip --version
python -c "import sys; print(sys.executable)"
```

## Project Setup

```bash
mkdir application
cd application
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

On Windows PowerShell, activate with `.venv\Scripts\Activate.ps1`. Install Python from an approved distribution, select an explicitly supported version, and use `python -m pip` so package installation targets the intended interpreter.
