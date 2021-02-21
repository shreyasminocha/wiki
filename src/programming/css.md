# CSS

### Make list items wrap vertically

Use `column-count`.

```css
.container {
    column-count: 8;
}
```

## Grid

```pug
div#container
	header
	aside
	main
	footer
```

```css
#container {
    display: grid;
    grid-template-areas:
    	"left header header"
        "left content content"
        "footer footer footer";
}

header { grid-area: header; }
aside { grid-area: left; }
main { grid-area: content; }
footer { grid-area: footer; }
```

## Center things

```css
.hero {
    display: grid;
    place-items: center;
}
```

