# Python : Exceptions

## Handling

```python
try:
    value = int(raw_value)
except ValueError as error:
    raise ConfigurationError("Invalid integer") from error
else:
    use(value)
finally:
    release_resource()
```

## Custom Exception

```python
class ConfigurationError(Exception):
    pass
```

Catch the narrowest useful exception, preserve causality with `raise ... from ...`, avoid empty `except` blocks, and do not expose confidential runtime details in public errors.
