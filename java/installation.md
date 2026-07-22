# Java : Installation

## Verify the JDK

```bash
java --version
javac --version
jshell --version
```

## Compile and Run

```bash
javac -d out src/com/example/Main.java
java -cp out com.example.Main
```

Install an approved JDK rather than only a runtime. Pin a supported Java release in development and CI, configure `JAVA_HOME` consistently, and verify which executable is selected with `which java` or the platform equivalent.
