# Python : Logging

## Configuration

```python
import logging

logging.basicConfig(
    level=logging.INFO,
    format="%(asctime)s %(levelname)s %(name)s %(message)s",
)
logger = logging.getLogger(__name__)
logger.info("Application started")
```

Use module loggers, structured context and appropriate severity. Never log passwords, tokens, private keys or unnecessary personal data. Configure handlers centrally, avoid duplicate handlers, and preserve correlation identifiers for distributed workflows.
