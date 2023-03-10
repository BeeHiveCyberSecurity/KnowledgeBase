# CuBox-i4Pro

SolidRun’s [CuBox-i4Pro](https://www.solid-run.com/product/cubox-i4pro/) is the “world’s smallest computer”. The specifications are Quad core i.MX6 1GHZ processor, 2GB RAM, Gigabit ethernet, eSata port, and microSD card slot.

_This image for the “Freescale” based NOT the “Marvell” based (original)._

By default, the Kali Linux CuBox-i4Pro image contains the [**kali-linux-default** metapackage](https://www.kali.org/docs/general-use/metapackages/) similar to most other platforms. If you wish to install extra tools please refer to our [metapackages page](https://www.kali.org/docs/general-use/metapackages/).

The build script for the CuBox-i4Pro has not been converted to the new style, so builds may fail. If you are planning to build for this board, please consider updating the script to the new way, and submitting it as a merge request.

[Kali on CuBox-i4Pro - Build-Script Instructions](broken-reference)

Kali does not provide pre-built images for download, but you can still generate one by cloning the [Kali-ARM Build-Scripts](https://gitlab.com/kalilinux/build-scripts/kali-arm) repository on GitLab, and follow the _README.md_ file’s instructions. The script to use is `cubox-i4pro.sh`.

Once the build script finishes running, you will have an “img” file in the directory where you ran the script from. At that point, the instructions are the same as if you had downloaded a pre-built image.

The easiest way to generate these images is **from within a pre-existing Kali Linux environment**.

[Kali on CuBox-i4Pro - User Instructions](broken-reference)

To install Kali on your Cubox-i4Pro, follow these instructions:

1. Get a fast microSD card with at least 16GB capacity. Class 10 cards are highly recommended.
2. Use the [**dd**](https://packages.debian.org/testing/dd) utility to image this file to your microSD card (same process as [making a Kali USB](https://www.kali.org/docs/usb/live-usb-install-with-windows/).

In our example, we assume the storage device is located at `/dev/sdb`. Do _not_ simply copy these value, **change this to the correct drive path**.

This process will wipe out your microSD card. If you choose the wrong storage device, you may wipe out your computers hard disk.

```
$ xzcat kali-linux-2022.4-cubox-i4pro-armhf.img.xz | sudo dd of=/dev/sdb bs=4M status=progres
```

This process can take a while, depending on your PC, your microSD card speed, and the size of the Kali Linux image.

Once the _dd_ operation is complete, boot up the CuBox-i4Pro with the microSD card plugged in.

You should be able to [log in to Kali](https://www.kali.org/docs/introduction/default-credentials/).
