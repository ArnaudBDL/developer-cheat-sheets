# Java : Modules

## Module Descriptor

```java
module com.example.application {
    requires java.net.http;
    exports com.example.application.api;
    opens com.example.application.model to com.example.framework;
}
```

## Compile and Run

```bash
javac -d out --module-source-path src -m com.example.application
java --module-path out -m com.example.application/com.example.application.Main
```

Export only intended APIs, use `opens` narrowly for reflection, and analyze automatic-module and split-package risks before modularizing existing systems.
