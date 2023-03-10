# Installing Kali on Mac Hardware

IMPORTANT! Newer Mac hardware (e.g. T2/M1 chips) do not run Linux well, or at all. This is true for [Linux in general](https://github.com/Dunedan/mbp-2016-linux/), not just Kali Linux.\
The model & year of the device will determine how successful your experience will be.\


Installing Kali Linux (Single boot) on Apple Mac hardware (such as MacBook/MacBook Pro/MacBook Airs/iMacs/iMacs Pros/Mac Pro/Mac Minis), can be a straight forward, if the hardware is supported. Most of the time, there are a few issues that come up, so there is a bit of trial and error.

This guide will show you how to replace macOS/OS X with Kali Linux. However, if you wish to keep macOS/OS X, you will want to refer to our [dual-boot](broken-reference) guide instead.

In our example, we will be installing Kali Linux on a Mac Mini (Mid 2011) using macOS High Sierra (10.13). The same procedure has also been tested on a Mac Book Air (Early 2014) using macOS Catalina (10.15).

[Installation Prerequisites](broken-reference)

This guide will make the following assumptions:

* You have read our [single boot Kali Linux install guide](broken-reference), as this has the same Installation Prerequisites (System requirements, setup assumptions and install media).
* Currently running macOS/OS X 10.7 or higher _(later versions are more preferred)_ as this means the hardware is Intel (and not a PowerPC CPU).
* Depending on the Mac hardware model & year, you may find:
  * **Different results** when trying to boot by using either a CD/DVD **or** a USB drive.
    * You may be able to increase the chances of booting _(especially older hardware and non-EFI)_ from a **USB drive** by having **rEFInd** pre-installed.
  * When using the graphical installer, you may notice the tracepad does not function (but will after Kali Linux is installed).
  * In-built wireless may not work, as `firmware-b43-installer` is [not included in the default images](https://gitlab.com/kalilinux/packages/kali-meta/-/commit/bdd4daa7be16e5114e21ade252638211e7d54813).

We will be wiping any existing data on the hard disk, so please backup any important information on the device to an external media.

[Kali Linux Installation Procedure](broken-reference)

1. To start your installation, make sure you **insert your Kali Linux installation medium** and **power on the device**. Immediately press and hold the [**Option (or Alt) ⌥** key until you see the boot menu](https://support.apple.com/en-us/HT201255) (rEFInd if installed, else the default macOS/OS X). You may or may not have a **Recovery HD** depending on your macOS/OS X setup.

[![](https://www.kali.org/docs/installation/hard-disk-install-on-mac/boot-mac.png)](https://www.kali.org/docs/installation/hard-disk-install-on-mac/boot-mac.png)

***

2. When the boot menu appears, if everything works as expected, you should see **two** volumes:

* **EFI Boot** - **Newer hardware** which support **UEFI**. It is common for **GUID Partition Table (GPT)** partitions to be used.
* **Windows** - “Non-EFI” boot. This use on **older hardware** which uses **BIOS**. You often see **Master Boot Record (MBR)** partition tables here.

If you only see **one volume** (EFI Boot), then the installation media **is not supported** for this device. This could be because the age of the firmware on the device.\
You may wish to install **rEFInd**, as it is a boot manager, and try again.

Even though Kali Linux is [based on Debian](https://www.kali.org/docs/policy/kali-linux-relationship-with-debian/), macOS/OS X always detects non-EFI boot media as Windows. We suggest that you select the **EFI Boot** volume to continue. However, if the installation hangs at this point, power cycle and select Windows (Being Kali Linux non-EFI/BIOS). The success depends on the Mac hardware’s model & year.

[![](https://www.kali.org/docs/installation/hard-disk-install-on-mac/boot-mac-usb-efi.png)](https://www.kali.org/docs/installation/hard-disk-install-on-mac/boot-mac-usb-efi.png)

[Kali Linux Installation Procedure](broken-reference)

1. The installation procedure from this point onwards is the same as our [Kali Linux Hard Disk install](broken-reference) guide.
2. After that is complete, all that is left is to reboot, take out the installation media, and enjoy Kali Linux.

[Troubleshooting macOS/OS X](broken-reference)

If you have issues installing Kali Linux on macOS/OS X, there are a few options you can try:

* Install the latest version of macOS/OS X ([App store](https://support.apple.com/en-gb/HT201541), [Recovery](https://support.apple.com/en-gb/HT204904) or [USB](https://support.apple.com/en-gb/HT201372)) and applying any updates as this may upgrade the firmware.
* Install **rEFInd** boot manager to replace the default boot manager.
* If you’re using a DVD, **refresh rEFInd** once the drive has stop spinning by pressing `ESC`.
* Switch from **EFI** to **BIOS boot** when trying to boot Kali Linux.
* Switch from **GPT** drive to **Hybrid MRB** drive _(using the Live image may help)_.

[Post Installation](broken-reference)

Now that you’ve completed installing Kali Linux, it’s time to customize your system.

The [General Use section](https://www.kali.org/docs/general-use/) has more information and you can also find tips on how to get the most out of Kali Linux in our [User Forums](https://forums.kali.org/).
