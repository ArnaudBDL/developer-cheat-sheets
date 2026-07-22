# Java : Control Structures

## Conditions and Loops

```java
if (score >= 80) {
    grade = "A";
} else if (score >= 60) {
    grade = "B";
} else {
    grade = "C";
}

for (Order order : orders) {
    process(order);
}

while (!queue.isEmpty()) {
    process(queue.remove());
}
```

## Switch Expression

```java
String label = switch (status) {
    case NEW -> "New";
    case ACTIVE -> "Active";
    case CLOSED -> "Closed";
};
```

Keep control flow shallow, use early returns where they improve clarity, and ensure every switch over evolving inputs has deliberate fallback behavior.
