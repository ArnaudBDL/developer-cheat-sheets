# Python : Dependencies

## Package Operations

```bash
python -m pip install package-name
python -m pip install --upgrade package-name
python -m pip uninstall package-name
python -m pip list
python -m pip show package-name
python -m pip check
```

## Repeatability

```bash
python -m pip install -r requirements.txt
python -m pip freeze > requirements-lock.txt
```

Use the project's selected dependency-management workflow, pin reproducible application deployments, review transitive dependencies, and never install untrusted packages based only on a familiar-looking name.
