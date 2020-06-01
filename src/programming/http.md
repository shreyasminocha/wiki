# HTTP

-   client establishes TCP connection with server
-   client sends a request
-   server sends a response with a status code and, optionally, a body

## Request Methods

-   `GET` — retrieve resource
-   `POST` — submit an entity and cause side-effects on the server
-   `PUT` — replace the target resource with the payload
-   `PATCH` — partial modifications to a resource
-   `DELETE` — delete resource
-   `HEAD` — `GET` response sans the response body
-   `OPTIONS` — list of possible request methods for a resource
-   `CONNECT`
-   `TRACE`

## Cookies

When a response contains the `Set-Cookie` header, a cookie is set on the client.

```http
HTTP/2.0 200 OK
Set-Cookie: foo=bar
Set-Cookie: baz=baj
```

With subsequent requests, the client will include the `foo` and `baz` cookies  in the `Cookie` header.

```http
GET /path HTTP/2.0
Host: example.com
Cookie: foo=bar; baz=baj
```

### `Expires`

```http
…
Set-Cookie: foo=bar; Expires=Wed, 21 Oct 2021 07:28:00 GMT;
```

>   the time and date set is relative to the client

### Security

-   `Secure` — cookie sent only with HTTPS
-   `HttpOnly` — inaccessible via JavaScript. only sent and modified by requests and responses respectively

