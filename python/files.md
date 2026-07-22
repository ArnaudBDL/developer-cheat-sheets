# Python : Files

## Text and JSON

```python
from pathlib import Path
import json

path = Path("settings.json")
with path.open("r", encoding="utf-8") as stream:
    settings = json.load(stream)
```

## Atomic-Style Replacement

```python
temporary = path.with_suffix(".tmp")
temporary.write_text(content, encoding="utf-8")
temporary.replace(path)
```

Use context managers, explicit encodings, `pathlib`, size limits, validated paths and safe temporary files. Never trust uploaded filenames or deserialize untrusted pickle data.
