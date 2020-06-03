# JavaScript

## `Date`

### `toLocalDateString(locales?, options?)`

#### `options`

-   `weekday`
    -   `long`
    -   `short`
    -   `narrow`
-   `era`
    -   `long`
    -   `short`
    -   `narrow`
-   `year`
    -   `numeric`
    -   `2-digit`
-   `month`
    -   `numeric`
    -   `2-digit`
    -   `long`
    -   `short`
    -   `narrow`
-   `day`
    -   `numeric`
    -   `two-digit`
-   `hour`, `minute`, `second`
    -   `numeric`
    -   `two-digit`
-   `timeZoneName`
    -   `long`
    -   `short`

```js
const options = { weekday: "short", day: "numeric", month: "short" };
const today = new Date();
console.log(today.toLocaleDateString(undefined, options)); // Tue, Jun 2
```

