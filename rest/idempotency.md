# REST : Idempotency

## Meaning

```text
An idempotent method has the same intended server effect when an identical
request is applied once or several times.
```

## Method Semantics

```text
GET, HEAD, OPTIONS, PUT and DELETE are idempotent by HTTP semantics.
POST is not idempotent by default.
PATCH is not guaranteed to be idempotent.
```

## Idempotency Key Pattern

```http
POST /payments HTTP/1.1
Idempotency-Key: 4b581ad8-67cc-49d7-a27a-b528fe45f7a1
Content-Type: application/json
```

## Server Controls

```text
Bind the key to caller, operation and request fingerprint.
Store the completed outcome for a bounded period.
Reject reuse with different request content.
Handle concurrent duplicates atomically.
Return the original outcome for a valid replay.
```

Idempotency does not mean every response is byte-for-byte identical. Logging and timestamps can differ while the intended resource effect remains the same.
