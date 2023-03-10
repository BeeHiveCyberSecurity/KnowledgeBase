# Making a Kali Bootable USB Drive (Linux)

Our favourite way, and the fastest method, for getting up and running with Kali Linux is to run it “live” from a USB drive. This method has several advantages:

* It’s non-destructive - it makes no changes to the host system’s hard drive or installed OS, and to go back to normal operations, you simply remove the “Kali Live” USB drive and restart the system.
* It’s portable - you can carry Kali Linux in your pocket and have it running in minutes on an available system
* It’s customizable - you can [roll your own custom Kali Linux ISO image](https://www.kali.org/docs/development/live-build-a-custom-kali-iso/) and put it onto a USB drive using the same procedures
* It’s potentially persistent - with a bit of extra effort, you can configure your Kali Linux “live” USB drive to have [persistent storage](broken-reference), so the data you collect is saved across reboots

In order to do this, we first need to create a bootable USB drive which has been set up from an ISO image of Kali Linux.

[What You’ll Need](broken-reference)

1. A _verified_ copy of the appropriate ISO image of the latest Kali build image for the system you’ll be running it on: see the details on [downloading official Kali Linux images](https://www.kali.org/docs/introduction/download-official-kali-linux-images/).
2. If you’re running under Linux, you can use the `dd` command, which is pre-installed, or use [Etcher](https://www.balena.io/etcher/).
3. A USB thumb drive, 4GB or larger. (Systems with a direct SD card slot can use an SD card with similar capacity. The procedure is identical.)

[Kali Linux Live USB Install Procedure](broken-reference)

The specifics of this procedure will vary depending on whether you’re doing it on a [Windows](broken-reference), [Linux](broken-reference), or [macOS/OS X](broken-reference) system.

[**Creating a Bootable Kali USB Drive on Linux (DD)**](broken-reference)

Creating a bootable Kali Linux USB drive in a Linux environment is easy. Once you’ve downloaded and verified your Kali ISO file, you can use the `dd` command to copy it over to your USB drive using the following procedure. Note that you’ll need to be running as root, or to execute the `dd` command with sudo. The following example assumes a Linux Mint 17.1 desktop - depending on the distro you’re using, a few specifics may vary slightly, but the general idea should be very similar. If you would prefer to use Etcher, then follow the same directions as a Windows user. Note that the USB drive will have a path similar to /dev/sdb.

WARNING: Although the process of imaging Kali Linux onto a USB drive is very easy, you can just as easily overwrite a disk drive you didn’t intend to with dd if you do not understand what you are doing, or if you specify an incorrect output path. Double-check what you’re doing before you do it, it’ll be too late afterwards.

Consider yourself warned.

1. First, you’ll need to identify the device path to use to write the image to your USB drive. _**Without**_ the USB drive inserted into a port, execute the command `sudo fdisk -l` at a command prompt in a terminal window (if you don’t use elevated privileges with fdisk, you won’t get any output). You’ll get output that will look something (_not exactly_) like this, showing a single drive - “/dev/sda” - containing three partitions (/dev/sda1, /dev/sda2, and /dev/sda5):

[![](<../../../.gitbook/assets/Parallels DesktopScreenSnapz007.png>)](<../../../.gitbook/assets/Parallels DesktopScreenSnapz007.png>)

2\. Now, plug your USB drive into an available USB port on your system, and run the same command, “sudo fdisk -l” a second time. Now, the output will look something (again, _not exactly_) like this, showing an additional device which wasn’t there previously, in this example “/dev/sdb”, a 16GB USB drive:

[![](../../../.gitbook/assets/FinderScreenSnapz002.png)](../../../.gitbook/assets/FinderScreenSnapz002.png)

3\. Proceed to (carefully!) image the Kali ISO file on the USB device. The example command below assumes that the ISO image you’re writing is named “kali-linux-2022.4-live-amd64.iso” and is in your current working directory. The blocksize parameter can be increased, and while it may speed up the operation of the dd command, it can occasionally produce unbootable USB drives, depending on your system and a lot of different factors. The recommended value, “bs=4M”, is conservative and reliable. Additionally, the parameter “conv=fsync” makes sure that the data is physically written to the USB drives before the commands returns:

```
:~$ dd if=kali-linux-2022.4-live-amd64.iso of=/dev/sdb conv=fsync bs=4M
```

Imaging the USB drive can take a good amount of time, over ten minutes or more is not unusual, as the sample output below shows. Be patient!

The `dd` command provides no feedback until it’s completed, but if your drive has an access indicator, you’ll probably see it flickering from time to time. The time to `dd` the image across will depend on the speed of the system used, USB drive itself, and USB port it’s inserted into. Once `dd` has finished imaging the drive, it will output something that looks like this:

```
893+1 records in
893+1 records out
3748147200 bytes (3.7 GB, 3.5 GiB) copied, 998.442 s, 3.8 MB/s
```

That’s it, really!

***

[**Creating a Bootable Kali USB Drive on Linux (DD with status)**](broken-reference)

Alternatively there are a few other options available for imaging.

The first option is `dd` with a status indicator. This is only available on newer systems however. To do this, we simply add the `status` flag:

```
:~$ dd if=kali-linux-2022.4-live-amd64.iso of=/dev/sdb conv=fsync bs=4M status=progress
```

Another option is to use `pv`. We can also use the `size` flag here to get an approximate timer. Change the size depending on the image being used:

```
:~$ dd if=kali-linux-2022.4-live-amd64.iso | pv -s 2.8G | dd of=/dev/sdb conv=fsync bs=4M
```

[**Creating a Bootable Kali USB Drive on Linux (Etcher)**](broken-reference)

The third is [Etcher](https://www.balena.io/etcher/).

1. Download and run Etcher.
2. Choose the Kali Linux ISO file to be imaged with “select image” and verify that the USB drive to be overwritten is the correct one. Click the “Flash!” button once ready.

[![](<../../../.gitbook/assets/kali usb install windows (1).png>)](<../../../.gitbook/assets/kali usb install windows (1).png>)

3\. Once Etcher alerts you that the image has been flashed, you can safely remove the USB drive.

You can now boot into a Kali Live / Installer environment using the USB device.
