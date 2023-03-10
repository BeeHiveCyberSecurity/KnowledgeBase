# Dual Booting Kali with Linux

Installing Kali Linux alongside another Linux installation can be quite useful. However, you need to exercise caution during the setup process. First, make sure that you’ve backed up any important data on your Linux installation. Since you’ll be modifying your hard drive, you’ll want to store this backup on external media. Once you’ve completed the backup, we recommend you peruse our [Kali Linux Hard Disk install guide](broken-reference), which explains the normal procedure for a basic Kali Linux install.

In our example, we will be installing Kali Linux alongside an installation of Ubuntu (Server 18.04), which is currently taking up 100% of the disk space in our computer. We will start by resizing our current Linux partition to occupy less space and then proceed to install Kali Linux in the newly-created empty partition.

[Installation Prerequisites](broken-reference)

This guide will make the following assumptions:

* You have read our [single boot Kali Linux install guide](broken-reference), as this has the same Installation Prerequisites (System requirements & setup assumptions).
* When [downloading Kali Linux](https://www.kali.org/docs/introduction/download-official-kali-linux-images/), [pick the **live** image](https://www.kali.org/docs/introduction/what-image-to-download/#which-image-to-choose), rather than the installer option.
* A single disk to install to _(rather than a dedicated disk per operating system)_.

***

We need to use a different image from the [single boot Kali Linux install guide](broken-reference), as we need the **live** image. This is because we need to edit the disk structure without mounting any partitions (otherwise they would be in-use). After we have finished altering the disk layout, we can still install Kali Linux using the live image, but there will be a few differences such as:

* Changing or removing the [desktop environment](https://www.kali.org/docs/general-use/switching-desktop-environments/).
* Installing or removing any [metapackages](https://www.kali.org/docs/general-use/metapackages/).

Both of these can be addressed post installation, as it saves swapping to the installer image (as you will need either multiple CD/DVD/USBs or to re-image half way though).

This installation has the potential to go wrong very easily as it involves editing existing partitions. Be aware of what partitions you are modifying and where you are installing Kali Linux to.\
Having a backup of your Linux files available is a good idea in the event something goes wrong.

[Resize Linux Procedure](broken-reference)

Before we can install Kali Linux, there needs to be room on the hard disk. By **booting into a live Kali Linux session** with your chosen installation medium, we can resize the partition to our desired size, as the disk will not be in use because Kali Linux will all be in memory.

1. To start resizing, make sure you **insert your Kali Linux installation medium** and **power on the device**. If needed, press any keyboard shortcuts for a “boot order menu” (depends on each manufacture) or boot into BIOS/UEFI and change the boot order to point to the installation medium first.
2. When the boot menu/options appears, you should see at least one new option. Depending on the manufacture, hardware, how the system is configured and install medium, you may see more options _(e.g. Can you boot into non-UEFI?)_.

You may need to try a few different options in order to find success.

3. You should be greeted with the Kali Linux **boot screen**. Select **Live**, and you should be booted into the Kali Linux default desktop.

[![](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/boot-live.png)](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/boot-live.png)

***

4. Now launch [**GParted**](https://packages.debian.org/testing/gparted), which we’ll use to shrink the existing Linux partition to give us enough room to install Kali Linux in the free space.

[![](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/gparted-1.png)](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/gparted-1.png)

***

5. Once GParted has opened, **select your Linux partition** (`/dev/sda1`) & **resize it** leaving enough space (we recommend at least 20 GB) for the Kali Linux installation.

Depending on your setup, the disk structure may be different to include:

* A swap partition
* Separate partitions for certain directories (e.g. `/home`, `/var` and `/tmp`)

You often just want to select the largest partition (commonly the data/home directory)

If you are moving past into any non-white in the partition then you are editing a section that is in use.\
Only remove from the area of the partition that is not in use.

If you wish to organize the partition to group all the Linux partitions together, placing the free space at the end, you may do so.

[![](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/gparted-2-linux.png)](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/gparted-2-linux.png)

***

6. Once you have resized your Linux partition, ensure you “**Apply All Operations**” on the hard disk. Exit gparted and **reboot**.

[![](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/gparted-3-linux.png)](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/gparted-3-linux.png)

[Kali Linux Installation Procedure](broken-reference)

1. The installation procedure from this point onwards is similar to a [Kali Linux Hard Disk install](broken-reference), until the point of the partitioning. At this point, you need to select “**Guided - use the largest continuous free space**” _(rather than “Guided - the entire disk”)_ which got created earlier with **gparted**.

[![](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/setup-partition-1-continuous.png)](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/setup-partition-1-continuous.png)

***

2. You can carry on following the [single boot Kali Linux install guide](broken-reference), expect you will not have the option to select [desktop environment](https://www.kali.org/docs/general-use/switching-desktop-environments/) or [metapackages](https://www.kali.org/docs/general-use/metapackages/) as you are using the live image. Once the installation is done, **reboot**.

You should be greeted with a **GRUB boot menu**, which will allow you to boot either into Kali Linux or the other Linux operating system.

[![](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/boot-linux.png)](https://www.kali.org/docs/installation/dual-boot-kali-with-linux/boot-linux.png)

[Post Installation](broken-reference)

Now that you’ve completed installing Kali Linux, it’s time to customize your system.

The [General Use section](https://www.kali.org/docs/general-use/) has more information and you can also find tips on how to get the most out of Kali Linux in our [User Forums](https://forums.kali.org/).
