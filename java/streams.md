# Java : Streams

## Pipeline

```java
List<String> activeNames = users.stream()
        .filter(User::active)
        .map(User::displayName)
        .sorted()
        .toList();
```

## Reduction

```java
BigDecimal total = amounts.stream()
        .reduce(BigDecimal.ZERO, BigDecimal::add);
```

Streams describe transformations and reductions. Avoid side effects in intermediate operations, do not reuse a consumed stream, and do not assume parallel streams improve performance without measurement and thread-safety analysis.
