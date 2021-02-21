# Git on a server

SSH daemon must be running, of course and `git` must be installed and on the `PATH`.

Create a `git` user.

Add ssh public keys to their `.ssh/authorized_keys` [^1]

Change the `git` user's shell to `git-shell`, lest they may wreak havoc.

Optionally, set up:

-   `git-http-backend`
-   gitweb, gitlist, … whatever  you fancy

[^1]: Consider adding `no-port-forwarding,no-X11-forwarding,no-agent-forwarding,no-pty`

## Permissions after pushes

`core.sharedRepository`: `group`, `all`, or octal permission bits.

```sh
git init --bare --shared[=all]
```

