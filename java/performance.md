# Java : Performance

## JDK Diagnostics

```bash
jcmd <pid> VM.version
jcmd <pid> GC.heap_info
jstack <pid>
jmap -histo <pid>
```

## Optimization Order

```text
Define target
Measure representative workload
Inspect CPU, allocation, garbage collection, locks and I/O
Fix algorithmic or architectural bottlenecks
Benchmark the change
Monitor production behavior
```

Use a proper benchmark harness for microbenchmarks, warm up the JVM, avoid optimizing from intuition, and preserve correctness, readability and security while tuning.
