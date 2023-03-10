# CuBox

The [CuBox](https://www.solid-run.com/product/cubox-carrier-base/) is a low end, low cost ARM computer. Despite its less-than-stellar specifications, its affordability makes it an excellent option for a tiny Linux system and it can do far more than act as a media PC.

_This image for the “Marvell” based (original) NOT the “Freescale” based._

By default, the Kali Linux CuBox image **does not** contains the [**kali-linux-default** metapackage](https://www.kali.org/docs/general-use/metapackages/) which is often found in Kali platforms. If you wish to install extra tools please refer to our [metapackages page](https://www.kali.org/docs/general-use/metapackages/).

The build script for the CuBox has not been converted to the new style, so builds may fail. If you are planning to build for this board, please consider updating the script to the new way, and submitting it as a merge request.

[Kali on CuBox - Build-Script Instructions](broken-reference)

Kali does not provide pre-built images for download, but you can still generate one by cloning the [Kali-ARM Build-Scripts](https://gitlab.com/kalilinux/build-scripts/kali-arm) repository on GitLab, and follow the _README.md_ file’s instructions. The script to use is `cubox.sh`.

Once the build script finishes running, you will have an “img” file in the directory where you ran the script from. At that point, the instructions are the same as if you had downloaded a pre-built image.

The easiest way to generate these images is **from within a pre-existing Kali Linux environment**.

[Kali on CuBox - User Instructions](broken-reference)

To install Kali on your Cubox, follow these instructions:

1. Get a fast microSD card with at least 16GB capacity. Class 10 cards are highly recommended.
2. Use the [**dd**](https://packages.debian.org/testing/dd) utility to image this file to your microSD card (same process as [making a Kali USB](https://www.kali.org/docs/usb/live-usb-install-with-windows/).

In our example, we assume the storage device is located at `/dev/sdb`. Do _not_ simply copy these value, **change this to the correct drive path**.

This process will wipe out your microSD card. If you choose the wrong storage device, you may wipe out your computers hard disk.

```
$ xzcat kali-linux-2022.4-cubox-armhf.img.xz | sudo dd of=/dev/sdb bs=4M status=progress
```

This process can take a while, depending on your PC, your microSD card speed, and the size of the Kali Linux image.

Once the _dd_ operation is complete, boot up the CuBox with the microSD card plugged in.

You should be able to [log in to Kali](https://www.kali.org/docs/introduction/default-credentials/).
