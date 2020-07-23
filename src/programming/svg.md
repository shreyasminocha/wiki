# Scalable Vector Graphics

```svg
<svg 
     viewbox="0 0 100 100"
     width="100" height="100"
     version="1.1" xmlns="http://www.w3.org/2000/svg"
>
    …
</svg>
```

Strokes are centered across paths by default. This may complicate width and coordinate calculation.

`stroke-alignment := "inside"  | "outside" | "center"`

## Shapes

### `rect`

```svg
<rect x="0" y="0" width="100" height="100" stroke="black" />
```

### `line`

```svg
<line x1="0" y1="0" x2="100" y2="100" stroke="black" />
```

### `polyline`

```svg
<polyline points="0,0, 0,20 20,20 20,0 0,0" stroke="black" />
```

Each of the points defined are connected by lines.

