# Java : Files and I/O

## NIO Files

```java
Path path = Path.of("data", "settings.json");
String content = Files.readString(path, StandardCharsets.UTF_8);
Files.writeString(path, updated, StandardCharsets.UTF_8);
```

## Stream Large Files

```java
try (Stream<String> lines = Files.lines(path, StandardCharsets.UTF_8)) {
    lines.filter(line -> !line.isBlank()).forEach(System.out::println);
}
```

Use explicit charsets, try-with-resources, path normalization, size limits and safe temporary files. Never trust uploaded filenames or deserialize untrusted Java object streams.
