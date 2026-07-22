# API Design : Methods

## Method Semantics

```text
GET      Retrieve a representation
HEAD     Retrieve response metadata without a response body
POST     Create a subordinate resource or process a command
PUT      Create or replace the target resource representation
PATCH    Apply a partial modification
DELETE   Remove the target resource
OPTIONS  Describe communication options
```

## Examples

```http
GET /users/42
POST /users
PUT /users/42
PATCH /users/42
DELETE /users/42
```

## Idempotency

```http
Idempotency-Key: 4e398f3e-7c8c-46ba-a049-9ac1294e20e2
```

For retry-sensitive creation or payment operations, define an idempotency policy, key scope, retention period and conflict behavior.
