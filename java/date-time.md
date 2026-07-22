# Java : Date and Time

## java.time

```java
Instant now = Instant.now();
LocalDate date = LocalDate.of(2026, 7, 22);
ZonedDateTime paris = now.atZone(ZoneId.of("Europe/Paris"));
Duration timeout = Duration.ofSeconds(30);
```

## Formatting

```java
DateTimeFormatter formatter = DateTimeFormatter.ISO_OFFSET_DATE_TIME;
String value = formatter.format(paris);
```

Use `Instant` for machine timestamps, explicit zones for civil time, and `LocalDate` when no time or zone exists. Avoid legacy mutable date types in new APIs.
