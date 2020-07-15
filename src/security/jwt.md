# JSON Web Tokens

Auth mechanism.

-   Backend
    -   has a secret key
-   Frontend
    -   sends a request with a header and a payload
-   Backend
    -   signs the header+payload with the *secret key*
        -   using the algorithm specified in the header
    -   returns the token to the frontend



-   Frontend

    -   must send the token with every request to protected routes.

        ```
        Authorization: Bearer <token>
        ```

-   Backend
    -   then independently computes the signature of the header+payload.
        -   If it matches the signature in the token, access is granted.

Since the frontend doesn't know the *secret key*, it cannot create signatures that will check out at the backend. Thus, the frontend cannot successfully tamper with the payload.

>   Can be used for stateless auth!

Parts:

-   header
-   payload
-   signature

```
header.payload.signature
```

## Parts

![Screenshot from the JWT debugger with two parts—'Encoded' and 'Decoded'](https://cdn.auth0.com/blog/legacy-app-auth/legacy-app-auth-5.png)

### Header

```json
{
    "alg": "HS256",
    "typ": "JWT"
}
```

**Base64 Encode**.

### Payload

Contains *claims*.

```json
{
    "sub": "9234",
    "username": "john",
    "admin": false
}
```

**Base64 Encode**.

>   Payload is *tamper-proof*, but publically visible.

### Signature verification

```js
    const computedSignature = HMACSHA256(
        base64UrlEncode(token.header) + "." +
        base64UrlEncode(token.payload),
        secret
    );

    if (token.signature === computedSignature) {
        return true;
    }

    return false;
```

## Links

-   [JWT Introduction](https://jwt.io/introduction)
-   [JWT Debugger](https://jwt.io/#debugger-io)
-   [RFC 7519](https://tools.ietf.org/html/rfc7519)