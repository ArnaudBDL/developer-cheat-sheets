# .NET : Security

## Core Controls

```text
Validate untrusted input
Authorize operations and resources
Use parameterized data access
Protect secrets outside source code
Require TLS
Constrain outbound requests and file paths
Avoid unsafe deserialization
Audit dependencies
Apply request, payload and execution limits
```

## Random Token

```csharp
string token = Convert.ToHexString(RandomNumberGenerator.GetBytes(32));
```

Do not use ordinary pseudo-random generators for security tokens. Keep authorization in application and source systems, not in UI state or model prompts.
