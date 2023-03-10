# BeagleBone Black

The [BeagleBone Black](http://beagleboard.org/BLACK) is a low-cost, community-supported ARM-based development platform aimed at developers and hobbyists. The BeagleBone Black runs a 1GHz Cortex-A8 CPU and includes hardware-based floating point and 3D acceleration; while much lower-powered than a desktop or laptop system, its affordability makes it an excellent option for a tiny Linux system.

The BeagleBone Black provides a microSD card slot for mass storage and if that device is bootable, will use it in preference to the board’s “burned-in” Angstrom or Debian operating system.

By default, the Kali Linux BeagleBone Black image contains the [**kali-linux-default** metapackage](https://www.kali.org/docs/general-use/metapackages/) similar to most other platforms. If you wish to install extra tools please refer to our [metapackages page](https://www.kali.org/docs/general-use/metapackages/).

[Kali on Beaglebone Black - Build-Script Instructions](broken-reference)

Kali does not provide pre-built images for download, but you can still generate one by cloning the [Kali-ARM Build-Scripts](https://gitlab.com/kalilinux/build-scripts/kali-arm) repository on GitLab, and follow the _README.md_ file’s instructions. The script to use is `beaglebone-black.sh`.

Once the build script finishes running, you will have an “img.xz” file in the `images` directory where you ran the script from. At that point, the instructions are the same as if you had downloaded a pre-built image.

The easiest way to generate these images is **from within a pre-existing Kali Linux environment**.

[Kali on Beaglebone Black - User Instructions](broken-reference)

To install Kali on your Beaglebone Black, follow these instructions:

1. Get a fast microSD card with at least 16GB capacity. Class 10 cards are highly recommended.
2. Use the [**dd**](https://packages.debian.org/testing/dd) utility to image this file to your microSD card (same process as [making a Kali USB](https://www.kali.org/docs/usb/live-usb-install-with-windows/).

In our example, we assume the storage device is located at `/dev/sdb`. Do _not_ simply copy these value, **change this to the correct drive path**.

This process will wipe out your microSD card. If you choose the wrong storage device, you may wipe out your computers hard disk.

```
$ xzcat images/kali-linux-2022.4-beaglebone-black-armhf.img.xz | sudo dd of=/dev/sdb bs=4M status=progres
```

This process can take a while, depending on your PC, your microSD card speed, and the size of the Kali Linux image.

Once the _dd_ operation is complete, boot up the Banana Pro with the microSD card plugged in.

You should be able to [log in to Kali](https://www.kali.org/docs/introduction/default-credentials/).
