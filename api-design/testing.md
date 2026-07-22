# API Design : Testing

## Test Layers

```text
Unit tests
Schema validation
Contract tests
Integration tests
Authorization tests
End-to-end tests
Performance tests
Resilience tests
Security tests
Compatibility tests
```

## Request Test

```bash
curl --fail-with-body --silent --show-error   --request GET   --header 'Accept: application/json'   --header 'Authorization: Bearer TOKEN'   'https://api.example.com/v1/users/usr_42'
```

## Contract Assertions

```text
Documented operation exists
Request matches schema
Response matches schema
Status code matches outcome
Error representation is consistent
Undocumented fields are rejected or handled as specified
Authorization is enforced
Breaking changes are detected
```

## Boundary Cases

Test missing fields, invalid formats, maximum sizes, empty collections, duplicate requests, concurrency conflicts, expired credentials, forbidden objects, pagination boundaries and dependency failures.
