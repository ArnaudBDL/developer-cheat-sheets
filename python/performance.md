# Python : Performance

## Measure

```bash
python -m timeit "sum(range(1000))"
python -m cProfile -o profile.stats -m application
```

## Optimization Order

```text
Define the latency or throughput target
Profile representative workloads
Fix algorithmic and I/O bottlenecks
Reduce unnecessary allocations and conversions
Choose appropriate collections and concurrency
Measure again
```

Prefer generators for streaming data, batch external calls where safe, cache only stable results with bounded growth, and never trade correctness or security for unmeasured speed.
