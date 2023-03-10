# NanoPi NEO Plus2

The [NanoPi NEO Plus2](http://nanopi.io/nanopi-neo-plus2.html) has an Allwinner H5, Quad Core Cortex™-A53 (ARMv8 64-bit) processor with Triple Core Mali-450 MP4 GPU and 1GB DDR3 RAM. The NanoPi NEO Plus2 has an 8GB eMMC, which is too small for a default Kali installation, so we run from an external microSD card.

By default, the Kali Linux NanoPi NEO Plus2 image contains the [**kali-linux-default** metapackage](https://www.kali.org/docs/general-use/metapackages/) similar to most other platforms. If you wish to install extra tools please refer to our [metapackages page](https://www.kali.org/docs/general-use/metapackages/).

[Kali on NanoPi NEO Plus2 - Build-Script Instructions](broken-reference)

Kali does not provide pre-built images for download, but you can still generate one by cloning the [Kali-ARM Build-Scripts](https://gitlab.com/kalilinux/build-scripts/kali-arm) repository on GitLab, and follow the _README.md_ file’s instructions. The script to use is `nanopi-neo-plus2.sh`.

Once the build script finishes running, you will have an “img.xz” file in the `images` directory where you ran the script from. At that point, the instructions are the same as if you had downloaded a pre-built image.

The easiest way to generate these images is **from within a pre-existing Kali Linux environment**.

[Kali on NanoPi NEO Plus2 - User Instructions](broken-reference)

To install Kali on your NanoPi NEO Plus2, follow these instructions:

1. Get a fast microSD card with at least 16GB capacity. Class 10 cards are highly recommended.
2. Use the [**dd**](https://packages.debian.org/testing/dd) utility to image this file to your microSD card (same process as [making a Kali USB](https://www.kali.org/docs/usb/live-usb-install-with-windows/).

In our example, we assume the storage device is located at `/dev/sdb`. Do _not_ simply copy these value, **change this to the correct drive path**.

This process will wipe out your microSD card. If you choose the wrong storage device, you may wipe out your computers hard disk.

```
$ xzcat images/kali-linux-2022.4-nanopi-neo-plus2-arm64.img.xz | sudo dd of=/dev/sdb bs=4M status=progres
```

This process can take a while, depending on your PC, your microSD card speed, and the size of the Kali Linux image.

Once the _dd_ operation is complete, boot up the NanoPi NEO Plus2 with the microSD card plugged in.

You should be able to [log in to Kali](https://www.kali.org/docs/introduction/default-credentials/).

[Kali on the NanoPi NEO Plus2 - Tips](broken-reference)

The NanoPi NEO Plus2 will attempt to boot from the microSD card first if one is plugged in.

The wireless chipset is an Ampak AP6210, which is a rebranded Cypress (formerly Broadcom) Wireless card, so enterprising users may be able to get [nexmon](https://github.com/seemoo-lab/nexmon) working, if the work was put in.

If you want to change boot arguments/the kernel command line, you will need to edit the `/boot/boot.cmd` file, and then run `mkimage -C none -A arm -T script -d /boot/boot.cmd /boot/boot.scr`.
