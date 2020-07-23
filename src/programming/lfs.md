# Linux from Scratch

> Version 9.1 (March 1st, 2020)

## Packages

### `Zlib-1.2.11`

compression-decompression

-   `libz`

### `Bzip2-1.0.8`

compression-decompression

#### 

`bzip2`, `bunzip2` primarily.

Also `bz{cat,cmp,diff,egrep,fgrep,grep,less,more}` among others.

#### 

-   `libbz2`

### `Xz-5.2.4`

compression-decompression

#### 

`lzma`, `unlzma`, `xz`, `unxz` primarily.

`{lz,xz}{cat,cmp,diff,egrep,fgrep,grep,less,more}`

#### Libraries

-   `liblzma`

### `File-5.38`

determine filetypes of files

#### 

`file`

#### 

-   `libmagic` — magic number recognition

### `Readline-8.0`

command-line editing and history

#### 

-   `libreadline` — commands for repl input manipulation
-   `libhistory` — handle command-line history lines

### `M4-1.4.18`

macro processor

#### 

`m4`

### `Bc-2.5.3`

arbitrary precision number processing

#### 

`bc`, `dc` (rpn)

### `Binutils-2.34`

linker, assembler, and other stuff for handling object files

##### 

…

#### 

…

### `GMP-6.2.0`

math libs

#### 

-   `libgmp` — math functions
-   `libgmpxx` — math functions, but for C++

### `MPFR-4.0.2`

arbitrary precision math

#### 

`libmpfr`

### `MPC-1.1.0`

complex number math

#### 

`libmpc`

### `Attr-2.4.48`

file extended attributes

#### 

`attr`, `{get,set}fattr`

#### 

`libattr`

### `Acl-2.2.53`

access control lists. fine-grained file/dir access control

#### 

-   `chacl` — "change ACL"
-   `{get,set}facl`

#### 

`libacl`

### `Shadow-4.8.1`

tools to securely handle passwords

#### 

`ch{age,fn,passwd,sh}`

`chgpasswd`

`group{add,del,mems,mod}`

`gp{ck,conv,unconv}`

`user{add,del,mod}`

…

### `GCC-9.2.0`

> gnu compiler collection

c compiler

`{c,g}++`

`{,g}cc`

`gcov{,-dump,-tool}` — coverage testing tool

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

kinda like bison?

`flex`, `flex++`, …

`libfl`

### `Grep-3.4`

find with regex

`{e,f,}grep`

`e`: extended

`f`: "fixed strings"

### `Bash-5.0`

shell

`bash`, `bashbug`

### `Libtool-2.4.6`

generic library for consistent shared library support

### `GDBM-1.18.1`

>   GNU DB Manager

database utils. key-value stores. crud.

### `Gperf-3.1`

"generates a perfect hash function from a key set"

### `Expat-2.2.9`

parse XML with C

`xmlwf`. xml well-formed?

`libexpat`

### `Inetutils-1.9.4`

networking tools

-   `dnsdomainname`
-   `{,t}ftp`
-   `hostname`
-   `ifconfig`
-   `ping{,6}`
-   `talk`
-   `telnet`
-   `traceroute`

### `Perl-5.30.1`

>   Practical Extraction and Report Language

`perl{,bug,doc,ivp,thanks,5.30.1}`, `pod{…}` (documentation format), …

### `XML::Parser-2.46`

perl interface to expat

### `Intltool-0.51.0`

i18n tool to extract translatable strings from source files

`intltoolize`, `intltool-{extract,merge,prepare,update}`

### `Autoconf-2.69`

creates shell scripts to _auto-configure_ source code

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
