# Java : Collections

## Core Interfaces

```java
List<String> names = new ArrayList<>();
Set<String> tags = new HashSet<>();
Map<String, User> users = new HashMap<>();
Deque<Job> jobs = new ArrayDeque<>();
```

## Immutable Factories

```java
List<String> roles = List.of("reader", "writer");
Map<String, Integer> limits = Map.of("small", 10, "large", 100);
```

The collections framework provides common interfaces, implementations and algorithms. Choose by ordering, uniqueness, lookup and concurrency needs. Do not modify immutable factory collections or structurally mutate ordinary collections during iteration.
