# Unix CLI Tools

## File management

### Wipe empty space

```sh
dd if=/dev/zero of=out bs=1M count=1024
shred -n 5 --remove out
```

## General

### `date`

```sh
date
```

```sh
date +"%Y-%m-%d"
```

```sh
date +%s
```

