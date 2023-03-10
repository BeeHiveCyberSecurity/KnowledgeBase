# Custom MK/SS808 Image

The following document describes our own method of creating a **custom Kali Linux MK/SS808 ARM image** and is targeted at developers. If you would like to install a pre-made Kali image, check out our [Install Kali on MK/SS808](https://www.kali.org/docs/arm/ss808-mk808/) article.

You’ll need to have root privileges to do this procedure, or the ability to escalate your privileges with the command “sudo su”.

[01. Create a Kali rootfs](broken-reference)

Build yourself a [Kali rootfs](broken-reference) as described in our Kali documentation, using an **armhf** architecture. By the end of this process, you should have a populated rootfs directory in `~/arm-stuff/rootfs/kali-armhf`.

[02. Create the Image File](broken-reference)

Next, we create the physical image file which will hold our MK/SS808 rootfs and boot images:

```
:~$ sudo apt install -y kpartx xz-utils sharutils
:~$ mkdir -p ~/arm-stuff/images/
:~$ cd ~/arm-stuff/images/
:~/arm-stuff/images$ dd if=/dev/zero of=kali-custom-ss808.img conv=fsync bs=4M count=7000
```

[03. Partition and Mount the Image File](broken-reference)

```
:~$ parted kali-custom-ss808.img --script -- mklabel msdos
:~$ parted kali-custom-ss808.img --script -- mkpart primary ext4 1 -1
```

```
:~$ loopdevice=`losetup -f --show kali-custom-ss808.img`
:~$ device=`kpartx -va $loopdevice| sed -E 's/.*(loop[0-9])p.*/\1/g' | head -1`
:~$ device="/dev/mapper/${device}"
:~$ rootp=${device}p1
:~$
:~$ mkfs.ext4 $rootp
:~$ mkdir -p root/
:~$ mount $rootp root
```

[04. Copy and Modify the Kali rootfs](broken-reference)

```
:~$ rsync -HPavz /root/arm-stuff/rootfs/kali-armhf-xfce4/ root
:~$ echo nameserver 8.8.8.8 > root/etc/resolv.conf
```

[05. Compile the rk3066 Kernel and Modules](broken-reference)

If you’re not using ARM hardware as the development environment, you will need to set up an [ARM cross-compilation environment](<../../../.gitbook/assets/arm cross compilation environment>) to build an ARM kernel and modules. Once that’s done, proceed with the following steps:

```
:~$ sudo apt install -y xz-utils
:~$ mkdir -p ~/arm-stuff/kernel/
:~$ cd ~/arm-stuff/kernel/
:~$
:~$ git clone git://github.com/aloksinha2001/picuntu-3.0.8-alok.git rk3066-kernel
:~$ cd rk3066-kernel/
:~$ sed -i "/vpu_service/d" arch/arm/plat-rk/Makefile
```

```
:~$ export ARCH=arm
:~$ export CROSS_COMPILE=~/arm-stuff/kernel/toolchains/arm-eabi-linaro-4.6.2/bin/arm-eabi-
:~$
:~$ # A basic configuration for the UG802 and MK802 III
:~$ # make rk30_hotdog_ti_defconfig

:~$ # A basic configuration for the MK808
:~$ make rk30_hotdog_defconfig

:~$ # configure your kernel !
:~$ make menuconfig

:~$ # Configure the kernel as per http://www.armtvtech.com/armtvtechforum/viewtopic.php?f=66&t;=835
:~$ mkdir -p ../initramfs/
:~$ wget http://208.88.127.99/initramfs.cpio -O ../initramfs/initramfs.cpio
:~$
:~$ mkdir -p ../patches/
:~$ wget http://patches.aircrack-ng.org/mac80211.compat08082009.wl_frag+ack_v1.patch -O ../patches/mac80211.patch
:~$ wget http://patches.aircrack-ng.org/channel-negative-one-maxim.patch- O ../patches/negative.patch
:~$ patch -p1 < ../patches/mac80211.patch
:~$ patch -p1 < ../patches/negative.patch
:~$
:~$ ./make_kernel_ruikemei.sh
```

```
:~$ make modules -j$(cat /proc/cpuinfo|grep processor | wc -l)
:~$ make modules_install INSTALL_MOD_PATH=~/arm-stuff/images/root
:~$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/dwmw2/linux-firmware.git firmware-git
:~$ mkdir -p ~/arm-stuff/images/root/lib/firmware
:~$ cp -rf firmware-git/* ~/arm-stuff/images/root/lib/firmware/
:~$ rm -rf firmware-git
```

```
:~$ umount $rootp
:~$ kpartx -dv $loopdevice
:~$ losetup -d $loopdevice
```

[07. dd the Image to a USB device](broken-reference)

Use the [**dd**](https://packages.debian.org/testing/dd) command to image this file to your SD card. In our example, we assume the storage device is located at `/dev/sdb`. **Change this as needed**:

```
:~$ dd if=kali-linux-ss808.img of=/dev/sdb conv=fsync bs=4M
```

Once the dd operation is complete, unmount and eject the SD card and boot your MK/SS808 into Kali Linux
