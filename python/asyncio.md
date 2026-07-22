# Python : Asyncio

## Coroutine

```python
import asyncio

async def fetch_all() -> list[str]:
    async with asyncio.TaskGroup() as group:
        tasks = [group.create_task(fetch(url)) for url in urls]
    return [task.result() for task in tasks]

results = asyncio.run(fetch_all())
```

Use `asyncio` for cooperative I/O-bound concurrency with async-compatible libraries. Avoid blocking calls in the event loop, bound concurrent operations, define timeouts, handle cancellation, and close clients and streams reliably.
