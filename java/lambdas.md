# Java : Lambdas

## Lambda and Method Reference

```java
Predicate<User> active = user -> user.active();
Function<User, String> name = User::displayName;
Consumer<String> printer = System.out::println;
Supplier<Instant> clock = Instant::now;
```

Lambdas implement functional interfaces with one abstract method. Captured local variables must be final or effectively final. Keep lambdas short and move complex business logic into named methods for readability and testing.
