# Unix CLI Tools

## Disks and drives

### Wipe empty space

```sh
sudo dd if=/dev/zero of=out bs=1M count=1024
shred -n 5 --remove out
```

### Bootable drive

```sh
sudo dd if=Downloads/os.iso of=/dev/disk3 bs=4m && sync
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

