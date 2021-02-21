# JavaScript

## Constructs

`for … of` loops through the items of an iterable.

`for … in` loops through the keys of an object.

Using `for … in` is discouraged.

```diff
- for (const key in obj) {
+ for (const key of Object.keys(obj)) {
```

## Array

### Functional

- `filter`
- `reduce(callback, init)` — `callback: (acc, current, idx, array)`
- `map`
- `forEach`
- `some`
- `every`

### Search

```js
['foo', 'bar', 'baz'].includes('bar')
// true
```

### 

```js
[{ id: 2 }, { id: 3 }, { id: 9 }].find((item) => item.id === 3);
// { id: 3 }
```

## `Object`

### `Object.assign`

>   Copy the values of all of the enumerable own properties from one or more source objects to a target object. Returns the target object.

```js
Object.assign(defaults, passed); // Mutates `defaults`
const options = Object.assign({}, defaults, passed); // Doesn't mutate `defaults`
```



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

