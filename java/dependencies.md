# Java : Dependencies

## Maven Dependency

```xml
<dependency>
  <groupId>org.example</groupId>
  <artifactId>library</artifactId>
  <version>1.2.3</version>
</dependency>
```

## Gradle Dependency

```kotlin
dependencies {
    implementation("org.example:library:1.2.3")
    testImplementation("org.junit.jupiter:junit-jupiter:5.12.0")
}
```

Review provenance and licenses, inspect transitive dependencies, use dependency locking or constraints where supported, scan known vulnerabilities, and test upgrades before production release.
