# HTTP Security Headers

-   `X-Content-Type-Options`

    -   `nosniff`

-   `X-Frame-Options`

    -   `SAMEORIGIN`

-   `X-XSS-Protection`

    -   `1; mode-block`

-   `Strict-Transport-Security`

    -   `max-age=31536000; includeSubDomains`

-   `Referer-Policy`

    -   `same-origin`

-   `Content-Security`

    -   `default-src: 'self'`

    Some directives:

    - `default-src`
    - `script-src` `object-src`
    - `style-src`  `img-src` `media-src` `font-src`
    - `frame-src`
    - `connect-src`
    - `form-action`

    Values:

    -   (Possibly incomplete) Domains
        -   Wildcards permitted for some parts
    -   `'none'`
    -   `'self'` — doesn't include subdomains
    -   `'unsafe-inline'` — Inline JS and CSS
    -   `'unsafe-eval'`

-   `Feature-Policy`

## Links

-   [Interactive CSP generator](https://report-uri.com/home/generate)