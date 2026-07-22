# Java : Security

## Core Controls

```text
Validate untrusted input
Use parameterized database queries
Avoid unsafe object deserialization
Restrict reflection and dynamic loading
Keep secrets outside source code
Use SecureRandom for security-sensitive randomness
Pin and scan dependencies
Validate file paths and outbound URLs
Apply time, memory and payload limits
```

```java
SecureRandom random = new SecureRandom();
byte[] token = new byte[32];
random.nextBytes(token);
```

Enforce authorization in application and source systems. Do not use assertions for security validation because assertions can be disabled.
