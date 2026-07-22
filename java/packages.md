# Java : Packages

## Layout

```text
src/main/java/com/example/application/Main.java
src/main/java/com/example/application/service/OrderService.java
src/test/java/com/example/application/service/OrderServiceTest.java
```

## Declaration and Import

```java
package com.example.application.service;

import java.time.Instant;
import com.example.application.model.Order;
```

Use reverse-domain package naming, align directories with package names, avoid wildcard imports, and keep public APIs in intentional packages rather than exposing implementation classes accidentally.
