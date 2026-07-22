# Java : Classes

## Class

```java
public final class User {
    private final long id;
    private String displayName;

    public User(long id, String displayName) {
        this.id = id;
        this.displayName = Objects.requireNonNull(displayName);
    }

    public long id() {
        return id;
    }
}
```

Encapsulate mutable state, establish invariants in constructors or factories, minimize inheritance, and prefer immutability where practical. Implement `equals`, `hashCode` and `toString` consistently when instances have value semantics.
