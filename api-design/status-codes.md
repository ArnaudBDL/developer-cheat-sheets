# API Design : Status Codes

## Successful Responses

```text
200 OK             Successful request with a response representation
201 Created        Resource created
202 Accepted       Request accepted for asynchronous processing
204 No Content     Successful request without a response body
206 Partial Content Partial representation returned
```

## Client Errors

```text
400 Bad Request            Invalid request syntax or structure
401 Unauthorized           Authentication is required or invalid
403 Forbidden              Authenticated caller lacks permission
404 Not Found              Resource is not available at the target URI
405 Method Not Allowed     Method is not supported for the target
409 Conflict               Request conflicts with current resource state
412 Precondition Failed    Conditional request precondition failed
415 Unsupported Media Type Unsupported request media type
422 Unprocessable Content  Semantically invalid content
429 Too Many Requests      Request rate exceeded
```

## Server Errors

```text
500 Internal Server Error
502 Bad Gateway
503 Service Unavailable
504 Gateway Timeout
```

Return the HTTP status that describes the protocol outcome. Do not report every failure as `200 OK`.
