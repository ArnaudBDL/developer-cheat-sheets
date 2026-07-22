# Java : Interfaces

## Interface

```java
public interface MessageSender {
    void send(Message message);

    default boolean isAvailable() {
        return true;
    }
}
```

## Implementation

```java
public final class EmailSender implements MessageSender {
    @Override
    public void send(Message message) {
        // Send through an authorized client.
    }
}
```

Use interfaces for stable behavioral contracts. Keep them cohesive, avoid leaking implementation types, and evolve public interfaces carefully because added abstract methods can break implementers.
