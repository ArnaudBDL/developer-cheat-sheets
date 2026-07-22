# Java : Enums

## Enum

```java
public enum Status {
    NEW,
    ACTIVE,
    CLOSED
}
```

## Enum with Behavior

```java
public enum Operation {
    ADD { double apply(double a, double b) { return a + b; } },
    SUBTRACT { double apply(double a, double b) { return a - b; } };

    abstract double apply(double a, double b);
}
```

Use enums for closed sets with stable symbolic values. Do not persist ordinal positions as business identifiers, and define explicit external values when serialized contracts must remain stable.
