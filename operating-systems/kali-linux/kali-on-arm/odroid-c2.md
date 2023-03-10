# ODROID-C2

The [ODROID-C2](https://wiki.odroid.com/odroid-c2/odroid-c2) has an Amlogic S905, Quad Core Cortex™-A53 (ARMv8 64-bit) processor with Triple Core Mali-450 GPU and 2GB DDR3 (32-bit / 912Mhz) of RAM. Kali Linux can run from either an external microSD card, or an eMMC module.

By default, the Kali Linux ODROID-C2 image contains the [**kali-linux-default** metapackage](https://www.kali.org/docs/general-use/metapackages/) similar to most other platforms. If you wish to install extra tools please refer to our [metapackages page](https://www.kali.org/docs/general-use/metapackages/).

[Kali on ODROID-C2 - Build-Script Instructions](broken-reference)

Kali does not provide pre-built images for download, but you can still generate one by cloning the [Kali-ARM Build-Scripts](https://gitlab.com/kalilinux/build-scripts/kali-arm) repository on GitLab, and follow the _README.md_ file’s instructions. The script to use is `odroid-c2.sh`.

Once the build script finishes running, you will have an “img.xz” file in the `images` directory where you ran the script from. At that point, the instructions are the same as if you had downloaded a pre-built image.

The easiest way to generate these images is **from within a pre-existing Kali Linux environment**.

[Kali on ODROID-C2 - User Instructions](broken-reference)

To install Kali on your ODROID-C2, follow these instructions:

1. Get a fast microSD card with at least 16GB capacity. Class 10 cards are highly recommended.
2. Use the [**dd**](https://packages.debian.org/testing/dd) utility to image this file to your microSD card (same process as [making a Kali USB](https://www.kali.org/docs/usb/live-usb-install-with-windows/).

In our example, we assume the storage device is located at `/dev/sdb`. Do _not_ simply copy these value, **change this to the correct drive path**.

This process will wipe out your microSD card. If you choose the wrong storage device, you may wipe out your computers hard disk.

```
$ xzcat images/kali-linux-2022.4-odroid-c2-arm64.img.xz | sudo dd of=/dev/sdb bs=4M status=progres
```

This process can take a while, depending on your PC, your microSD card speed, and the size of the Kali Linux image.

Once the _dd_ operation is complete, boot up the ODROID-C2 with the microSD card plugged in.

The same image file can be used for either eMMC or microSD card.

You should be able to [log in to Kali](https://www.kali.org/docs/introduction/default-credentials/).

[Kali on the ODROID-C2 - Tips](broken-reference)

The bootloader on the ODROID-C2 is u-boot, and in order to make changes to the kernel command line, the file to edit is `/etc/default/u-boot` and the option is `U_BOOT_PARAMETERS`. If you make any modifications to this file, you will want to then run `u-boot-update`.

USB on the ODROID-C2 will autosuspend if there is nothing plugged in to a USB port at boot time, so one possible change you might want to add is `usbcore.autosuspend=-1` if you want to plug in a USB device **after** the ODROID-C2 has booted.

If both a microSD card and an eMMC are plugged in, the ODROID-C2 will attempt to boot from the microSD card first.
