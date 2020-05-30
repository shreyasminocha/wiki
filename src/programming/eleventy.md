# Eleventy

```sh
npm i -g @11ty/eleventy
```

-   `.eleventy.js`
-   `.eleventyignore`



-   `dir`
    -   `input`
    -   `output`
    -   `includes`
    -   `layouts`
    -   `data`

```js
conf.addPassthroughCopy({
    static: '/'
});
```

## Setting a layout for a collection

If the collection is `collection/`, set common keys in `collection/collection.json`:

```json
{
    "tags": "collection",
    "layout": "../layouts/collection.pug"
}
```

## Frontmatter keys in layout files

They're globals.

```md
---
name: Foo
chairperson: bar
​```
```

```pug
extends /layouts/base.pug

block content
	p=name
	p=chairperson
```

