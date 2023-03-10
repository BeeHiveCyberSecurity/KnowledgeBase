# Custom Raspberry Pi Image

The following document describes our own method of creating a **custom Kali Linux Raspberry Pi ARM image** and is targeted at developers. If you would like to install a pre-made Kali image, check out our [Install Kali on Raspberry Pi](https://www.kali.org/docs/arm/raspberry-pi/) article.

You’ll need to have root privileges to do this procedure, or the ability to escalate your privileges with the command “sudo su”.

[01. Create a Kali rootfs](broken-reference)

Build a [Kali rootfs](broken-reference) as described in our Kali documentation, using an **armel** architecture. By the end of this process, you should have a populated rootfs directory in **\~/arm-stuff/rootfs/kali-armel**.

[02. Create the Image File](broken-reference)

Next, we create the physical image file, which will hold our Raspberry Pi rootfs and boot images:

```
:~$ sudo apt install -y kpartx xz-utils sharutils
:~$ mkdir -p ~/arm-stuff/images/
:~$ cd ~/arm-stuff/images/
:~$ dd if=/dev/zero of=kali-custom-rpi.img conv=fsync bs=4M count=7000
```

[03. Partition and Mount the Image File](broken-reference)

```
:~$ parted kali-custom-rpi.img --script -- mklabel msdos
:~$ parted kali-custom-rpi.img --script -- mkpart primary fat32 0 64
:~$ parted kali-custom-rpi.img --script -- mkpart primary ext4 64 -1
```

```
:~$ loopdevice=`losetup -f --show kali-custom-rpi.img`
:~$ device=`kpartx -va $loopdevice | sed -E 's/.*(loop[0-9])p.*/\1/g' | head -1`
:~$ device="/dev/mapper/${device}"
:~$ bootp=${device}p1
:~$ rootp=${device}p2
:~$
:~$ mkfs.vfat $bootp
:~$ mkfs.ext4 $rootp
:~$ mkdir -p root
:~$ mkdir -p boot
:~$ mount $rootp root
:~$ mount $bootp boot
```

[04. Copy and Modify the Kali rootfs](broken-reference)

```
:~$ rsync -HPavz /root/arm-stuff/rootfs/kali-armel/ root
:~$ echo nameserver 8.8.8.8 > root/etc/resolv.conf
```

[05. Compile the Raspberry Pi Kernel and Modules](broken-reference)

If you’re not using ARM hardware as the development environment, you will need to set up an [ARM cross-compilation environment](<../../../.gitbook/assets/arm cross compilation environment>) to build an ARM kernel and modules. Once that’s done, proceed with the following instructions:

```
:~$ mkdir -p ~/arm-stuff/kernel/
:~$ cd ~/arm-stuff/kernel/
:~$ git clone https://github.com/raspberrypi/tools.git
:~$ git clone https://github.com/raspberrypi/linux.git raspberrypi
:~$ cd raspberrypi/
:~$ touch .scmversion
:~$ export ARCH=arm
:~$ export CROSS_COMPILE=~/arm-stuff/kernel/toolchains/arm-eabi-linaro-4.6.2/bin/arm-eabi-
:~$ make bcmrpi_cutdown_defconfig

:~$ # configure your kernel !
:~$ make menuconfig
:~$ make -j$(cat /proc/cpuinfo|grep processor | wc -l)
:~$ make modules_install INSTALL_MOD_PATH=~/arm-stuff/images/root
:~$ cd ../tools/mkimage/
:~$ python imagetool-uncompressed.py ../../raspberrypi/arch/arm/boot/Image
```

```
:~$ cd ~/arm-stuff/images/
:~$ git clone git://github.com/raspberrypi/firmware.git rpi-firmware
:~$ cp -rf rpi-firmware/boot/* boot/
:~$ rm -rf rpi-firmware
:~$
:~$ cp ~/arm-stuff/kernel/tools/mkimage/kernel.img boot/
:~$ echo "dwc_otg.lpm_enable=0 console=ttyAMA0,115200 kgdboc=ttyAMA0,115200 console=tty1 root=/dev/mmcblk0p2 rootfstype=ext4 rootwait" > boot/cmdline.txt
```

```
:~$ umount $rootp
:~$ umount $bootp
:~$ kpartx -dv $loopdevice
:~$ losetup -d $loopdevice
```

Use the [**dd**](https://packages.debian.org/testing/dd) command to image this file to your SD card. In our example, we assume the storage device is located at `/dev/sdb`. **Change this as needed**:

```
:~$ dd if=kali-linux-rpi.img of=/dev/sdb conv=fsync bs=4M
```

Once the dd operation is complete, unmount and eject the SD card and boot your Pi into Kali Linux
