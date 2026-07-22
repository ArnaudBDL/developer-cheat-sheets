# Java : Concurrency

## Executor Service

```java
try (ExecutorService executor = Executors.newFixedThreadPool(4)) {
    Future<Result> future = executor.submit(() -> performTask());
    Result result = future.get(30, TimeUnit.SECONDS);
}
```

## Concurrent Utilities

```text
ExecutorService and Future
CompletableFuture
BlockingQueue
ConcurrentHashMap
Semaphore and CountDownLatch
Atomic variables
Locks and conditions
```

Prefer standard `java.util.concurrent` building blocks to hand-built thread coordination. Bound pools and queues, preserve interruption, define timeouts, minimize shared mutable state, and test for races, deadlocks and starvation.
