# got

```sh
npm i got
```

```js
import got from "got";
```

```js
await got("https://example.com");
```

-   `got.get`
-   `got.post`
-   `got.put`
-   `got.patch`
-   `got.delete`
-   `got.head`

> Don't forget the `await`

## Using response body

```js
const response = await got("https://example.com");
const { body } = response;
const { data } = body;
```

## Search parameters

```js
await got.get("https://example.com/foo", {
    searchParams: {
        sort: "ascending",
        items: 100,
        page: 2,
    },
});
```

## Headers

```js
await got("https://example.com", {
    headers: {
        "user-agent": "got v1.0.0",
    },
});
```

## Extending

```js
const api = got.extend({
    prefixUrl: "https://api.example.com",
});

await api.get("/foo");
await api.delete("/foo");
```

## POST requests

```js
await got.post("https://example.com", {
    json: {
        name: "John",
    },
    responseType: "json",
});
```
