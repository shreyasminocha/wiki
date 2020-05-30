# Haskell

Haskell is a purely functional programming language.

**Disclaimer**: I'm no Haskell expert. These are just notes I'm compiling as I learn Haskell and as such, they may be prone to inaccuracies or glaring errors.

> “Functional languages excel at wholemeal programming, a term coined by Geraint Jones. Wholemeal programming means to think big: work with an entire list, rather than a sequence of elements; develop a solution space, rather than an individual solution; imagine a graph, rather than a single path. The wholemeal approach often offers new insights or provides new perspectives on a given problem. It is nicely complemented by the idea of projective programming: first solve a more general problem, then extract the interesting bits and pieces by transforming the general program into more specialised ones.”
>
> —Ralf Hinze

> There is no precise, accepted meaning for the term “functional”. But when we say that Haskell is a functional language, we usually have in mind two things:
>
> -   Functions are first-class, that is, functions are values which can be used in exactly the same ways as any other sort of value.
> -   The meaning of Haskell programs is centered around evaluating expressions rather than executing instructions.
>
> —[CIS194 by UPenn](https://www.seas.upenn.edu/~cis194/spring13/lectures/01-intro.html)

## About

Haskell:

-   is statically typed.
-   has type inference.
-   is lazy.
-   is cool and unique \(for people used to OO languages\).

## Basics

BTW functions \(and lots of other stuff\) in Haskell are immutable. FP is different from imperative languages in that it doesn't have the concept of state.

### Comments

Comments begin with `--` and run till the end of the line.

### Basic operators

#### Arithmetic

-   `+`
-   `-`
-   `*`
-   `/` \(float division\)

#### Boolean

-   `&&`
-   `||`
-   `not`

#### Logical

-   `==`
-   `/=` — "≠"
-   `>`
-   `<`
-   `>=`
-   `<=`

#### Other

-   `:` — "cons" operator. Adds something to the beginning of a list
-   `++` — concatenation operator
-   `!!` — list indexing operator. e.g. `[1, 2, 3] !! 2` gives `3`

### Basic in-built functions

-   `succ` — "successor"
-   `pred` — "predecessor"
-   `min`
-   `max`
-   `head` — first element of a list
-   `tail` — all but first element of a list
-   `last` — last element of a list
-   `init` — all but last element of a list
-   `length`
-   `null` — checks if a list is empty, that is, if it is `[]`
-   `reverse` — reverses a list
-   `take` — `take x y` returns the first `x` elements of list `y`
-   `drop` — `drop x y` removes and returns the first `x` elements of list `y`
-   `maximum` — returns the largest element of a list

    — `minimum` — `maximum`s brother

-   `sum` — ∑ over a list
-   `products` — ∏ over a list
-   `elem` — whether an element is in a list
-   `mod` — `mod x y` is the remainder when `y` is divided by `x`
-   `even`
-   `odd`
-   `div` — integer division.

Functions can also be called in the infix form. For example, `elem 2 [1, 2, 3]` is equivalent to `` 2 `elem` [1, 2, 3] ``.

### Functions

`ƒ x y = x*y` creates a function `ƒ` that "takes two parameters `x` and `y`" and returns their product. Quoting to indicate this is not exactly accurate, but suffices for the time-being.

#### Pattern matching

> Pattern matching consists of specifying patterns to which some data should conform and then checking to see if it does and deconstructing the data according to those patterns. When defining functions, you can define separate function bodies for different patterns.
>
> —LYAH

```haskell
factorial 0 = 1
factorial n = n * factorial (n - 1)
```

```haskell
addVectors (x1, y1) (x2, y2) = (x1 + x2, y1 + y2)
```

```haskell
length' [] = 0
length' (_:rest) = 1 + length' rest
```

```haskell
capital "" = "Empty string"
capital all@(x:xs) = "The first letter of " ++ all ++ " is " ++ [x]
```

While matching against an expression that uses `++` might be intuitive in some cases, this just can't be done.

#### Guards

```haskell
bmiTell bmi
    | bmi <= 18.5 = "Underweight"
    | bmi <= 25.0 = "Normal"
    | bmi <= 30.0 = "Overweight"
    | otherwise = "Obese"
```

```haskell
bmiTell weight height
    | weight / (height ^ 2) <= 18.5 = "Underweight"
    | weight / (height ^ 2) <= 25.0 = "Normal"
    | weight / (height ^ 2) <= 30.0 = "Overweight"
    | otherwise   = "Obese"
```

Guards can be written inline \(often at the cost of readability\).

#### `where`

```haskell
bmiTell weight height
    | bmi <= 18.5 = "Underweight"
    | bmi <= 25.0 = "Normal"
    | bmi <= 30.0 = "Overweight"
    | otherwise   = "Obese"
    where bmi = weight / (height ^ 2)
```

`where` bindings _must_ be aligned neatly as follows:

```haskell
bmiTell weight height
    | bmi <= thin = "Underweight"
    | bmi <= normal = "Normal"
    | bmi <= fat = "Overweight"
    | otherwise   = "Obese"
    where bmi = weight / (height ^ 2)
          thin = 18.5
          normal = 25.0
          fat = 30.0
```

`where` bindings are scoped to the function. `where` bindings can also be used to pattern match. `where` bindings can be nested.

#### `let`–`in` expression

`let <binding> in <expression>`

These are similar to `where` bindings in many respects. `where` bindings are syntactic constructs while `let`–`in` are expressions \(that evaluate to the expression after `in`\) themselves. Which to use when is often a stylistic choice.

`let` expressions are very versatile.

```haskell
4 * (let a = 9 in a + 1) + 2
```

```haskell
[let square x = x * x in (square 5, square 3, square 2)]
```

```haskell
(let (a,b,c) = (1,2,3) in a+b+c) * 100
```

```haskell
calcBmis pair = [bmi | (w, h) <- pair, let bmi = w / h ^ 2]
```

When we want to bind several variables on the same line, we separate the bindings with `;`.

#### `if`–`then`–`else` expressions

#### `case` expressions

They are … expressions!

```haskell
case <expression> of <pattern> -> <result>
                     <pattern> -> <result>
                     <pattern> -> <result>
                     …
```

### Ranges

`[1..20]` is a list with elements `1` to `20`. Similarly, `['a'..'f']` is a list with characters `'a'` through `'z'`. `[2,4..20]` is a list of all even numbers from `2` to `20`. Haskell range-step specifying capabilities don't extend beyond simple arithmetic progressions. `[20,19..1]` will work as expected, but `[20..1]` will not. Using floating points in ranges is not a good idea.

Haskell's cool in that you can create infinite lists. For example, `let x = [1,2..]` creates and stores an infinite list of natural numbers. Since Haskell is lazy, it does not evaluate the list until it needs to. `take 29 x` and `take 500 x` return the first 29 and 500 natural numbers respectively.

-   `cycle` — cycles a list into an infinite list
-   `repeat` — `repeat x` returns an infinite list containing infinite `x`s.

### List comprehensions

~~COOL!~~

-   `let perfectSquares = [x^2 | x <- [0..]]` — an infinite list of perfect squares
-   `` let evenNumbers = [x | x <- [0..], x `mod` 2 == 0] `` — a relatively ugly way of producing an infinite list of even numbers

Filtering is a common pattern in FP.

-   `[x*y | x <- [2,5,10], y <- [8,10,11]]` — multiplies all pairs \(x, y\) where `x` is an element of `[2,5,10]` and `y` is an element of `[8,10,11]`.

Here are a few more examples:

```haskell
let nouns = ["hobo","frog","pope"]
let adjectives = ["lazy","grouchy","scheming"]

let combos = [adjective ++ " " ++ noun | adjective <- adjectives, noun <- nouns]
```

```haskell
length' list = sum [1 | _ <- list]

-- `_` indicates that we don't care about what the element we derive from `list` actually is. We sum a list which is equivalent to a list with as many `1`s as the number of elements in `list`.
```

```haskell
stripSpaces str = [chr | chr <- str, chr /= ' ']
```

BTW nested list comprehensions are possible on nested lists.

### Tuples

Tuples:

-   are immutable
-   are typed — `(Int, Char)` is incompatible with `(Int, String)`. Also, `(Int, Int)` is incompatible with `(Int, Int, Int)`
-   are not "cons-able"

Functions on tuples:

-   `fst` — returns the first element of a tuple
-   `snd` — returns the second element of a tuple

[Some people advise against using tuples with &gt; 2 elements](https://www.seas.upenn.edu/~cis194/spring13/lectures/01-intro.html#pairs).

## Types and Typeclasses

As mentioned earlier, Haskell is statically typed. It has a powerful and "expressive" type system.

Haskell has type inference, but explicit types annotations have several benefits:

-   Serve as a form of documentation.
-   Some run-time errors wil now be compile-time errors.

### Common types

-   `Int` — bounded. 32 or 64 bits depending on the machine.
-   `Integer` — not bounded. `BigInteger` of sorts
-   `Float`
-   `Double`
-   `Bool`
-   `Char`

### Typeclasses

A typeclass is an interface of sorts that implements certain defined behaviour. If a type is a part of a typeclass, it will implement the behaviour that the typeclass defines.

The prefix `:t` can be used to examine the type of an expression in GHCi.

#### Common typeclasses

-   `Eq` — support equality testing
-   `Ord` — types whose values can be ordered. `Ordering` is a type that can be `GT`, `LT` or `EQ`.
-   `Show` — can be represented as strings, that is, they can be converted to strings.
-   `Read` — can be converted from strings
-   `Enum` — sequentially ordered types. Can be used in list ranges. Have `succ`s and `pred`s.
-   `Bounded` — have upper and lower bounds
-   `Num` — "numeric". Can behave like numbers.
-   `Integral` — "integers". Implements `Num`.
-   `Floating` — "floating point numbers". Also implements `Num`.

### Relevant functions

-   `compare`
-   `read`
-   `show`

The following are not functions, but polymorphic constants:

-   `minBound` — For example, `minBound :: Int`
-   `maxBound` — For example, `maxBound :: Int`

Whole numbers are also polymorphic constants — `20 :: Float`.

### Type annotations

```haskell
count :: Int
count = 0
```

`::` is to be read as "has the type".

```haskell
isPrime :: Int -> Bool
isPrime num = …
```

`isPrime` takes an `Int` as a parameter and returns a `Bool`.

```haskell
contains :: [Int] -> Int -> Bool
contains arr elem = …
```

`contains` takes a list of `Int` and an `Int` and returns a `Bool`. The reason for this slightly unintuitive syntax for functions that take more than one parameter has a very good reason that will come up later.

Names of types begin with uppercase letters.

#### Type variables

#### Class constraints

## Recursion

Recursion is an important pattern in FP. While the fibonacci sequence, factorial etc are cliché examples of recursion, many more functions can be written with recursion.

-   `maximum`
-   `replicate`
-   `reverse`
-   `zip`
-   `sum`
-   `product`

Obligatory cliché Haskell quicksort:

```haskell
quicksort (pivot:rest) =
    let lessThan = quicksort [x | x <- rest, x <= pivot]
        greaterThan = quicksort [x | x <- rest, x > pivot]
    in lessThan ++ [pivot] ++ greaterThan
```

> A successful Haskell programmer must think in haskell.

## Higher order functions

### Currying, Partial Applications

### Maps, filters

### Lambdas

### Folds

### Function application with `$`

### Function composition

## Resources

-   [LYAH](https://learnyouahaskell.com). Many examples here are adapted from LYAH.
-   [UPenn's CIS194](https://www.seas.upenn.edu/~cis194/spring13/lectures.html)
-   [Haskell awesome list](https://github.com/krispo/awesome-haskell)
-   [FP awesome list](https://github.com/xgrommx/awesome-functional-programming)
