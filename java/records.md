# Java : Records

## Record

```java
public record Product(String id, String name, BigDecimal price) {
    public Product {
        Objects.requireNonNull(id);
        Objects.requireNonNull(name);
        if (price.signum() < 0) {
            throw new IllegalArgumentException("price must be non-negative");
        }
    }
}
```

Records are concise carriers for transparent data aggregates. Their components are final references, but referenced objects can still be mutable. Use compact constructors for invariants and avoid records where identity and encapsulated mutable lifecycle are central.
