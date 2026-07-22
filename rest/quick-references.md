# REST : Quick References

## HTTP methods

```text
GET     Read a resource
POST    Create a resource
PUT     Replace a resource
PATCH   Partially update a resource
DELETE  Delete a resource
```

## Headers

```http
Accept: application/json
Content-Type: application/json
Authorization: Bearer TOKEN
ETag: "version"
If-None-Match: "version"
```

## cURL

```bash
curl -i URL
curl -X POST URL -H "Content-Type: application/json" -d '{"name":"Ada"}'
curl -H "Authorization: Bearer TOKEN" URL
```
