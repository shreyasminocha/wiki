# nginx

>   Engine X

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



## Logging

```
log_format minimal '[$time_local] $status "$request" $body_bytes_sent bytes'
```

```
access_log path minimal;
```

```
error_log path severity
```

Default severity: `error`

