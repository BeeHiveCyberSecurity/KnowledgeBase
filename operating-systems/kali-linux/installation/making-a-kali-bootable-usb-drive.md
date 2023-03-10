# Making a Kali Bootable USB Drive

[What You’ll Need](broken-reference)

1. A _verified_ copy of the appropriate ISO image of the latest Kali build image for the system you’ll be running it on: see the details on [downloading official Kali Linux images](https://www.kali.org/docs/introduction/download-official-kali-linux-images/).
2. If you’re running under Linux or macOS/OS X, you can use the `dd` command, which is pre-installed, or use [Etcher](https://www.balena.io/etcher/). If you’re running under Windows, there is not one tool that is considered the overall best for imaging. We recommend [Etcher](https://www.balena.io/etcher/) _(installer or portable)_ as it is simpler to use, however [Rufus](https://rufus.ie/) is another popular option with its advanced options. If one does not work for you, consider the other.
3. A USB thumb drive, 4GB or larger. (Systems with a direct SD card slot can use an SD card with similar capacity. The procedure is identical.)

[Kali Linux USB Install Procedure](broken-reference)

The specifics of this procedure will vary depending on whether you’re doing it on a [Windows](broken-reference), [Linux](broken-reference), or [macOS/OS X](broken-reference) system.

[**Creating a Bootable Kali USB Drive on Linux (DD)**](broken-reference)

Creating a bootable Kali Linux USB drive in a Linux environment is easy. Once you’ve downloaded and verified your Kali ISO file, you can use the `dd` command to copy it over to your USB drive using the following procedure. Note that you’ll need to be running as root, or to execute the `dd` command with sudo. The following example assumes a Linux Mint 17.1 desktop - depending on the distro you’re using, a few specifics may vary slightly, but the general idea should be very similar. If you would prefer to use Etcher, then follow the same directions as a Windows user. Note that the USB drive will have a path similar to /dev/sdb.

WARNING: Although the process of imaging Kali Linux onto a USB drive is very easy, you can just as easily overwrite a disk drive you didn’t intend to with dd if you do not understand what you are doing, or if you specify an incorrect output path. Double-check what you’re doing before you do it, it’ll be too late afterwards. Consider yourself warned.

1. First, you’ll need to identify the device path to use to write the image to your USB drive. _**Without**_ the USB drive inserted into a port, execute the command `sudo fdisk -l` at a command prompt in a terminal window (if you don’t use elevated privileges with fdisk, you won’t get any output). You’ll get output that will look something (_not exactly_) like this, showing a single drive - “/dev/sda” - containing three partitions (/dev/sda1, /dev/sda2, and /dev/sda5):

[![](https://www.kali.org/docs/installation/create-bootable-media/Parallels-DesktopScreenSnapz007.png)](https://www.kali.org/docs/installation/create-bootable-media/Parallels-DesktopScreenSnapz007.png)

2\. Now, plug your USB drive into an available USB port on your system, and run the same command, “sudo fdisk -l” a second time. Now, the output will look something (again, _not exactly_) like this, showing an additional device which wasn’t there previously, in this example “/dev/sdb”, a 16GB USB drive:

[![](https://www.kali.org/docs/installation/create-bootable-media/FinderScreenSnapz002.png)](https://www.kali.org/docs/installation/create-bootable-media/FinderScreenSnapz002.png)

3\. Proceed to (carefully!) image the Kali ISO file on the USB device. The example command below assumes that the ISO image you’re writing is named “kali-linux-2022.4-installer-amd64.iso” and is in your current working directory. The blocksize parameter can be increased, and while it may speed up the operation of the dd command, it can occasionally produce unbootable USB drives, depending on your system and a lot of different factors. The recommended value, “bs=4M”, is conservative and reliable. Additionally, the parameter “conv=fsync” makes sure that the data is physically written to the USB drives before the commands returns:

```
:~$ dd if=kali-linux-2022.4-installer-amd64.iso of=/dev/sdb conv=fsync bs=4M
```

Imaging the USB drive can take a good amount of time, over ten minutes or more is not unusual, as the sample output below shows. Be patient!

The `dd` command provides no feedback until it’s completed, but if your drive has an access indicator, you’ll probably see it flickering from time to time. The time to `dd` the image across will depend on the speed of the system used, USB drive itself, and USB port it’s inserted into. Once `dd` has finished imaging the drive, it will output something that looks like this:

```
893+1 records in
893+1 records out
3748147200 bytes (3.7 GB, 3.5 GiB) copied, 998.442 s, 3.8 MB/s
```

That’s it, really!

[**Creating a Bootable Kali USB Drive on macOS/OS X (DD)**](broken-reference)

macOS/OS X is based on UNIX, so creating a bootable Kali Linux USB drive in an macOS/OS X environment is similar to doing it on Linux. Once you’ve downloaded and verified your chosen Kali ISO file, you use `dd` to copy it over to your USB drive. If you would prefer to use Etcher, then follow the same directions as a Windows user. Note that the USB drive will have a path similar to /dev/disk2.

WARNING: Although the process of imaging Kali on a USB drive is very easy, you can just as easily overwrite a disk drive you didn’t intend to with dd if you do not understand what you are doing, or if you specify an incorrect output path. Double-check what you’re doing before you do it, it’ll be too late afterwards. Consider yourself warned.

1. _**Without**_ the USB drive plugged into the system, open a Terminal window, and type the command `diskutil list` at the command prompt.
2. You will get a list of the device paths (looking like **/dev/disk0**, **/dev/disk1**, etc.) of the disks mounted on your system, along with information on the partitions on each of the disks.

[![](https://www.kali.org/docs/installation/create-bootable-media/TerminalScreenSnapz010.png)](https://www.kali.org/docs/installation/create-bootable-media/TerminalScreenSnapz010.png)

3\. Plug in your USB device to your Apple computer’s USB port and run the command `diskutil list` a second time. Your USB drive’s path will most likely be the last one. In any case, it will be one which wasn’t present before. In this example, you can see that there is now a **/dev/disk6** which wasn’t previously present.

[![](https://www.kali.org/docs/installation/create-bootable-media/TerminalScreenSnapz011.png)](https://www.kali.org/docs/installation/create-bootable-media/TerminalScreenSnapz011.png)

4\. Unmount the drive (assuming, for this example, the USB drive is **/dev/disk6** - _do **not** simply copy this, verify the correct path on your own system!_):

```
$ diskutil unmountDisk /dev/disk6
```

5. Proceed to (carefully!) image the Kali ISO file on the USB device. The following command assumes that your USB drive is on the path /dev/disk6, and you’re in the same directory with your Kali Linux ISO, which is named “kali-linux-2022.4-installer-amd64.iso”. We will replace /dev/disk6 with /dev/rdisk6 to improve the write speeds:

```
$ sudo dd if=kali-linux-2022.4-installer-amd64.iso of=/dev/rdisk6 bs=4M status=progress
```

There is a chance you may receive an error when running the above command, that you will receive the following error:

```
dd: invalid number: '4M'
```

If this is the case, please change the `4M` to be `4m`. Additionally, increasing the blocksize (bs) will speed up the write progress, but will also increase the chances of creating a bad USB drive. Using the given value on macOS/OS X has produced reliable images consistently. Another potential error will be that `status=progress` does not work on your version of macOS. If this is the case, remove this section and instead use `CTRL+T` to measure status.

Imaging the USB drive can take a good amount of time, over half an hour is not unusual, as the sample output below shows. Be patient!

The dd command provides no feedback until it’s completed, but if your drive has an access indicator, you’ll probably see it flickering from time to time. The time to `dd` the image across will depend on the speed of the system used, USB drive itself, and USB port it’s inserted into. Once dd has finished imaging the drive, it will output something that looks like this:

```
893+1 records in
893+1 records out
3748147200 bytes transferred in 915.043994 secs (4096139 bytes/sec)
```

And that’s it!

***

[**Creating a Bootable Kali USB Drive on Windows (Etcher)**](broken-reference)

1. Plug your USB drive into an available USB port on your Windows PC, note which drive designator (e.g. “`G:\`”) it uses once it mounts, and launch **Etcher**.
2. Click **Flash from file**, and locate the Kali Linux ISO file to be imaged with.
3. Click **Select target** and choose the USB drive you want to make bootable.
4. Click the **Flash!** button once ready.

_Note: You may get a UAC prompt asking for administrator privileges that you will need to accept._

[![](https://www.kali.org/docs/installation/create-bootable-media/Etcher1.png)](https://www.kali.org/docs/installation/create-bootable-media/Etcher1.png)

5\. Once Etcher alerts you that the image has been flashed, you can safely remove the USB drive and proceed to boot into Kali with it.

_At the time of writing, Etcher will use MBR. This is to allow for the most hardware compatibility._

[**Creating a Bootable Kali USB Drive on Linux and macOS/OS X (Etcher)**](broken-reference)

Alternatively, [Etcher](https://www.balena.io/etcher/) can be used.

1. Download and run Etcher.
2. Choose the Kali Linux ISO file to be imaged with “select image” and verify that the USB drive to be overwritten is the correct one. Click the “Flash!” button once ready.

[![](https://www.kali.org/docs/installation/create-bootable-media/kali-usb-install-windows.png)](https://www.kali.org/docs/installation/create-bootable-media/kali-usb-install-windows.png)

3\. Once Etcher alerts you that the image has been flashed, you can safely remove the USB drive.

You can now boot into a Kali Installer environment using the USB device.

To boot from an alternate drive on an macOS/OS X system, bring up the boot menu by pressing the **Option** key immediately after powering on the device and select the drive you want to use.

For more information, see [Apple’s knowledge base](https://support.apple.com/kb/ht1310).

***

[**Creating a Bootable Kali USB Drive on Windows (Rufus)**](broken-reference)

1. Plug your USB drive into an available USB port on your Windows PC, note which drive designator (e.g. “`G:\`”) it uses once it mounts, and launch **Rufus**.
2. With **Device**, check the dropdown list of options for the USB drive (e.g. “`G:\`” and size).
3. **Boot selection** needs to point to point to the Kali Linux ISO file, which can be done by clicking the **SELECT** button
4. Depending on your configuration, you can set the **Partition scheme**, as well as **Target system**. If you are not sure, leave it as the default values.
5. Click the **START** button once ready.

[![](https://www.kali.org/docs/installation/create-bootable-media/Rufus1.png)](https://www.kali.org/docs/installation/create-bootable-media/Rufus1.png)

6\. You may get a prompt saying about **ISOHybird image**. Selecting ISO image, will allow you to edit the files from the Kali Linux ISO, but at the potential lose of hardware compatibility. As a result, we recommend selecting **DD Image**.

[![](https://www.kali.org/docs/installation/create-bootable-media/Rufus2.png)](https://www.kali.org/docs/installation/create-bootable-media/Rufus2.png)

_Note: If you select “DD Image” option, you can create another partition on the USB drive, allowing you to use the rest of the space. Start -> Run (Windows + R) -> `diskmgmt.msc` -> Locate the USB drive -> Right-click in “Unallocated” -> New Simple Volume -> Follow the rest of the wizard with next, next, next…_

[![](https://www.kali.org/docs/installation/create-bootable-media/Rufus3.png)](https://www.kali.org/docs/installation/create-bootable-media/Rufus3.png)

***

[**Booting A USB Drive In Windows**](broken-reference)

Depending on the system _(such as BIOS or UEFI)_, as well as the version of Windows, and how they are each configured, you may need to re-image the USB drive.

* **M**aster **B**oot **R**ecord (MBR) is often used on legacy systems that use BIOS as well as UEFI which has **C**ompatibility **S**upport **M**odule (CSM) enabled
* **G**UID **P**artition **T**able (GPT) is required where UEFI has CSM disabled, forcing to use the modern standard

After writing the image to the USB drive, reboot Windows with the USB inserted. Depending on the motherboard manufacture, will also depend on the next stage. Some motherboard’s support a “temporary” boot menu, allowing for a one off selection. Others you need to enter BIOS/UEFI to configure it to try and boot from USB first. Entering either location, also depends on the motherboard. You can look up on the manufactures website and read the manual, try and read the screen when booting _(however the text may be shown too quick or full logos used)_, or try common key combinations (such as `ESC`, `F1`, `F2`, `F3`, `F4`, `F8`, `F10`, `F11`, `F12` or `DEL`).
