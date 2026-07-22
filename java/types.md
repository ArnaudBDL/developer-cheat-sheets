# Java : Types

## Primitive Types

```java
boolean active = true;
byte small = 10;
short quantity = 1000;
int count = 42;
long total = 10_000L;
float ratio = 1.5F;
double price = 19.99;
char initial = 'J';
```

## Reference Types

```java
String name = "Arnaud";
Integer boxed = 42;
Object value = name;
String missing = null;
```

Primitive values are not references. Use wrapper types only when nullability, generics or APIs require them. Avoid accidental unboxing of null values and document whether a reference may be null.
