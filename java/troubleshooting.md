# Java : Troubleshooting

## Environment

```bash
java --version
javac --version
echo "$JAVA_HOME"
java -XshowSettings:properties -version
```

## Runtime Diagnostics

```bash
jps -l
jcmd <pid> VM.command_line
jcmd <pid> Thread.print
jstack <pid>
```

## Common Causes

```text
JDK and bytecode version mismatch
Incorrect classpath or module path
Missing dependency
Duplicate dependency version
Wrong main class
Encoding or locale difference
Out-of-memory condition
Deadlock or blocked thread
Environment-specific configuration
```

Capture the exact command, JDK vendor and version, build-tool version, complete stack trace and minimal reproducer. Remove credentials and sensitive data before sharing diagnostics.
