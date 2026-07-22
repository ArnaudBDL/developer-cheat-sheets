# OWASP : Authentication

## Controls

- Use a trusted identity provider where appropriate.
- Require multi-factor authentication for sensitive access.
- Rate-limit and monitor authentication and recovery workflows.
- Prevent account enumeration through consistent responses.
- Store passwords with an adaptive password hashing function.
- Generate high-entropy session identifiers and rotate them after authentication.
- Set secure, HTTP-only and appropriate SameSite cookie attributes.
- Expire, revoke and invalidate sessions predictably.
- Reauthenticate before high-risk operations.
- Protect password reset and account recovery as authentication flows.

## Review Checklist

```text
Registration
Sign-in
Multi-factor authentication
Password change
Password reset
Account recovery
Session creation
Session rotation
Logout and revocation
Remember-me behavior
Brute-force protection
Error messages
```
