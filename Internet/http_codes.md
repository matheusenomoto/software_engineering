# HTTP Codes

* Class 1xx: Informational Responses
* Class 2xx: Success
* Class 3xx: Redirection
* Class 4xx: Client Errors
* Class 5xx: Server Errors

| Code | Official | Description & When to Use |
|:----:|:--------:|:--------------------------|
| 100 | Continue | Indicates that the initial part of the request has been received and the client should continue sending the rest. Rarely used in common applications. |
| 101 | Switching Protocols | The server agrees to switch the connection protocol (e.g., from HTTP to WebSocket) at the client’s request. |
| 200 | Ok | The most common success code. Indicates the request succeeded. Use it for GET requests (data returned in the body) or POST/PUT (result of the operation returned in the body). |
| 201 | Created | The request succeeded and a new resource was created as a result. Essential in REST APIs for POST or PUT requests that create new objects. |
| 202 | Accepted | The request has been accepted for processing, but the processing has not been completed yet. Useful for asynchronous operations (e.g., video processing, heavy report generation). |
| 204 | No Content | The request succeeded, but there is no content to return in the response body. Perfect for DELETE requests where you just need confirmation of deletion. |
| 301 | Moved Permanently | The requested resource has been permanently moved to a new URL. Browsers and search engines (like Google) will update their links. Crucial for SEO. |
| 302 | Found (Temporary Redirect) | The resource is temporarily located at a different URL. The client should continue using the original URL for future requests. |
| 304 | Not Modified | A cache-related response. Indicates that the resource has not changed since the client’s last request. The browser may use its cached version, saving bandwidth. |
| 400 | Bad Request | The server could not understand the request due to invalid syntax (e.g., malformed JSON, missing parameters). The generic client-side error. |
| 401 | Unauthorized | The request requires authentication. The client is either unauthenticated (not logged in) or provided invalid credentials. |
| 403 | Forbidden | The client is authenticated (logged in) but does not have permission to access the requested resource. Unlike 401, the server knows who the client is but denies access. |
| 404 | Not Found | The most famous web error. The server could not find the requested resource. The URL does not match anything on the server. |
| 405 | Method Not Allowed | The HTTP method used (e.g., POST) is not allowed for the requested resource (which may only accept GET). |
| 409 | Conflict | The request could not be completed due to a conflict with the current state of the resource. A classic example: trying to create a user with an email that already exists. |
| 429 | Too Many Requests | The client sent too many requests in a given period (rate limiting). The client should wait before retrying. |
| 500 | Internal Server Error | A generic server error. Something went wrong on the server and it does not know how to handle the situation (e.g., a bug, database access failure). |
| 502 | Bad Gateway | The server, acting as a gateway or proxy, received an invalid response from the upstream server. |
| 503 | Service Unavailable | The server is not ready to handle the request. Typically a temporary condition such as traffic overload or scheduled maintenance. |
| 504 | Gateway Timeout | The server, acting as a gateway, did not receive a timely response from the upstream server. |