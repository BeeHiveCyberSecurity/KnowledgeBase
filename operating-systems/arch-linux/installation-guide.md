# Installation Guide

This document is a guide for installing Arch Linux using the live system booted from an installation medium made from an official installation image. The installation medium provides accessibility features which are described on the page Install Arch Linux with accessibility options. For alternative means of installation, see Category:Installation process.

Before installing, it would be advised to view the FAQ. For conventions used in this document, see Help:Reading. In particular, code examples may contain placeholders (formatted in _`italics`_) that must be replaced manually.

This guide is kept concise and you are advised to follow the instructions in the presented order per section. For more detailed instructions, see the respective ArchWiki articles or the various programs' man pages, both linked from this guide. For interactive help, the IRC channel and the [forums](https://bbs.archlinux.org/) are also available.

Arch Linux should run on any [x86\_64](https://en.wikipedia.org/wiki/X86-64)-compatible machine with a minimum of 512 MiB RAM, though more memory is needed to boot the live system for installation.[\[1\]](https://lists.archlinux.org/archives/list/arch-releng@lists.archlinux.org/message/D5HSGOFTPGYI6IZUEB3ZNAX4D3F3ID37/) A basic installation should take less than 2 GiB of disk space. As the installation process needs to retrieve packages from a remote repository, this guide assumes a working internet connection is available.

### Pre-installation

#### Acquire an installation image

Visit the [Download](https://archlinux.org/download/) page and, depending on how you want to boot, acquire the ISO file or a netboot image, and the respective GnuPG signature.

#### Verify signature

It is recommended to verify the image signature before use, especially when downloading from an _HTTP mirror_, where downloads are generally prone to be intercepted to [serve malicious images](https://www2.cs.arizona.edu/stork/packagemanagersecurity/attacks-on-package-managers.html).

On a system with GnuPG installed, do this by downloading the _ISO PGP signature_ ([under Checksums in the page Download](https://archlinux.org/download/#checksums)) to the ISO directory, and verifying it with:

```
$ gpg --keyserver-options auto-key-retrieve --verify archlinux-version-x86_64.iso.sig
```

Alternatively, from an existing Arch Linux installation run:

```
$ pacman-key -v archlinux-version-x86_64.iso.sig
```

**Note:**

* The signature itself could be manipulated if it is downloaded from a mirror site, instead of from [archlinux.org](https://archlinux.org/download/) as above. In this case, ensure that the public key, which is used to decode the signature, is signed by another, trustworthy key. The `gpg` command will output the fingerprint of the public key.
* Another method to verify the authenticity of the signature is to ensure that the public key's fingerprint is identical to the key fingerprint of the [Arch Linux developer](https://archlinux.org/people/developers/) who signed the ISO-file. See [Wikipedia:Public-key cryptography](https://en.wikipedia.org/wiki/Public-key\_cryptography) for more information on the public-key process to authenticate keys.

#### Prepare an installation medium

The installation image can be supplied to the target machine via a USB flash drive, an optical disc or a network with PXE: follow the appropriate article to prepare yourself an installation medium from the chosen image.

#### Boot the live environment

**Note:** Arch Linux installation images do not support Secure Boot. You will need to disable Secure Boot to boot the installation medium. If desired, Secure Boot can be set up after completing the installation.

1. Point the current boot device to the one which has the Arch Linux installation medium. Typically it is achieved by pressing a key during the [POST](https://en.wikipedia.org/wiki/Power-on\_self\_test) phase, as indicated on the splash screen. Refer to your motherboard's manual for details.
2. When the installation medium's boot loader menu appears, select _Arch Linux install medium_ and press `Enter` to enter the installation environment.
3. You will be logged in on the first [virtual console](https://en.wikipedia.org/wiki/Virtual\_console) as the root user, and presented with a Zsh shell prompt.

To switch to a different console—for example, to view this guide with [Lynx](https://lynx.invisible-island.net/lynx\_help/Lynx\_users\_guide.html) alongside the installation—use the `Alt+`_`arrow`_ shortcut. To edit configuration files, [mcedit(1)](https://man.archlinux.org/man/mcedit.1), nano and vim are available. See [pkglist.x86\_64.txt](https://geo.mirror.pkgbuild.com/iso/latest/arch/pkglist.x86\_64.txt) for a list of the packages included in the installation medium.

#### Set the console keyboard layout

The default console keymap is [US](https://en.wikipedia.org/wiki/File:KB\_United\_States-NoAltGr.svg). Available layouts can be listed with:

```
# ls /usr/share/kbd/keymaps/**/*.map.gz
```

To set the keyboard layout, pass a corresponding file name to [loadkeys(1)](https://man.archlinux.org/man/loadkeys.1), omitting path and file extension. For example, to set a [German](https://en.wikipedia.org/wiki/File:KB\_Germany.svg) keyboard layout:

```
# loadkeys de-latin1
```

Console fonts are located in `/usr/share/kbd/consolefonts/` and can likewise be set with [setfont(8)](https://man.archlinux.org/man/setfont.8).

#### Verify the boot mode

To verify the boot mode, list the efivars directory:

```
# ls /sys/firmware/efi/efivars
```

If the command shows the directory without error, then the system is booted in UEFI mode. If the directory does not exist, the system may be booted in [BIOS](https://en.wikipedia.org/wiki/BIOS) (or [CSM](https://en.wikipedia.org/wiki/Compatibility\_Support\_Module)) mode. If the system did not boot in the mode you desired, refer to your motherboard's manual.

#### Connect to the internet

To set up a network connection in the live environment, go through the following steps:

*   Ensure your network interface is listed and enabled, for example with [ip-link(8)](https://man.archlinux.org/man/ip-link.8):

    ```
    # ip link
    ```
* For wireless and WWAN, make sure the card is not blocked with rfkill.
* Connect to the network:
  * Ethernet—plug in the cable.
  * Wi-Fi—authenticate to the wireless network using iwctl.
  * Mobile broadband modem—connect to the mobile network with the mmcli utility.
* Configure your network connection:
  * DHCP: dynamic IP address and DNS server assignment (provided by systemd-networkd and systemd-resolved) should work out of the box for Ethernet, WLAN, and WWAN network interfaces.
  * Static IP address: follow Network configuration#Static IP address.
*   The connection may be verified with ping:

    ```
    # ping archlinux.org
    ```

#### Update the system clock

In the live environment systemd-timesyncd is enabled by default and time will be synced automatically once a connection to the internet is established.

Use [timedatectl(1)](https://man.archlinux.org/man/timedatectl.1) to ensure the system clock is accurate:

```
# timedatectl status
```

#### Partition the disks

When recognized by the live system, disks are assigned to a block device such as `/dev/sda`, `/dev/nvme0n1` or `/dev/mmcblk0`. To identify these devices, use lsblk or _fdisk_.

```
# fdisk -l
```

Results ending in `rom`, `loop` or `airoot` may be ignored.

The following partitions are required for a chosen device:

* One partition for the [root directory](https://en.wikipedia.org/wiki/Root\_directory) `/`.
* For booting in UEFI mode: an EFI system partition.

If you want to create any stacked block devices for LVM, system encryption or RAID, do it now.

Use fdisk or parted to modify partition tables. For example:

```
# fdisk /dev/the_disk_to_be_partitioned
```

**Note:**

* If the disk does not show up, make sure the disk controller is not in RAID mode.
* If the disk from which you want to boot already has an EFI system partition, do not create another one, but use the existing partition instead.
* Swap space can be set on a swap file for file systems supporting it.

**Example layouts**

| Mount point  | Partition                       | [Partition type](https://en.wikipedia.org/wiki/GUID\_Partition\_Table#Partition\_type\_GUIDs) | Suggested size                                                                    |
| ------------ | ------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `/mnt/boot`1 | `/dev/`_`efi_system_partition`_ | EFI system partition                                                                          | At least 300 MiB. If multiple kernels will be installed, then no less than 1 GiB. |
| `[SWAP]`     | `/dev/`_`swap_partition`_       | Linux swap                                                                                    | More than 512 MiB                                                                 |
| `/mnt`       | `/dev/`_`root_partition`_       | Linux x86-64 root (/)                                                                         | Remainder of the device                                                           |

1. Other mount points, such as `/mnt/efi`, are possible, provided that the used boot loader is capable of loading the kernel and initramfs images from the root volume. See the warning in Arch boot process#Boot loader.

| Mount point | Partition                 | [Partition type](https://en.wikipedia.org/wiki/Partition\_type) | Suggested size          |
| ----------- | ------------------------- | --------------------------------------------------------------- | ----------------------- |
| `[SWAP]`    | `/dev/`_`swap_partition`_ | Linux swap                                                      | More than 512 MiB       |
| `/mnt`      | `/dev/`_`root_partition`_ | Linux                                                           | Remainder of the device |

See also Partitioning#Example layouts.

#### Format the partitions

Once the partitions have been created, each newly created partition must be formatted with an appropriate file system. See File systems#Create a file system for details.

For example, to create an Ext4 file system on `/dev/`_`root_partition`_, run:

```
# mkfs.ext4 /dev/root_partition
```

If you created a partition for swap, initialize it with [mkswap(8)](https://man.archlinux.org/man/mkswap.8):

```
# mkswap /dev/swap_partition
```

**Note:** For stacked block devices replace `/dev/`_`*_partition`_ with the appropriate block device path.

If you created an EFI system partition, format it to FAT32 using [mkfs.fat(8)](https://man.archlinux.org/man/mkfs.fat.8).

**Warning:** Only format the EFI system partition if you created it during the partitioning step. If there already was an EFI system partition on disk beforehand, reformatting it can destroy the boot loaders of other installed operating systems.

```
# mkfs.fat -F 32 /dev/efi_system_partition
```

#### Mount the file systems

Mount the root volume to `/mnt`. For example, if the root volume is `/dev/`_`root_partition`_:

```
# mount /dev/root_partition /mnt
```

Create any remaining mount points (such as `/mnt/boot`) and mount the volumes in their corresponding hierarchical order.

**Tip:** Run [mount(8)](https://man.archlinux.org/man/mount.8) with the `--mkdir` option to create the specified mount point. Alternatively, create it using [mkdir(1)](https://man.archlinux.org/man/mkdir.1) beforehand.

For UEFI systems, mount the EFI system partition:

```
# mount --mkdir /dev/efi_system_partition /mnt/boot
```

If you created a swap volume, enable it with [swapon(8)](https://man.archlinux.org/man/swapon.8):

```
# swapon /dev/swap_partition
```

[genfstab(8)](https://man.archlinux.org/man/genfstab.8) will later detect mounted file systems and swap space.

### Installation

#### Select the mirrors

Packages to be installed must be downloaded from mirror servers, which are defined in `/etc/pacman.d/mirrorlist`. On the live system, after connecting to the internet, reflector updates the mirror list by choosing 20 most recently synchronized HTTPS mirrors and sorting them by download rate.

The higher a mirror is placed in the list, the more priority it is given when downloading a package. You may want to inspect the file to see if it is satisfactory. If it is not, edit the file accordingly, and move the geographically closest mirrors to the top of the list, although other criteria should be taken into account.

This file will later be copied to the new system by _pacstrap_, so it is worth getting right.

#### Install essential packages

Use the [pacstrap(8)](https://man.archlinux.org/man/pacstrap.8) script to install the [base](https://archlinux.org/packages/?name=base) package, Linux kernel and firmware for common hardware:

```
# pacstrap -K /mnt base linux linux-firmware
```

**Tip:**

* You can substitute [linux](https://archlinux.org/packages/?name=linux) for a kernel package of your choice, or you could omit it entirely when installing in a [container](https://en.wikipedia.org/wiki/Container\_\(virtualization\)).
* You could omit the installation of the firmware package when installing in a virtual machine or container.

The [base](https://archlinux.org/packages/?name=base) package does not include all tools from the live installation, so installing other packages may be necessary for a fully functional base system. In particular, consider installing:

* userspace utilities for the management of file systems that will be used on the system,
* utilities for accessing RAID or LVM partitions,
* specific firmware for other devices not included in [linux-firmware](https://archlinux.org/packages/?name=linux-firmware) (e.g. [sof-firmware](https://archlinux.org/packages/?name=sof-firmware) for sound cards),
* software necessary for networking (e.g. a network manager or DHCP client),
* a text editor,
* packages for accessing documentation in man and info pages: [man-db](https://archlinux.org/packages/?name=man-db), [man-pages](https://archlinux.org/packages/?name=man-pages) and [texinfo](https://archlinux.org/packages/?name=texinfo).

To install other packages or package groups, append the names to the _pacstrap_ command above (space separated) or use pacman while [chrooted into the new system](broken-reference). For comparison, packages available in the live system can be found in [pkglist.x86\_64.txt](https://geo.mirror.pkgbuild.com/iso/latest/arch/pkglist.x86\_64.txt).

### Configure the system

#### Fstab

Generate an fstab file (use `-U` or `-L` to define by UUID or labels, respectively):

```
# genfstab -U /mnt >> /mnt/etc/fstab
```

Check the resulting `/mnt/etc/fstab` file, and edit it in case of errors.

#### Chroot

Change root into the new system:

```
# arch-chroot /mnt
```

#### Time zone

Set the time zone:

```
# ln -sf /usr/share/zoneinfo/Region/City /etc/localtime
```

Run [hwclock(8)](https://man.archlinux.org/man/hwclock.8) to generate `/etc/adjtime`:

```
# hwclock --systohc
```

This command assumes the hardware clock is set to [UTC](https://en.wikipedia.org/wiki/UTC). See System time#Time standard for details.

#### Localization

Edit `/etc/locale.gen` and uncomment `en_US.UTF-8 UTF-8` and other needed locales. Generate the locales by running:

```
# locale-gen
```

Create the [locale.conf(5)](https://man.archlinux.org/man/locale.conf.5) file, and set the LANG variable accordingly:

```
/etc/locale.conf
```

```
LANG=en_US.UTF-8
```

If you [set the console keyboard layout](broken-reference), make the changes persistent in [vconsole.conf(5)](https://man.archlinux.org/man/vconsole.conf.5):

```
/etc/vconsole.conf
```

```
KEYMAP=de-latin1
```

#### Network configuration

Create the hostname file:

```
/etc/hostname
```

```
myhostname
```

Complete the network configuration for the newly installed environment. That may include installing suitable network management software.

#### Initramfs

Creating a new _initramfs_ is usually not required, because mkinitcpio was run on installation of the kernel package with _pacstrap_.

For LVM, system encryption or RAID, modify [mkinitcpio.conf(5)](https://man.archlinux.org/man/mkinitcpio.conf.5) and recreate the initramfs image:

```
# mkinitcpio -P
```

#### Root password

Set the root password:

```
# passwd
```

#### Boot loader

Choose and install a Linux-capable boot loader. If you have an Intel or AMD CPU, enable microcode updates in addition.

### Reboot

Exit the chroot environment by typing `exit` or pressing `Ctrl+d`.

Optionally manually unmount all the partitions with `umount -R /mnt`: this allows noticing any "busy" partitions, and finding the cause with [fuser(1)](https://man.archlinux.org/man/fuser.1).

Finally, restart the machine by typing `reboot`: any partitions still mounted will be automatically unmounted by _systemd_. Remember to remove the installation medium and then login into the new system with the root account.

### Post-installation

See General recommendations for system management directions and post-installation tutorials (like creating unprivileged user accounts, setting up a graphical user interface, sound or a touchpad).

For a list of applications that may be of interest, see List of applications.
