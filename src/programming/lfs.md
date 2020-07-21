# Linux from Scratch

> Version 9.1 (March 1st, 2020)

## Packages

### `Zlib-1.2.11`

compression-decompression

-   `libz`

### `Bzip2-1.0.8`

compression-decompression

#### Programs

`bzip2`, `bunzip2` primarily.

Also `bz{cat,cmp,diff,egrep,fgrep,grep,less,more}` among others.

#### Libraries

-   `libbz2`

### `Xz-5.2.4`

compression-decompression

#### Programs

`lzma`, `unlzma`, `xz`, `unxz` primarily.

`{lz,xz}{cat,cmp,diff,egrep,fgrep,grep,less,more}`

#### Libraries

-   `liblzma`

### `File-5.38`

determine filetypes of files

#### Programs

`file`

#### Libraries

-   `libmagic` — magic number recognition

### `Readline-8.0`

command-line editing and history

#### Libraries

-   `libreadline` — commands for repl input manipulation
-   `libhistory` — handle command-line history lines

### `M4-1.4.18`

macro processor

#### Programs

`m4`

### `Bc-2.5.3`

arbitrary precision number processing

#### Programs

`bc`, `dc` (rpn)

### `Binutils-2.34`

linker, assembler, and other stuff for handling object files

##### Programs

…

#### Libraries

…

### `GMP-6.2.0`

math libs

#### Libraries

-   `libgmp` — math functions
-   `libgmpxx` — math functions, but for C++

### `MPFR-4.0.2`

arbitrary precision math

#### Libraries

`libmpfr`

### `MPC-1.1.0`

complex number math

#### Libraries

`libmpc`

### `Attr-2.4.48`

file extended attributes

#### Programs

`attr`, `{get,set}fattr`

#### Libraries

`libattr`

### `Acl-2.2.53`

access control lists. fine-grained file/dir access control

#### Programs

-   `chacl` — "change ACL"
-   `{get,set}facl`

#### Libraries

`libacl`

### `Shadow-4.8.1`

tools to securely handle passwords

#### Programs

`ch{age,fn,passwd,sh}`

`chgpasswd`

`group{add,del,mems,mod}`

`gp{ck,conv,unconv}`

`user{add,del,mod}`

…

### `GCC-9.2.0`

> gnu compiler collection

c compiler

#### Programs

`{c,g}++`

`{,g}cc`

`gcov{,-dump,-tool}` — coverage testing tool

#### Libraries

…

### `Pkg-config-0.29.2`

### `Ncurses-6.2`

"libraries for terminal-independent handling of character screens"

### `Libcap-2.31`

"capabilities" (aka privileges)

### `Sed-4.8`

stream editor. find-replace

`sed`

### `Psmisc-23.2`

display info about running processes

### `Iana-Etc-2.30`

data for network services|protocols

Installs `/etc/protocols` and `/etc/services`

### `Bison-3.5.2`

parser generator

-   `bison` — given rules generates parser code
-   `yacc` ("yet another compiler compiler")

*   `liby`

### `Flex-2.6.4`

### `Grep-3.4`

find with regex

### `Bash-5.0`

shell

### `Libtool-2.4.6`

### `GDBM-1.18.1`

database utils. key-value stores

### `Gperf-3.1`

### `Expat-2.2.9`

### `Inetutils-1.9.4`

### `Perl-5.30.1`

### `XML::Parser-2.46`

### `Intltool-0.51.0`

i18n

### `Autoconf-2.69`

### `Automake-1.16.1`

### `Kmod-26`

kernel modules

### `Gettext-0.20.1`

i18n

### `Libelf from Elfutils-0.178`

executable and linked files

### `Libffi-3.3`

### `OpenSSL-1.1.1d`

### `Python-3.8.1`

### `Ninja-1.10.0`

simple build system

### `Meson-0.53.1`

another simple build system

### `Coreutils-8.31`

buncha random unix-ey tools

### `Check-0.14.0`

testing/assertion

### `Diffutils-3.7`

diff and siblings

### `Gawk-5.0.1`

### `Findutils-4.7.0`

finding files and things

### `Groff-1.22.4`

document processing

### `GRUB-2.04`

> grand unified bootloader

bootloader

### `Less-551`

pager

### `Gzip-1.10`

compression-decompression

### `Zstd-1.4.4`

compression-decompression

### `IPRoute2-5.5.0`

### `Kbd-2.2.0`

### `Libpipeline-1.5.2`

### `Make-4.3`

build systems

### `Patch-2.7.6`

apply patches (typically) created via diff

### `Man-DB-2.9.0`

man pages.

### `Tar-1.32`

### `Texinfo-6.7`

info pages. man pages, except longer.

### `Vim-8.2.0190`

vim.
