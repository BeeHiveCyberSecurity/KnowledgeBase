# Verify your ISO image

It is important to verify the integrity and authenticity of your ISO image.

The integrity check confirms that your ISO image was properly downloaded and that your local file is an exact copy of the file present on the download servers. An error during the download could result in a corrupted file and trigger random issues during the installation.

The authenticity check confirms that the ISO image you downloaded was signed by Linux Mint, and thus that it isn’t a modified or malicious copy made by somebody else.

### Download the SHA256 sums provided by Linux Mint[¶](broken-reference)

All [download mirrors](https://www.linuxmint.com/mirrors.php) provide the ISO images, a `sha256sum.txt` file and a `sha256sum.txt.gpg` file. You should be able to find these files in the same place you downloaded the ISO image from.

If you can’t find them, browse the [Heanet download mirror](https://ftp.heanet.ie/mirrors/linuxmint.com/stable/) and click the version of the Linux Mint release you downloaded.

Download both `sha256sum.txt` and `sha256sum.txt.gpg`.

Do not copy their content, use “right-click->Save Link As…” to download the files themselves and do not modify them in any way.

### Integrity check[¶](broken-reference)

To check the integrity of your local ISO file, generate its SHA256 sum and compare it with the sum present in `sha256sum.txt`.

```
sha256sum -b yourfile.iso
```

If the sums match, your ISO image was successfully downloaded. If they don’t, download it again.

***

### Authenticity check[¶](broken-reference)

To verify the authenticity of `sha256sum.txt`, check the signature of `sha256sum.txt.gpg` by following the steps below.

#### Import the Linux Mint signing key:[¶](broken-reference)

```
gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-key "27DE B156 44C6 B3CF 3BD7  D291 300F 846B A25B AE09"
```

Note

If gpg complains about the key ID, try the following commands instead:

```
gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-key A25BAE09
gpg --list-key --with-fingerprint A25BAE09
```

Check the output of the last command, to make sure the fingerprint is `27DE B156 44C6 B3CF 3BD7 D291 300F 846B A25B AE09` (with or without spaces).

#### Verify the authenticity of sha256sum.txt:[¶](broken-reference)

```
gpg --verify sha256sum.txt.gpg sha256sum.txt
```

The output of the last command should tell you that the file signature is `good` and that it was signed with the `A25BAE09` key.

Note

GPG might warn you that the Linux Mint signature is not trusted by your computer. This is expected and perfectly normal.
