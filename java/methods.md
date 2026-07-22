# Java : Methods

## Declaration

```java
public static BigDecimal calculateTotal(
        List<BigDecimal> amounts,
        BigDecimal taxRate) {
    BigDecimal subtotal = amounts.stream()
            .reduce(BigDecimal.ZERO, BigDecimal::add);
    return subtotal.multiply(BigDecimal.ONE.add(taxRate));
}
```

## Overloading

```java
void send(String message) { }
void send(String message, Duration timeout) { }
```

Java passes arguments by value, including object references. Keep methods focused, validate public boundaries, avoid ambiguous overloads, return consistent abstractions, and use varargs only when the call remains unambiguous.
