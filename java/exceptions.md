# Java : Exceptions

## Handling

```java
try {
    return parser.parse(input);
} catch (ParseException exception) {
    throw new ConfigurationException("Invalid configuration", exception);
} finally {
    resource.close();
}
```

## Try with Resources

```java
try (BufferedReader reader = Files.newBufferedReader(path, UTF_8)) {
    return reader.readLine();
}
```

Catch the narrowest useful exception, preserve the cause, use checked exceptions for recoverable contractual conditions only when they improve the API, and never expose confidential internals in public error messages.
