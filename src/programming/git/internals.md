# Git Internals

Git is not magic.

> Git is fundamentally a content-addressable filesystem with a VCS user interface written on top of it.

"Porcelain" — Higher-level, more user-friendly commands.

"Plumbing" — Lower-level commands meant for interfacing with the VCS toolkit.

```text
$ ls -F1 .git
```

-   `config` — project-specific configuration
-   `index` — git stores staging index information in this file
-   `HEAD` — points to the currently checked-out branch
-   `hooks/` — client-side and server-side hooks
-   `info/` — global exclude file
-   `objects/` — stores content
-   `refs/` — "stores pointers into commit objects in that data \(branches, tags, remotes and more\)"

## Objects

> \[A\]t the core of Git is a simple key-value data store. What this means is that you can insert any kind of content into a Git repository, for which Git will hand you back a unique key you can use later to retrieve that content.

### Blob

Git is similar to the UNIX file system in some ways. However, git was designed to work with files that don't change often. File content is saved as a "blob" in git. Two files with the same content anywhere in the world will be stored as the same blob by git. The blob does not store metadata such as the file's name or mode.

`git hash-object` takes a file, optionally writes it to the database \(with `-w`\), and prints the 40-character SHA checksum hash by which it will be identified. The checksum itself is a checksum of the file contents along with a header.

```text
$ echo 'foo' > a.txt
$ echo 'foo' > b.txt
$ git init

$ git hash-object -w a.txt
257cc5642cb1a054f08cc83f2d943e56fd3ebe99

$ git hash-object -w b.txt
257cc5642cb1a054f08cc83f2d943e56fd3ebe99
```

```text
$ find .git/objects -type f
```

The above lists "files" in `.git/objects`. For example, `.git/objects/25/7cc5642cb1a054f08cc83f2d943e56fd3ebe99`. `25` are the first two characters of the hash, `7cc5642cb1a054f08cc83f2d943e56fd3ebe99` are the other 38. Git presumably does this subdirectory-thing to avoid constraints imposed by some filesystems on the maximum number of files in a directory.

```text
$ git cat-file -t 257cc5642cb1a054f08cc83f2d943e56fd3ebe99
blob
```

```text
$ git cat-file blob 257cc5642cb1a054f08cc83f2d943e56fd3ebe99
foo

$ git cat-file -p 257cc5642cb1a054f08cc83f2d943e56fd3ebe99
foo
```

### Tree

Trees group blobs and store the metadata associated with the blobs. They correspond loosely with the concept of directories in the UNIX filesystem.

```text
$ git cat-file -p 'master^{tree}'
```

```text
100644 blob 664e5860e5a29097e673e14639dbae33d71098f4    .eslintignore   [
100644 blob 0d20ca61dfe1a9ad35862d403aa3e582c21cda51    .eslintrc.yml
100644 blob d124b533c0893da4a15aa5447bf4d5a5583a9fec    .gitignore
100644 blob 8a4cf69715b929acd1683ad1fb6af4c5cbd2ff64    .stylelintrc.yml
040000 tree 7c73db8e4c875dbb9c75e54139048f3ce763c89b    archetypes
100644 blob b82eeb6841cf2a466ee3c7fcf05cbf829a6a2ca7    config.yml
040000 tree e395cf748a2199479e1d8e835c6fe90066983adb    content
100644 blob 8feae855aeb0f392eaad037cf3534fe22a26a525    gulpfile.js
040000 tree 8f4aa58a3fa460e1a52c40f55f8a4749e8ace81f    layouts
100644 blob dd85817db646256ba284950fda7ecffd541a42ad    package-lock.json
100644 blob 5abbb73bc45270fff66606f0edf0e4bce35c6197    package.json
100644 blob 0c576833121dc7ff51f73b3ad399e2a6ea9b2235    readme.md
040000 tree 6a1072a6112e0903cc8ab48373234bbee4e4acf9    static
```

Directories are stored as trees.

Git normally creates a tree by taking the state of the index \(staging area\) and writing a series of tree objects from it. To create a tree manually, we must first set up an index by staging some files.

```text
$ git update-index --add --cacheinfo 100644 257cc5642cb1a054f08cc83f2d943e56fd3ebe99 b.txt
```

Git's modes are based on UNIX's, but are much stricter. The following are the valid modes for files:

| Mode     | Description |
| :------- | :---------- |
| `100644` | Normal      |
| `100755` | Executable  |
| `120000` | Symlink     |

`git write-tree` writes the staging area to a tree.

```text
$ git write-tree
b6643bc0af3fefb3ea606e41cee107ec08fbbed8
```

```text
$ git cat-file -t b6643bc0af3fefb3ea606e41cee107ec08fbbed8
tree
```

```text
$ git cat-file -p b6643bc0af3fefb3ea606e41cee107ec08fbbed8
100644 blob 257cc5642cb1a054f08cc83f2d943e56fd3ebe99    b.txt
```

## See also

-   [https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain)
-   [https://jwiegley.github.io/git-from-the-bottom-up/](https://jwiegley.github.io/git-from-the-bottom-up/)
