# Git

## Commit case-change file renames

```sh
git mv -f README.md readme.md
```

## GPG sign commits

```conf
[user]
    …
    email = example@example.com
    signingkey = 00000000
```

### Verify commits

```sh
git verify-commit c567d83
```

## Rename branches

```sh
git branch -m old new
```

## Githooks

### Executing local hooks from global hooks

```
#!/usr/bin/env bash

if [ -e ./.git/hooks/commit-msg ]; then
    ./.git/hooks/commit-msg "$@"
fi

…
```

### Hooks won't work

`chmod +x`?

## Push to upstream by default

> Just set your `push.default` to `upstream` to push branches to their upstreams (which is the same that pull will pull from […]), rather than pushing branches to ones matching in name (which is the default setting for `push.default` — matching).
>
> —[Brian Campbell](https://stackoverflow.com/users/69755/brian-campbell) on [Stack Overflow](https://stackoverflow.com/a/5739015)

```conf
[push]
    default = upstream
```

Useful for easily pushing to a remote branch with a name different from that of the local branch. Long-form method:

```sh
git push origin local-branch:remote-branch
```

## Patches

### Generating patches

```sh
git format-patch --to example@example.com head~..head
```

## Applying patches

```sh
git apply 0001-Example.patch
```

```sh
git am 0001-Example.patch
```

## `send-email`

```ini
[sendemail]
    smtpserver = mail.example.com
    smtpuser = foo
    smtpencryption = tls
    smtpserverport = 587
    from = foo-alias@example.com
    confirm = auto
```

```sh
git send-email --to '~sircmpwn/email-test-drive@lists.sr.ht' head^
```

```sh
git send-email --annotate -v2 head^
```

