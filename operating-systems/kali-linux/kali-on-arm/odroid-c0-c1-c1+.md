# ODROID-C0/C1/C1+

The [ODROID-C1](https://www.hardkernel.com/shop/odroid-c1-2/) is a quad core 1.5GHz Cortex A5, with 1GB of RAM development board. Kali Linux fits on an external microSD card or on an eMMC module.

The ODROID-C0 and ODROID-C1+ are both essentiall the same base hardware, but with changed peripherals, so we can use the same image for all 3 of the devices.

By default, the Kali Linux ODROID-C images contains the [**kali-linux-default** metapackage](https://www.kali.org/docs/general-use/metapackages/) similar to most other platforms. If you wish to install extra tools please refer to our [metapackages page](https://www.kali.org/docs/general-use/metapackages/).

The build script for the ODROID-C0/C1/C1+ has not been converted to the new style, so builds may fail. If you are planning to build for this board, please consider updating the script to the new way, and submitting it as a merge request.

[Kali on ODROID-C0/C1/C1+ - Build-Script Instructions](broken-reference)

Kali does not provide pre-built images for download, but you can still generate one by cloning the [Kali-ARM Build-Scripts](https://gitlab.com/kalilinux/build-scripts/kali-arm) repository on GitLab, and follow the _README.md_ file’s instructions. The script to use is `odroid-c.sh`.

Once the build script finishes running, you will have an “img” file in the directory where you ran the script from. At that point, the instructions are the same as if you had downloaded a pre-built image.

The easiest way to generate these images is **from within a pre-existing Kali Linux environment**.

[Kali on ODROID-C0/C1/C1+ - User Instructions](broken-reference)

To install Kali on your ODROID-C0/C1/C1+, follow these instructions:

1. Get a fast microSD card or eMMC module with at least 16GB capacity. Class 10 cards are highly recommended.
2. Use the [**dd**](https://packages.debian.org/testing/dd) utility to image this file to your microSD card (same process as [making a Kali USB](https://www.kali.org/docs/usb/live-usb-install-with-windows/).

In our example, we assume the storage device is located at `/dev/sdb`. Do _not_ simply copy these value, **change this to the correct drive path**.

This process will wipe out your microSD card or eMMC. If you choose the wrong storage device, you may wipe out your computers hard disk.

```
$ xzcat kali-linux-2022.4-odroid-c-armhf.img.xz | sudo dd of=/dev/sdb bs=4M status=progres
```

This process can take a while, depending on your PC, your microSD card or eMMC’s speed, and the size of the Kali Linux image.

Once the _dd_ operation is complete, boot up the ODROID-C0/C1/C1+ with the microSD card or eMMC plugged in.

You should be able to [log in to Kali](https://www.kali.org/docs/introduction/default-credentials/).
