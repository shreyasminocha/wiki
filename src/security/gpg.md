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

## Trust levels

-   Ultimate — it's your own key
-   Full — you've verified the identity of the key owner _and signed their public key_
-   Marginal — enough to make the key show up as "valid"