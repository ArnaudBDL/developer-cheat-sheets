# Python : Concurrency

## Models

```text
threading             Shared-memory concurrency, commonly for blocking I/O
multiprocessing       Separate processes for CPU-bound parallel work
concurrent.futures    High-level thread and process executors
asyncio               Cooperative asynchronous I/O
```

## Executor

```python
from concurrent.futures import ThreadPoolExecutor

with ThreadPoolExecutor(max_workers=4) as executor:
    results = list(executor.map(fetch, urls))
```

Protect shared mutable state, bound concurrency, propagate cancellation and errors, and benchmark with the actual workload before choosing a model.
