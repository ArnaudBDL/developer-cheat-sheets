# Java : Virtual Threads

## Virtual Thread

```java
Thread thread = Thread.ofVirtual().start(() -> handleRequest());
thread.join();
```

## Per-Task Executor

```java
try (ExecutorService executor = Executors.newVirtualThreadPerTaskExecutor()) {
    Future<Response> response = executor.submit(client::call);
    return response.get();
}
```

Virtual threads are suited to high-concurrency workloads dominated by blocking operations. They do not make CPU work faster. Keep concurrency bounded by downstream capacity and inspect pinning or thread-local assumptions when performance is unexpected.
