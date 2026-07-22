# REST : HTTP Methods

## Methods

```text
GET      Retrieve a representation
HEAD     Retrieve response metadata without a response body
POST     Submit data or create a subordinate resource
PUT      Create or replace the target resource
PATCH    Apply a partial modification
DELETE   Remove the target resource
OPTIONS  Describe communication options
```

## Safety and Idempotency

```text
Method   Safe   Idempotent
GET      Yes    Yes
HEAD     Yes    Yes
OPTIONS  Yes    Yes
PUT      No     Yes
DELETE   No     Yes
POST     No     No by default
PATCH    No     Not guaranteed
```

## Rules

- Do not use GET for state changes.
- Define PUT as replacement unless the contract explicitly says otherwise.
- Document the patch format used by PATCH.
- Return `Allow` when responding with `405 Method Not Allowed`.
- Preserve method semantics through gateways, proxies and clients.
