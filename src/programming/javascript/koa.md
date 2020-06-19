# Koa

Koa is a minimal web framework for node.js.

> Only methods that are common to nearly all HTTP servers are integrated directly into Koa's small ~570 SLOC codebase. This includes things like content negotiation, normalization of node inconsistencies, redirection, and a few others.
>
> Koa is not bundled with any middleware.

This is quite unlike express.

There is an ecosystem of npm modules around koa that implement all sorts of useful middleware.

Koa leverages `async` functions, allowing us to avoid callback hell and implement error handling with greater ease.

Koa is awesome \[citation needed\].

## Useful modules

-   [`koa-router`](https://npmjs.com/package/koa-router)
-   [`koa-body`](https://npmjs.com/package/koa-body)
-   [`koa-views`](https://npmjs.com/package/koa-views)
-   [`koa-static`](https://npmjs.com/package/koa-static)
-   [`koa-session`](https://npmjs.com/package/koa-session)
-   [`koa-passport`](https://npmjs.com/package/koa-passport)

## Minimal Koa app

```js
import Koa from "koa";
import Router from "koa-router";

const app = new Koa();
const router = new Router();

router.get("/", async (ctx) => {
    ctx.body = "response";
});

app.use(router.routes());
app.use(router.allowedMethods())

app.listen(process.env.PORT || 3000);
```

