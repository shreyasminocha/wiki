# nginx

> Engine X

```
location modifier pattern {
	…
}
```

Modifiers:

-   (none) — prefix match
-   `=` — exact match
-   `~` — case-sensitive regex
-   `~*` — case-insensitive regex
-   `^~` — non-regex

```nginx
client_max_body_size 25M;
```

```nginx
add_header x-header "value";
```

## Logging

```nginx
log_format minimal '[$time_local] $status "$request" $body_bytes_sent bytes'
```

```nginx
access_log path minimal;
```

```nginx
error_log path severity;
```

Default severity: `error`

## Clean URLs

```nginx
try_files $uri $uri.html $uri/index.html =404;

rewrite ^/index(?:\.html|/)?$ / permanent;
rewrite ^/(.*)/index(?:\.html|/)?$ /$1 permanent;
rewrite ^/(.*)(?:\.html|/)$ /$1 permanent;
```

—[_URLs Without Trailing Slash or Extension_](https://christopheraue.net/design/urls-without-trailing-slash-or-extension)
