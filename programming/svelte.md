# Svelte

Svelte is a "framework-less framework".

* No virtual DOM
* Single-file components
* Templating-like syntax

```text
<script>
    ...
</script>

<style>
    ...
</style>

…
```

```markup
<script>
let subject = "world";
</script>

<span>Hello {subject}</span>
```

Styles are _component-scoped_.

## Templating

```markup
{#if condition}
    <code>true</code>
{/if}
```

```markup
{#if condition}
    <code>true</code>
{:else}
    <code>true</code>
{/if}
```

```markup
{#if condition}
    …
{:else if other}
    …
{:else}
    …
{/if}
```

```markup
{#each array as element}
    <li>{element}</li>
{/each}
```

```markup
{#each array as element, index}
    <li>{element}</li>
{/each}
```

```markup
{#each array as {a, b, c}}
    <li>{element}</li>
{/each}
```

## Reactivity

```markup
<script>
    let num = 1;
    $: let double = num * 2;
    $: let triple = num * 3;
</script>

<input type="range" bind:value={num}>

<li>x: {num}</li>
<li>2x: {double}</li>
<li>3x: {triple}</li>
```

> `$:` means "re-run whenever these values change"

## Events

* `on:click`
* `on:mousemove`
* `on:submit`
* …
* `|once`
* `|preventDefault`

## Bindings

* `bind:value`

```markup
<script>
    let name;
</script>

<input bind:value={name} placeholder="John Doe">

<p>
    Hi {name}
</p>
```

* `bind:checked`
* `bind:group`

## Links

* [Official examples](https://svelte.dev/examples)

