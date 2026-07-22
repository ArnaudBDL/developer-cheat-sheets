# OWASP : Checklists

## Design

- [ ] Assets and trust boundaries identified
- [ ] Security requirements documented
- [ ] Threat model reviewed
- [ ] Authorization model defined
- [ ] Abuse and failure cases considered
- [ ] Data retention and recovery defined

## Implementation

- [ ] Inputs validated at trusted boundaries
- [ ] Queries and commands parameterized
- [ ] Secrets stored outside source code
- [ ] Authentication and sessions hardened
- [ ] Object and tenant authorization enforced
- [ ] Sensitive output minimized
- [ ] Dependencies pinned and reviewed

## Deployment

- [ ] Production hardening applied
- [ ] Debug features disabled
- [ ] Public exposure reviewed
- [ ] TLS and headers validated
- [ ] Least-privilege identities configured
- [ ] Logs, alerts and retention configured
- [ ] Backup and restoration tested

## Release Gate

- [ ] Security tests passed
- [ ] Critical findings resolved or formally accepted
- [ ] OpenAPI and operational documentation current
- [ ] Dependency and secret scans passed
- [ ] Monitoring and incident ownership confirmed
- [ ] Rollback procedure validated
