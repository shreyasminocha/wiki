# Fish

## Loops

```text
for file in *.txt;
    echo "$file";
end
```

```text
while read word;
    echo "$word"
end < /usr/share/dict/words
```

```text
while test -f foo;
    true
end
```

## Conditions

```text
if test $status -ne 0;
    echo "oop—"
end
```

-   `-eq`
-   `-ne`
-   `-gt`
-   `-ge`
-   `-lt`
-   `-le`

*   `-f`
*   `-d`

```text
if ...;
    echo something
else if ...;
    echo something_else
else;
    echo something_else_altogether
end
```

## Variables

```text
set foo hi
```

-   `-l` — scoped local to the current block
-   `-g` — global scope
-   `-x` — environment variable

## Command Substitution

```text
set total (math "$total+1")
```
