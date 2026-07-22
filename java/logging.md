# Java : Logging

## System Logger

```java
private static final System.Logger LOGGER =
        System.getLogger(Application.class.getName());

LOGGER.log(System.Logger.Level.INFO, "Application started");
```

Use the project's chosen logging facade and implementation consistently. Include correlation context, choose levels deliberately, centralize configuration, and never log passwords, tokens, private keys or unnecessary personal data.
