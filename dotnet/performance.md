# .NET : Performance

## Measure

```bash
dotnet-counters monitor --process-id <pid>
dotnet-trace collect --process-id <pid>
dotnet-gcdump collect --process-id <pid>
```

## Optimization Order

```text
Define target
Measure representative workloads
Inspect CPU, allocations, GC, locks, I/O and downstream latency
Fix algorithmic and architectural bottlenecks
Benchmark changes
Monitor production
```

Use asynchronous I/O where appropriate, pool only measured hot-path resources, avoid unnecessary allocations, and never trade correctness or security for unmeasured speed.
