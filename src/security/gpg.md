# GnuPG CLI

## Decrypt files

```sh
gpg --decrypt file.pdf.gpg > file.pdf
```

## Verifying signatures

```sh
gpg --verify dl.zip.sig dl.zip
```

## Import keys

```sh
curl https://example.com/user.asc | gpg --import
```

