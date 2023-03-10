# NanoPC-T3

The [NanoPC-T3](http://wiki.friendlyarm.com/wiki/index.php/NanoPC-T3) has an Samsung S5P6818, Octa Core Cortex™-A53 (ARMv8 64-bit) processor and either 1GB or 2GB DDR3 RAM. The NanoPC-T3 has an 8GB eMMC, which is too small for a default Kali installation, so we run from an external microSD card.

By default, the Kali Linux NanoPC-T3 image contains the [**kali-linux-default** metapackage](https://www.kali.org/docs/general-use/metapackages/) similar to most other platforms. If you wish to install extra tools please refer to our [metapackages page](https://www.kali.org/docs/general-use/metapackages/).

[Kali on NanoPC-T3 microSD card - User Instructions](broken-reference)

If you’re unfamiliar with the details of [downloading and validating a Kali Linux image](https://www.kali.org/docs/introduction/download-official-kali-linux-images/), or for [using that image to create a bootable device](https://www.kali.org/docs/usb/live-usb-install-with-windows/), it’s strongly recommended that you refer to the more detailed procedures described in the specific articles on those subjects.

To install a pre-built image of the standard build of Kali Linux on your NanoPC-T3, follow these instructions:

1. Get a fast microSD card with at least 16GB capacity. Class 10 cards are highly recommended.
2. Download _and validate_ the `Kali NanoPC-T3` image from the [downloads](https://www.kali.org/get-kali/) area. The process for validating an image is described in more detail on [Downloading Kali Linux](https://www.kali.org/docs/introduction/download-official-kali-linux-images/).
3. Use the [**dd**](https://packages.debian.org/testing/dd) utility to image this file to your microSD card (same process as [making a Kali USB](https://www.kali.org/docs/usb/live-usb-install-with-windows/).

In our example, we assume the storage device is located at `/dev/sdb`. Do _not_ simply copy these value, **change this to the correct drive path**.

This process will wipe out your microSD card. If you choose the wrong storage device, you may wipe out your computers hard disk.

```
$ xzcat kali-linux-2022.4-nanopc-t-arm64.img.xz | sudo dd of=/dev/sdb bs=4M status=progres
```

This process can take a while, depending on your PC, your microSD card’s speed, and the size of the Kali Linux image.

Once the _dd_ operation is complete, boot up the NanoPC-T3 with the microSD card plugged in.

You should be able to [log in to Kali](https://www.kali.org/docs/introduction/default-credentials/).

[Kali on the NanoPC-T3 - Tips](broken-reference)

The NanoPC-T3 will attempt to boot from the microSD card first if one is plugged in.

The wireless chipset is an Ampak AP6212, which is a rebranded Cypress (formerly Broadcom) Wireless card, so enterprising users may be able to get [nexmon](https://github.com/seemoo-lab/nexmon) working, if the work was put in.

If you want to change boot arguments/the kernel command line, you will need to install the package `libubootenv-tool` then create a file `env.conf` with the boot arguments you want to use. The default is `console=ttySAC0,115200n8 root=/dev/mmcblk0p2 rootfstype=ext3 rootwait rw consoleblank=0 net.ifnames=0\nbootdelay 1` and then write it to the sdcard with `fw_setenv /dev/mmcblk0 -s env.conf`

[Kali on NanoPC-T3 - Image Customization](broken-reference)

If you want to customize the Kali NanoPC-T3 image, including changes to the [packages](https://www.kali.org/docs/general-use/metapackages/) being installed, changing the [desktop environment](https://www.kali.org/docs/general-use/switching-desktop-environments/), increasing or decreasing the image file size or generally being adventurous, check out the [Kali-ARM Build-Scripts](https://gitlab.com/kalilinux/build-scripts/kali-arm) repository on GitLab, and follow the _README.md_ file’s instructions. The script to use is `nanopc-t.sh`.
