# REST : Status Codes

## Success

```text
200 OK
201 Created
202 Accepted
204 No Content
206 Partial Content
```

## Redirection and Caching

```text
301 Moved Permanently
302 Found
303 See Other
304 Not Modified
307 Temporary Redirect
308 Permanent Redirect
```

## Client Errors

```text
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
405 Method Not Allowed
409 Conflict
412 Precondition Failed
415 Unsupported Media Type
422 Unprocessable Content
429 Too Many Requests
```

## Server Errors

```text
500 Internal Server Error
502 Bad Gateway
503 Service Unavailable
504 Gateway Timeout
```

Use the most specific status supported by the actual outcome. A `201` response should identify the created resource, commonly with `Location`.
