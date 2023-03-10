# Custom Chromebook Image

The following document describes our own method of creating a **custom Kali Linux Samsung Chromebook ARM image** and is targeted at developers. If you would like to install a pre-made Kali image, check out our [Install Kali on Samsung Chromebook](https://www.kali.org/docs/arm/chromebook-exynos/) article.

In this guide, we create an image with two boot partitions - one containing a kernel hard-coded to boot from the SD card and the other containing a kernel hard-coded to boot from USB. Depending on your USB storage media type, make sure to mark the relevant boot partition with higher priority after you dd the image to your USB device as instructed in the last stages of this guide.

You’ll need to have root privileges to do this procedure, or the ability to escalate your privileges with the command “sudo su”.

[**01. Create a Kali rootfs**](broken-reference)

Start by building a [Kali rootfs](broken-reference) as described in our Kali documentation, using an **armhf** architecture. By the end of this process, you should have a populated rootfs directory in `~/arm-stuff/rootfs/kali-armhf`.

[**02. Create the Image File**](broken-reference)

Next, we create the physical image file that will hold our Chromebook rootfs and boot images:

```
:~$ sudo apt install -y kpartx xz-utils gdisk uboot-mkimage u-boot-tools vboot-kernel-utils vboot-utils cgpt
:~$ mkdir -p ~/arm-stuff/images/
:~$ cd ~/arm-stuff/images/
:~$ dd if=/dev/zero of=kali-custom-chrome.img conv=fsync bs=4M count=7000
```

[**03. Partition and Mount the Image File**](broken-reference)

```
:~$ parted kali-custom-chrome.img --script -- mklabel msdos
:~$ parted kali-custom-chrome.img --script -- mktable gpt
:~$ gdisk kali-custom-chrome.img <<EOF
x
l
8192
m
n
1

+16M
7f00
n
2

+16M
7f00
n
3

w
y
EOF
```

```
:~$ loopdevice=`losetup -f --show kali-custom-chrome.img`
:~$ device=`kpartx -va $loopdevice| sed -E 's/.*(loop[0-9])p.*/\1/g' | head -1`
:~$ device="/dev/mapper/${device}"
:~$ bootp1=${device}p1
:~$ bootp2=${device}p2
:~$ rootp=${device}p3

:~$ mkfs.ext4 $rootp
:~$ mkdir -p root
:~$ mount $rootp root
```

[**04. Copy and Modify the Kali rootfs**](broken-reference)

Copy over the Kali rootfs you bootstrapped earlier using [**rsync**](https://packages.debian.org/testing/rsync) to the mounted image:

```
:~$ cd ~/arm-stuff/images/
:~$ rsync -HPavz ~/arm-stuff/rootfs/kali-armhf/ root
:~$
:~$ echo nameserver 8.8.8.8 > root/etc/resolv.conf
:~$
:~$ mkdir -p root/etc/X11/xorg.conf.d/
:~$ cat <<EOF > root/etc/X11/xorg.conf.d/50-touchpad.conf
Section "InputClass"
Identifier "touchpad"
MatchIsTouchpad "on"
Driver "synaptics"
Option "TapButton1" "1"
Option "TapButton2" "3"
Option "TapButton3" "2"
Option "FingerLow" "15"
Option "FingerHigh" "20"
Option "FingerPress" "256"
EndSection
EOF
```

[**05. Compile the Samsung Chromium Kernel and Modules**](broken-reference)

If you’re not using ARM hardware as the development environment, you will need to set up an [ARM cross-compilation environment](<../../../.gitbook/assets/arm cross compilation environment>) to build an ARM kernel and modules. Once that’s done, proceed with the following instructions.

Fetch the Chromium kernel sources and place them in our development tree structure:

```
:~$ mkdir -p ~/arm-stuff/kernel/
:~$ cd ~/arm-stuff/kernel/
:~$ git clone http://git.chromium.org/chromiumos/third_party/kernel.git -b chromeos-3.4 chromeos
:~$ cd chromeos/
```

```
:~$ cat <<EOF > kernel.its
/dts-v1/;

/ {
description = "Chrome OS kernel image with one or more FDT blobs";
#address-cells = ;
images {
{
description = "kernel";
data = /incbin/("arch/arm/boot/zImage");
type = "kernel_noload";
arch = "arm";
os = "linux";
compression = "none";
load = ;
entry = ;
};
{
description = "exynos5250-snow.dtb";
data = /incbin/("arch/arm/boot/exynos5250-snow.dtb");
type = "flat_dt";
arch = "arm";
compression = "none";
{
algo = "sha1";
};
};
};
configurations {
default = "";
{
kernel = "";
fdt = "";
};
};
};
EOF
```

Patch the kernel, in our case, with wireless injection patches:

```
:~$ mkdir -p ../patches/
:~$ wget http://patches.aircrack-ng.org/mac80211.compat08082009.wl_frag+ack_v1.patch -O ../patches/mac80211.patch
:~$ wget http://patches.aircrack-ng.org/channel-negative-one-maxim.patch -O ../patches/negative.patch
:~$ patch -p1 < ../patches/negative.patch
:~$ patch -p1 < ../patches/mac80211.patch
```

Configure, then cross-compile the Chromium kernel as shown below:

```
:~$ export ARCH=arm
:~$ export CROSS_COMPILE=~/arm-stuff/kernel/toolchains/arm-eabi-linaro-4.6.2/bin/arm-eabi-
:~$
:~$ ./chromeos/scripts/prepareconfig chromeos-exynos5

# Disable LSM
:~$ sed -i 's/CONFIG_SECURITY_CHROMIUMOS=y/# CONFIG_SECURITY_CHROMIUMOS is not set/g' .config

# If cross compiling, do this once:
:~$ sed -i 's/if defined(__linux__)/if defined(__linux__) ||defined(__KERNEL__) /g' include/drm/drm.h

:~$ make menuconfig
:~$ make -j$(cat /proc/cpuinfo|grep processor | wc -l)
:~$ make dtbs
:~$ cp ./scripts/dtc/dtc /usr/bin/
:~$ mkimage -f kernel.its kernel.itb
:~$ make modules_install INSTALL_MOD_PATH=~/arm-stuff/images/root/

# Copy over firmware. Ideally use the original firmware (/lib/firmware) from the Chromebook.
:~$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/dwmw2/linux-firmware.git
:~$ cp -rf linux-firmware/* ~/arm-stuff/images/root/lib/firmware/
:~$ rm -rf linux-firmware
```

```
:~$ echo "console=tty1 debug verbose root=/dev/mmcblk1p3 rootwait rw rootfstype=ext4" > /tmp/config-sd
:~$ echo "console=tty1 debug verbose root=/dev/sda3 rootwait rw rootfstype=ext4" > /tmp/config-usb
:~$
:~$ vbutil_kernel --pack /tmp/newkern-sd --keyblock /usr/share/vboot/devkeys/kernel.keyblock --version 1 --signprivate /usr/share/vboot/devkeys/:~$ kernel_data_key.vbprivk --config=/tmp/config-sd --vmlinuz kernel.itb --arch arm
:~$ vbutil_kernel --pack /tmp/newkern-usb --keyblock /usr/share/vboot/devkeys/kernel.keyblock --version 1 --signprivate /usr/share/vboot/devkeys/:~$ kernel_data_key.vbprivk --config=/tmp/config-usb --vmlinuz kernel.itb --arch arm
```

[**06. Prepare the Boot Partition**](broken-reference)

```
:~$ dd if=/tmp/newkern-sd of=$bootp1 conv=fsync # first boot partition for SD
:~$ dd if=/tmp/newkern-usb of=$bootp2 conv=fsync # second boot partition for USB
:~$
:~$ umount $rootp
:~$
:~$ kpartx -dv $loopdevice
:~$ losetup -d $loopdevice
```

[**07. dd the Image and Mark the USB Drive Bootable**](broken-reference)

```
:~$ dd if=kali-linux-chrome.img of=/dev/sdb conv=fsync bs=4M
:~$ cgpt repair /dev/sdb
```

This is the point where you need to mark either boot partition 1 or 2 to have higher priority. The number with the higher priority will boot first. The example below will give priority 10 to the first partition (-i) and will thus boot successfully from a SD card.

```
:~$ cgpt add -i 1 -S 1 -T 5 -P 10 -l KERN-A /dev/sdb
:~$ cgpt add -i 2 -S 1 -T 5 -P 5 -l KERN-B /dev/sdb
```

To see your partition list and order, use the command **cgpt show**:

```
:~$ cgpt show /dev/sdb
start size part contents
0 1 PMBR
1 1 Pri GPT header
2 32 Pri GPT table
8192 32768 1 Label: "KERN-A"
Type: ChromeOS kernel
UUID: 63AD6EC9-AD94-4B42-80E4-798BBE6BE46C
Attr: priority=10 tries=5 successful=1
40960 32768 2 Label: "KERN-B"
Type: ChromeOS kernel
UUID: 37CE46C9-0A7A-4994-80FC-9C0FFCB4FDC1
Attr: priority=5 tries=5 successful=1
73728 3832490 3 Label: "Linux filesystem"
Type: 0FC63DAF-8483-4772-8E79-3D69D8477DE4
UUID: E9E67EE1-C02E-481C-BA3F-18E721515DBB
125045391 32 Sec GPT table
125045423 1 Sec GPT header
:~$
```

Once this operation is complete, boot up your Samsung Chromebook with the SD/USB device plugged in. At the developer mode boot screen, hit CTRL+u to boot from from your USB storage device. Log in to Kali (root / toor) and startx.
