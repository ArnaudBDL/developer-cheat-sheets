# Copilot Studio : Connectors

## Connector Uses

```text
Read business data
Create or update records
Invoke supported services
Integrate Microsoft and third-party systems
Expose custom APIs through custom connectors
```

## Review Checklist

```text
Connection owner
Authentication model
Delegated or application identity
Allowed operations
Data classification
Data policy compatibility
Rate and service limits
Error handling
Environment portability
```

Use least-privilege connections and separate production identities. Do not assume connector availability implies permission to expose its data. Test each connector under the exact identity and environment used after deployment.
