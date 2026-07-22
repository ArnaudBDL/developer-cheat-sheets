# API Design : Versioning

## Path Versioning

```http
GET /v1/users/42
```

## Header Versioning

```http
Accept: application/vnd.example.v1+json
```

## Compatibility

```text
Usually compatible
  Add an optional response field
  Add an optional request field
  Add a new endpoint

Usually breaking
  Remove or rename a field
  Change a field type
  Change validation semantics
  Change authentication requirements
  Remove an accepted enum value
```

## Lifecycle

Define release, support, deprecation, migration and retirement policies. Publish breaking changes before deployment and provide a migration path.
