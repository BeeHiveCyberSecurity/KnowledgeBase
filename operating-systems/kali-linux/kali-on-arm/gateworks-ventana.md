# Gateworks Ventana

The [Gateworks Ventana](https://www.gateworks.com/products/industrial-single-board-computers/imx6-single-board-computer-gateworks-ventana-family/) implementing a flash drive sized computer. Kali Linux fits on a microSD card for it.

_This image is for the “NXP (formerly Freescale) i.MX6” based boards._

By default, the Kali Linux Gateworks Ventana image contains the [**kali-linux-default** metapackage](https://www.kali.org/docs/general-use/metapackages/) similar to most other platforms. If you wish to install extra tools please refer to our [metapackages page](https://www.kali.org/docs/general-use/metapackages/).

[Kali on the Gateworks Ventana - User Instructions](broken-reference)

If you’re unfamiliar with the details of [downloading and validating a Kali Linux image](https://www.kali.org/docs/introduction/download-official-kali-linux-images/), or for [using that image to create a bootable device](https://www.kali.org/docs/usb/live-usb-install-with-windows/), it’s strongly recommended that you refer to the more detailed procedures described in the specific articles on those subjects.

To install a pre-built image of the standard build of Kali Linux on your Ventana, follow these instructions:

1. Get a fast microSD card with at least 16GB capacity. Class 10 cards are highly recommended.
2. Download _and validate_ the `Kali Ventana` image from the [downloads](https://www.kali.org/get-kali/) area. The process for validating an image is described in more detail on [Downloading Kali Linux](https://www.kali.org/docs/introduction/download-official-kali-linux-images/).
3. Use the [**dd**](https://packages.debian.org/testing/dd) utility to image this file to your microSD card. In our example, we use a microSD which is located at `/dev/sdb`. _**Change this as needed.**_

This process will wipe out your microSD card. If you choose the wrong storage device, you may wipe out your computers hard disk.

```
$ xzcat kali-linux-2022.4-gateworks-ventana-armhf.img.xz | sudo dd of=/dev/sdb bs=4M status=progress
```

This process can take a while, depending on your PC, your microSD card’s speed, and the size of the Kali Linux image.

Once the _dd_ operation is complete, boot up a computer with the Gateworks Ventana plugged in.

You should be able to [log in to Kali](https://www.kali.org/docs/introduction/default-credentials/).

[Kali on the Gateworks Ventana - Image Customization](broken-reference)

If you want to customize the Kali Gateworks Ventana image, including changes to the [packages](https://www.kali.org/docs/general-use/metapackages/) being installed, changing the [desktop environment](https://www.kali.org/docs/general-use/switching-desktop-environments/), increasing or decreasing the image file size or generally being adventurous, check out the [Kali-ARM Build-Scripts](https://gitlab.com/kalilinux/build-scripts/kali-arm) repository on GitLab, and follow the _README.md_ file’s instructions. The script to use is `gateworks-ventana.sh`.
