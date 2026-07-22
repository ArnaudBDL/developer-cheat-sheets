# API Design : Documentation

## OpenAPI Skeleton

```yaml
openapi: 3.1.0
info:
  title: Users API
  version: 1.0.0
servers:
  - url: https://api.example.com/v1
paths:
  /users/{userId}:
    get:
      operationId: getUser
      parameters:
        - name: userId
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: User found
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/User'
components:
  schemas:
    User:
      type: object
      required: [id, name]
      properties:
        id: { type: string }
        name: { type: string }
```

## Documentation Checklist

```text
Authentication
Endpoints and operations
Parameters and schemas
Examples
Errors
Pagination and filtering
Rate limits
Idempotency
Versioning and deprecation
Changelog
Support contact
```

Validate the OpenAPI document in CI and keep examples synchronized with the implementation.
