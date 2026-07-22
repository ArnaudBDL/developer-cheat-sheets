# Java : Quick References

## JDK

```bash
java --version
javac --version
javac -d out src/com/example/Main.java
java -cp out com.example.Main
```

## Build

```bash
mvn clean verify
./gradlew clean build
```

## Diagnostics

```bash
jps -l
jcmd <pid> VM.command_line
jcmd <pid> Thread.print
jstack <pid>
```
