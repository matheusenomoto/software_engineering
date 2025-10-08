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
| 400 |  |  |