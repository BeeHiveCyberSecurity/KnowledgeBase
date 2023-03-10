# Rebuilding a Source Package

Kali Linux is [easy to customize at a per-package level](broken-reference), and it’s equally simple to make modifications to individual [packages](https://pkg.kali.org/) and rebuild them from their source code for inclusion in your custom ISO or on your desktop install.

Accomplishing this is a simple three-step process:

* use **apt** to pull down the package sources
* modify them as needed
* rebuild the package using the Debian tools.

In this example, we will rebuild the [libfreefare](https://github.com/nfc-tools/libfreefare) package in order to add some extra hardcoded Mifare access keys into the mifare-format tool.

Before anything else, ensure that the `deb-src` line in `/etc/apt/sources.list` is not commented out.

[Downloading the Package Source](broken-reference)

```
:~$ # Get the source package
:~$ sudo apt update
:~$ apt source libfreefare
:~$ cd libfreefare-0.4.0/
```

[Edit the Package Source Code](broken-reference)

Make the changes needed to the source code of the package. In our case, we modify an example file, mifare-classic-format.c:

```
:~$ vim examples/mifare-classic-format.c
```

[Check for Build Dependencies](broken-reference)

Check for any build dependencies the package may have. These need to be installed before you can build the package:

```
:~$ dpkg-checkbuilddeps
```

The output should be similar to the following, depending on what packages you already have installed. If **dpkg-checkbuilddeps** returns no output, that means you can proceed with the build, all of the dependencies are already satisfied:

```
dpkg-checkbuilddeps: Unmet build dependencies: dh-autoreconf libnfc-dev libssl-dev
```

[Install Build Dependencies](broken-reference)

Install any build dependencies if needed, as shown in the output of **dpkg-checkbuilddeps**:

```
:~$ sudo apt install -y dh-autoreconf libnfc-dev libssl-dev
```

[Build the Modified Package](broken-reference)

With all of the dependencies installed, the **dpkg-buildpackage** command is all it takes to build your new version:

```
:~$ dpkg-buildpackage
```

[Install the New Package](broken-reference)

If the build completes without errors, you’ll be able to install your newly-created package with **dpkg**:

```
:~$ sudo dpkg -i ../libfreefare*.deb
```
