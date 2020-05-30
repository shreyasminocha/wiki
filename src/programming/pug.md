# Pug

Indentation-based. Indentation must be consistent.

```
doctype html
```

```
a(href="https://example.com")
```

```
nav
	ul
		li: a(href="https://example.com") Example
		li: a(href="https://example.com/1") One
		li: a(href="https://example.com/1") One
```

`li: a …` is shorthand for:

```
<li>
	<a>…</a>
</li>
```

```pug
.main //- <div class="main">
	…

#this //- <div id="this">
	…
	
button.link.button //- <button class="link button">
```

## Conditionals

```
if followers.length == 0
	p No followers
```

## Iteration

```
ul
	each user in activeUsers
		li: img(src=`/img/{user.id}`)
```

```
each val, key in {1: 'one', 2: 'two', 3: 'three'}
```

```
each val, index in ['zero', 'one', 'two']
```

## Includes

## Inheritance

## Interpolation

## Mixins

