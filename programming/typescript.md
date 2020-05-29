# TypeScript

## Type annotations

Intended _contract_ of a variable/function.

```text
let foo: string;
```

```text
function bar(a: string, b?: number): void {
    …
}
```

```text
(foo: string) => boolean
```

```text
let primes: number[];
```

## Interfaces

```text
interface Rule {
    readonly message: string,
    readonly test?: (commitMessage: string) => boolean;
}
```

## Type aliases

## Enums

```text
enum Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY,
    SATURDAY, SUNDAY
}
```

```text
enum Result {
    pass = 'type',
    fail = 'fail',
    info = 'info'
}​
```

## Classes
