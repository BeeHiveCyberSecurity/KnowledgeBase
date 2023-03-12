# Installation

This guide explains some of the ways in which Ubuntu Linux can be installed to your desktop or laptop computer. It concentrates on installing Ubuntu alongside a pre-existing version Windows so that, each time you start the computer, you can choose which operating system you want to use. It is community created documentation, the work of many hands and minds convinced by their own experience that Linux is a superior operating system and deserves to be widely used. The official guide [Ubuntu 16.04 Installation Guide](https://help.ubuntu.com/16.04/installation-guide/index.html) covers a complete list of alternative installation methods for Ubuntu. At present (March 2018), however, it does not explain some of the very important preliminary steps if you want to install Ubuntu alongside Windows.

We will initially assume that your computer has an standard optical drive that can read and write DVD disks. Further along, we will explain how to work with USB drives if the system has no DVD drive.

### Hardware Requirements <a href="#hardware_requirements" id="hardware_requirements"></a>

Ubuntu has been designed keeping in mind the most common hardware, so it is highly likely that Ubuntu will work on your machine _**without any problem**_. Nonetheless, you should check if your hardware works with Ubuntu and meets the minimum system requirements. If you already have your computer, you can easily do so by making a LiveDVD or USB drive (as described below) and starting the computer with it in the appropriate drive. You may, however, have to change the boot order (as described below) to get your machine to start from the LiveDVD. If you are buying a new machine from a retail store, inquire of the salesperson and try it with the LiveDVD or USB drive while still in the returnable period. For a comprehensive review of all Ubuntu supported hardware follow this link: Supported Architectures:

For a list of **Ubuntu-certified** machines, follow this link: [Ubuntu-Certified Hardware](https://wiki.ubuntu.com/HardwareSupport):

However, the fact that a given machine is not listed does not mean that Ubuntu won't work on it.

For a list of the the minimal system requirements a machine needs in order to run the graphical version of Ubuntu, follow this link: [System Requirements](../../../.gitbook/assets/SystemRequirements):

* Relative to most modern machines, these requirements are **extremely modest**.

### Make a LiveDVD <a href="#make_a_livedvd" id="make_a_livedvd"></a>

The LiveDVD is a **fully functional Ubuntu environment**, and it allows you to get a taste of Ubuntu on your machine before installing it on your hard disk. You first need to download an .iso image from [https://www.ubuntu.com/download/desktop](https://www.ubuntu.com/download/desktop) and then burn it to a DVD (see BurningIsoHowto and [Installation/CDIntegrityCheck](../../../.gitbook/assets/CDIntegrityCheck)).

### Try to Boot from the LiveDVD <a href="#try_to_boot_from_the_livedvd" id="try_to_boot_from_the_livedvd"></a>

You can try putting the LiveDVD in the DVD drive and starting the computer. There is some rather small chance that the computer will boot from the LiveDVD. More likely, it will completely ignore the DVD and boot Windows as usual. If this happens, then the computer came with the hard disk ahead of the DVD in the boot order (also known as the boot sequence). The boot order in machines made after about 2012 is set in something called the UEFI (Uniform Extensible Firmware Interface). You must edit the UEFI to change the boot order.

### Changing the Boot Order in the UEFI Editor <a href="#changing_the_boot_order_in_the_uefi_editor" id="changing_the_boot_order_in_the_uefi_editor"></a>

Windows has a UEFI editor. It is accessed and works slightly differently in Windows 8.1 and Windows 10. To get to this editor in Windows 8.1, begin from Settings (the cogwheel) on the start page. From there go to "Update and Recovery" then "Recovery" then "Advanced startup" then "Restart now" then "Troubleshoot" then "Advanced options" and then "UEFI Firmware settings". Once you have reached this editor, use the right arrow key to move across to the "Boot" tab and then follow instructions on the screen to move the optical drive to the top of the boot order. It is also a good idea to enable booting from USB. On the Security tab it is possible to disable SecureBoot. It should not be necessary to do so, but if you have trouble getting the boot to start, come back and disable SecureBoot. (Do NOT be tempted to enable "Legacy mode". If you do, Windows won't work at all and Linux will work poorly.)

To get to the UEFI editor in Windows 10, navigate to Settings. (Click the Windows Start key in the lower left corner of the screen. Above it then appear some icons; the “cogwheel” which shows the word “Settings” when the cursor is over it is the one you want to click. Then:

* Select “Update & security”.
* Select “Recovery” from the left menu.
* Click “Restart Now” under “Advanced startup. ... “
* Click “Troubleshoot”.
* Click “Advanced options”.
* Select “UEFI Firmware Settings”.
* What you now see seems to depend on the make and model of the computer. Look around for “Boot sequence” or “Boot priority” and pick it.
* Another screen should come up; again it seems to depend on the make and model of your computer. Avoid anything suggestive of “Windows boot manager” and go for anything suggestive of the DVD reader.
* Click “Restart”.

Now when booted the computer should look for your DVD drive before it jumps into a Windows boot. If there is nothing in the drive, it will (at this stage) still boot Windows. (You may well wonder if the process is this complicated because someone wanted it to be as hard as legally possible to install other operating systems.)

### Preparing to Install Ubuntu alongside Windows <a href="#preparing_to_install_ubuntu_alongside_windows" id="preparing_to_install_ubuntu_alongside_windows"></a>

Installing Ubuntu Linux as the only operating system is much simpler than installing it alongside Windows so that you can choose when you turn on the computer which operating system to use. If Ubuntu is to be the only operating system, you are ready to install it. But if you are reading this you are probably going to want to preserve the Windows operating system that came with your computer, so we must deal with that more complicated case. The complexities are in dealing with Windows, not Ubuntu.

*   Prepare Windows to share the computer. There are three things to do.

    **(1) Back up Windows on a bootable USB drive.** There are instructions on the Microsoft web site. This is just a precautionary step, but it is a good idea whether or not you install Ubuntu. The chances of damaging Windows in the process of installing Ubuntu are very slight, but better safe than sorry.

    **(2) Disable Fast Startup.** Windows 8.1 and 10 and presumably future versions have a feature called Fast Startup. When it is enabled -- and it is enabled by default -- Windows shuts down in a hybrid state, somewhere between a full shutdown and a "sleep" state. The dual boot manager which Ubuntu will install (called grub) does not presently (2018) know how to start Windows from this hybrid state. You must therefore **disable Fast Startup** if you ever want to use Windows again after installing Ubuntu. Here is how to turn off Fast Startup in Windows 10:

    * Type "Control Panel" in the search box near the lower left corner of the Windows home screen.
    * Click “Control Panel”.
    * Click “Power Options”.
    * Click “Choose what the power buttons do.”
    * Click “Change settings that are currently unavailable.”
    * Scroll down to Shutdown settings and uncheck “Turn on fast startup”.
    * Click “Save changes.”

    Now when you shut down Windows you will get a complete shutdown, and the Linux boot manager will be able to start Windows if you tell it to do so.\
    Other versions of Windows may be different, but do not fail to turn of Fast Startup, or you will never boot Windows again.

    **(3). Either Shrink the Windows C: Drive to Make Room for Linux OR Turn off Windows Updating**

Now comes the most confusing part. Before we can install Linux we must shrink the Windows C drive to make room for Linux. There are two mutually exclusive ways to do this:

1. Use Windows Disk Management
   * or
2. Use GParted, a utility available within the Ubuntu installation process.

If the Windows method has been used, GParted may not be available during the Ubuntu installation.

Each method seems to have its problems. The Windows Disk Management utility is perfectly safe but is likely to be unable to shrink the C drive to less than about 60 percent of a terabyte hard disk. That is because some files have been placed far out in the disk space and the Windows utility is unable to move them. (Strangely, the Windows defragmenter detects 0 fragmentation and is unable to move those files.) Moreover, using this method is going to complicate both preparing Windows to receive Linux and the installation of Linux. GParted moves those trouble-making files, can give Linux much more of the disk, and is very easy. There are concerns, however, that if GParted has been used, then when Windows 10 updates, it may damage the Linux partition. One Kubuntu user reports that Windows updates have twice destroyed his Linux partition. ( Post #7 in this thread: [https://ubuntuforums.org/showthread.php?t=2385462](https://ubuntuforums.org/showthread.php?t=2385462)) Unlike earlier versions of Windows, in Windows 10 it is not possible to completely turn off all updates, though it is possible to reduce them, as explained below.

If the GParted route is chosen, it is probably a good idea to reduce Windows updates to the minimum Microsoft considers essential before installing Ubuntu. Exactly how to do that seems to be evolving in Windows 10. In early 2018, the following method seemed to work. In the “Search” window next to the Windows icon in the lower left corner of the screen type Run. A screen opens saying that Run, a desktop app, was the best match. Start it. In the screen that opens type “services.msc” A long list of “services” comes up. Down near the bottom is “Windows update service.” Click it and in the pane on the left you should be able to “disable” it. It is said, however, that updates that Microsoft considers “Priority,” will still come through. With most updates shut down, the probability of damage to the Linux partition by very occasional use of Windows does not seem to be high.

In choosing between the easy, powerful, but slightly risky GParted and the complicated, weak, but totally safe Disk Management, it should also be borne in mind that the Ubuntu “Files” program and Linux programs such as Writer or Calc (in the LibreOffice suite) can create directories (= folders) in the Windows partition and read and write data files there. Thus, space in the Windows partition is not totally lost to you when using Linux. The reverse is not true; Windows programs cannot read or write anything in the Linux partition. Linux programs, however, must reside in the Linux partition.

Thus, in the end, the choice between the two methods of making room for Linux depends on the expected use of the computer. If it is to be primarily a Windows machine, by all means use Windows Disk Management and give Ubuntu 50 gigabytes or so. If it is to be primarily a Linux machine with only seldom use of Windows, you may want to go with GParted, disable Windows updates, always back up thoroughly before booting Windows, and hope for the best.

**Partitioning with Windows Disk Management**

If you decide to go with Windows Disk Management, it is worthwhile to look at several good presentations with screen shots on this topic on the Internet. It may be a good idea to first run the Windows defragmenter; again, consult the Internet on this. We give here a summary of the partitioning process that you can easily print and keep at hand as you work.

Click the Windows “Start” icon in the lower left corner of the opening screen. Type “partition” in the search box. “Create and format hard disk partitions” should come up. Click it. A screen comes up showing existing partitions. Right click the partition labeled C. Then in the menu on the right click “Shrink volume.”

A screen appears showing:

Total size before shrink in MB\
Size of available shrink space in MB\
Enter amount of space to shrink in MB\
Total size after shrink in MB\


Use the up and down arrows to enter in the third box the amount to shrink. It must be less than the number in the second box, sometimes considerably less.\
Click the “Shrink” button.

### Standard Installation of Ubuntu 16.04 with a LiveDVD <a href="#standard_installation_of_ubuntu_16.04_with_a_livedvd" id="standard_installation_of_ubuntu_16.04_with_a_livedvd"></a>

Put the LiveDVD in the drive and close it. After some whirring, a screen comes up asking whether you want to try Ubuntu or install it. Click the install icon. Next comes a screen with one box asking whether we want to check the Internet for updates and download them as we install and another box asking whether to install third-party software. Normally, check both boxes and click continue.

Then comes the Installation type screen.

If you **have not** used Windows to shrink the C drive, the first option should say “Install Ubuntu alongside Windows 10.” Pick it; that will start the GParted program. With sliders you can adjust how much space each operating system gets. You should give Ubuntu a minimum of 50 gigabytes, but you can give it much more. When you have the proportion you want, click Continue and the installer will create the new partition. Skip the next paragraph of this text.

If you **have** used Windows to shrink the C drive, matters will be more complicated because in Windows you shrank the C drive but did not create a new partition. That we must now do. Check “Something else” and click “Continue”. In the next screen click “freespace” then click the + sign on the lower left. In the next screen labeled “Create Partition” select “Logical” and in the “Mount point” box use the drop down menu to select / . In the “Use as” box, use the drop-down menu to select “Ext4 Journaling file system.” Click OK. You should now be brought back to the “Installation type” screen. Click “Install now”.

Proceed to pick your time zone and your keyboard layout. After a bit more whirring of the DVD, Ubuntu is installed. Shut down, remove the DVD, start up and you should get the Linux start menu, pick Ubuntu, and your machine should boot Ubuntu Linux. You can also shut down and restart booting Windows just to be sure that it also works.

### Calming the Touchpad <a href="#calming_the_touchpad" id="calming_the_touchpad"></a>

If you are using a laptop with a touchpad you may find when you try LibreOffice Writer that the cursor dances around wildly as you type. With previous Ubuntu releases there was a touchpad option “Disable while typing” which was on by default. Strangely, the option is gone in 16.04. To calm the touchpad, go to “System Settings” then “Mouse and touchpad” and clear all of the boxes at the bottom of the screen, in particular, “Tap to click”. That should fix the problem. To click, you will have to tap the touchpad on the bar at the lower left, not just anywhere. There seems to be some third-party software called touchpad-indicator which has a “disable touchpad on typing” function.

### Getting Gedit and other programs <a href="#getting_gedit_and_other_programs" id="getting_gedit_and_other_programs"></a>

When Ubuntu starts up, it has the launcher on the left of the screen. Programs with icons in the launcher are easily started by clicking the icon. Initially the launcher has the Dash icon, the Files icon, the Firefox web browser, the components of LibreOffice, the System Settings cogwheel icon, Ubuntu software, Trash, and of course Amazon. There are, however, some other useful programs, such as the text editor Gedit, already installed but not in the launcher. To get Gedit into the launcher, click on the Dash, the top icon in the launcher, type “Gedit” and its icon appears on the right. If you like, you can drag it over into the launcher. You can do the same for Screenshot. You can then, if you like, download and install from the Ubuntu repository various useful programs. Some widely used ones are:

Gimp, the image processor that rivals Photoshop

Skype for telephoning over the Internet

CodeBlocks for C++ programming

Pdfshufffler – to split or combine pdf files; useful for documents too big for Writer all in one file.

gThumb image viewer

* **You are now ready to enjoy Ubuntu Linux!**

### Alternate Installations <a href="#alternate_installations" id="alternate_installations"></a>

You may not wish to use the standard LiveCD for one of the following reasons:

* Your computer does not meet the hardware requirements, or the required drivers are missing from the standard LiveCD. The LiveCD is designed to support most standard hardware, but this won't cover every possible configuration.
* _**Or**_, you may simply prefer to _**install a more customized version of Ubuntu**_ different from the standard install depending on your taste.

Ubuntu has you covered in this regard, and towards this end you can use an **Alternate Installation CD**. Refer to the Getting Ubuntu page for download locations. The Alternate CD allows more advanced installation options which are not available with the standard LiveCD.

### Installation without a CD <a href="#installation_without_a_cd" id="installation_without_a_cd"></a>

The new generations of laptops and netbooks are increasingly shipping without CD drives. To cater to this need, or if you do not wish to burn a CD to install Ubuntu, you are not left to trudge in the dark - **Ubuntu can be installed without using a CD or CD-ROM drive**!

* [Quick Install from USB](../../../.gitbook/assets/FromUSBStickQuick) - A quick guide to installing from a USB memory stick. Intended for less technically-inclined readers.
* [Install from USB](../../../.gitbook/assets/FromUSBStick) - Installing from a USB memory stick (full version).
* [USB stick + grub](../../../.gitbook/assets/FromCForUSBStick) - Similar to above but using grub.
* [Installation/iso2usb](../../../.gitbook/assets/iso2usb) - Overview: cloning and extraction, tools and a simple 'Do it yourself' extracting method.
* Smart Boot Manager - Installing from a PC which will not boot from a CD.
* [Install within Windows](../../../.gitbook/assets/FromWindows) - Yes, it is possible to install Ubuntu **from within Windows** without using floppies, a CD, or any other removable media! This uses _Wubi_, and installs Ubuntu as a large file that may be uninstalled like any other program in Windows.
* [Install with Floppies](../../../.gitbook/assets/WithFloppies) - Installing without a CD drive over a network.
* [Install From Hard Drive with Floppies](../../../.gitbook/assets/FromHardDriveWithFloppies) - Installing without a CD drive or network capabilities from a hard drive.
* [Install from Existing Linux](../../../.gitbook/assets/FromLinux) - Installing using a spare partition from an existing Linux system to house the Ubuntu CD image.
* [Virtual Machine](../../../.gitbook/assets/FromVM) - Installing using a physical disk to a Virtual Machine.
* [Portable installed system booting from UEFI & BIOS](<../../../.gitbook/assets/UEFI and BIOS>) - A system for a USB pendrive - a good alternative to a persistent live system.

Please refer also to the network installation guides below.

### Upgrading an installation <a href="#upgrading_an_installation" id="upgrading_an_installation"></a>

If you are upgrading from a previous version of Ubuntu to a new version, please refer to the Upgrade Notes for upgrading instructions.

### Server and network installations <a href="#server_and_network_installations" id="server_and_network_installations"></a>

Ubuntu can be installed over a network or the Internet.

* [Local Network](../../../.gitbook/assets/LocalNet) - Booting the installer from a local server, using DHCP, TFTP, and PXE.
* [Installation/Netboot](../../../.gitbook/assets/Netboot) - Another description of installing over the net, with no CD-ROM drive or a non-bootable SCSI CD-ROM drive.
* [Netboot Install From Internet](../../../.gitbook/assets/NetbootInstallFromInternet) - Booting using files saved to an existing partition and downloading the packages from the internet at installation time.
* [Network Console](../../../.gitbook/assets/NetworkConsole) - Booting from a CD (could be TFTP or similar too) and installing the system over SSH.
* [On NFS Drive](../../../.gitbook/assets/OnNFSDrive) - Installing on a NFS-server and using with diskless clients.
* [On NFS Drive with Local Boot](../../../.gitbook/assets/OnNFSDriveWithLocalBoot) - Installing on an NFS-server with a local /boot (e.g. Booting from CompactFlash for a silent media center PC).
* [Quick Install over SSH](<../../../.gitbook/assets/OverSSH Light>) - A quick guide for installing Hardy Ubuntu 12.04 on a dedicated server over ssh.
* [Over SSH](../../../.gitbook/assets/OverSSH) - Installing on a dedicated server over ssh (full version).
* [Install with Floppies](../../../.gitbook/assets/WithFloppies) - Installing without a CD drive over a network.

### Installing on external or RAID hard disks <a href="#installing_on_external_or_raid_hard_disks" id="installing_on_external_or_raid_hard_disks"></a>

Ubuntu can be installed on an external hard disk or RAID array.

* BootFromFirewireHardDisk - Booting Linux from a Firewire hard disk.
* BootFromUSB - Booting an Ubuntu system on a USB hard disk on computers which cannot boot from USB (using a boot CD).
* BootFromSD - Booting an Ubuntu system from a SD card on computers which cannot boot from SD
* [LiveUsbPendrivePersistent](https://wiki.ubuntu.com/LiveUsbPendrivePersistent) - Installing Ubuntu or Kubuntu on a USB pendrive with persistent mode.
* [Installation/LVMOnRaid](../../../.gitbook/assets/LVMOnRaid) - Installing onto a Software RAID Array, with all partitions on RAID and LVM (including root and boot).
* FakeRaidHowto - Installing onto a BIOS RAID array.
* How\_to\_dual-boot\_Ubuntu\_and\_XP\_after\_installing\_them\_separately\_on\_two\_HDs - If you really want to keep XP and Ubuntu on separate hard drives.
* Installation/SoftwareRAID - Install a Linux software RAID
* Installation/FromImageLoadedOnHardDrive - Installing via a CD image loaded onto a hard drive.

### LVM Installation Guides <a href="#lvm_installation_guides" id="lvm_installation_guides"></a>

* EncryptedFSOnLVMOnRAID
* EncryptedFilesystemLVMHowto
* FileServerOnLVMOnRAID1
* [Installation/LVMOnRaid](../../../.gitbook/assets/LVMOnRaid)
* Installation/RAID1+LVM
* SettingUpLVM-WithoutACleanInstall



### &#x20;<a href="#other_installation_guides" id="other_installation_guides"></a>

### &#x20;<a href="#see_also" id="see_also"></a>
