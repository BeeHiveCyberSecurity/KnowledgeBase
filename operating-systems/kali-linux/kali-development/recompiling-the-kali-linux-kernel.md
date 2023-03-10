# Recompiling the Kali Linux Kernel

The customizability of Kali Linux extends all the way down into the Linux kernel.

Depending on your requirements, you might want to add drivers, patches, or kernel features that are not included in the stock Kali Linux kernel. The following guide will describe how the Kali Linux kernel can be quickly modified and recompiled for your needs. Note that global wireless injection patches are already present by default in the Kali Linux kernel.

[Install Build Dependencies](broken-reference)

Start by installing all the build dependencies for recompiling the kernel:

```
:~$ sudo apt install -y build-essential libncurses5-dev fakeroot xz-utils
```

[Download the Kali Linux Kernel Source Code](broken-reference)

The remainder of this section focuses on the 4.9 version of the Linux kernel, but the examples can, of course, be adapted to the particular version of the kernel that you want. We assume that the linux-source-4.9 binary package has been installed. Note that we install a binary package containing the upstream sources, we do not retrieve the Kali source package named linux:

```
:~$ sudo apt install -y linux-source-4.9
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  bc libreadline7
Suggested packages:
  libncurses-dev | ncurses-dev libqt4-dev
The following NEW packages will be installed:
  bc libreadline7 linux-source-4.9
0 upgraded, 3 newly installed, 0 to remove and 0 not upgraded.
Need to get 95.4 MB of archives.
After this operation, 95.8 MB of additional disk space will be used.
[...]
:~$ ls /usr/src
linux-config-4.9  linux-patch-4.9-rt.patch.xz  linux-source-4.9.tar.xz
```

Notice that the package contains _/usr/src/linux-source-4.9.tar.xz_, a compressed archive of the kernel sources. You must extract these files in a new directory (not directly under /usr/src/, since there is no need for special permissions to compile a Linux kernel). Instead, _\~/kernel/_ is more appropriate:

```
:~$ mkdir -p ~/kernel/
:~$ cd ~/kernel/
:~/kernel$ tar -xaf /usr/src/linux-source-4.9.tar.xz
```

[Configure Your Kernel](broken-reference)

When recompiling a more recent version of the kernel (possibly with an additional patch), the configuration will most likely be kept as close as possible to that proposed by Kali Linux. In this case, and rather than reconfiguring everything from scratch, it is sufficient to copy the _/boot/config-version_ file (the version is that of the kernel currently used, which can be found with the **uname -r** command) into a _.config_ file in the directory containing the kernel sources:

```
:~/kernel$ cp /boot/config-4.9.0-kali1-amd64 ~/kernel/linux-source-4.9/.config
```

If you need to make changes or if you decide to reconfigure everything from scratch, you must take the time to configure your kernel. This can be done by calling the **make menuconfig** command:

```
:~/kernel$ make menuconfig
```

The details of using **menuconfig** to set up a kernel build are beyond the scope of this guide. There is a [detailed tutorial on configuring a kernel build](https://www.linux.org/threads/the-linux-kernel-configuring-the-kernel-part-1.8745/) on Linux.org.

[Build the Kernel](broken-reference)

Once the kernel configuration is ready, a simple **make deb-pkg** will generate up to 5 Debian packages: _linux-image-**version**_ that contains the kernel image and the associated modules, _linux-headers-**version**_, which contains the header files required to build external modules, _linux-firmware-image-**version**_, which contains the firmware files needed by some drivers (this package might be missing when you build from the kernel sources provided by Debian or Kali), _linux-image-**version**-dbg_, which contains the debugging symbols for the kernel image and its modules, and _linux-libc-dev_, which contains headers relevant to some user-space libraries like GNU glibc. The Linux kernel image is a big build, expect it to take a while to complete:

```
:~/kernel$ make clean
:~/kernel$ make deb-pkg LOCALVERSION=-custom KDEB_PKGVERSION=$(make kernelversion)-1
[...]
:~/kernel$ ls ../*.deb
../linux-headers-4.9.0-kali1-custom_4.9.2-1_amd64.deb
../linux-image-4.9.0-kali1-custom_4.9.2-1_amd64.deb
../linux-image-4.9.0-kali1-custom-dbg_4.9.2-1_amd64.deb
../linux-libc-dev_4.9.2-1_amd64.deb
```

[Install the Modified Kernel](broken-reference)

When the build has successfully completed, you can go ahead and install the new custom kernel and reboot your system. Please note that the specific kernel version numbers will vary - in our example, done on a Kali 2016.2 system, it was 4.9.2. Depending on the current kernel version you’re building, you will need to adjust your commands accordingly:

```
:~/kernel$ sudo dpkg -i ../linux-image-4.9.0-kali1-custom_4.9.2-1_amd64.deb
:~/kernel$ reboot
```

Once your system has rebooted, your new kernel should be running. If things go wrong and your kernel fails to boot successfully, you can still use the Grub menu to boot from the original stock Kali kernel and fix your issues.
