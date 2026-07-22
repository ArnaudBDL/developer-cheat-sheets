# Java : Generics

## Generic Type

```java
public final class Box<T> {
    private final T value;

    public Box(T value) {
        this.value = value;
    }

    public T value() {
        return value;
    }
}
```

## Bounds

```java
static double sum(List<? extends Number> values) { }
static void addDefaults(List<? super Integer> values) { }
```

Use generics for compile-time type safety. Remember type erasure, avoid raw types, and use bounded wildcards deliberately: producers commonly use `extends`, consumers commonly use `super`.
