# Java : Testing

## JUnit Example

```java
import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

class CalculatorTest {
    @Test
    void addsTwoNumbers() {
        assertEquals(5, Calculator.add(2, 3));
    }
}
```

## Run

```bash
mvn test
./gradlew test
```

Test public behavior, boundaries, failures and security cases. Keep tests deterministic, isolate external services, avoid excessive mocking of internal details, and verify the built artifact in integration tests.
