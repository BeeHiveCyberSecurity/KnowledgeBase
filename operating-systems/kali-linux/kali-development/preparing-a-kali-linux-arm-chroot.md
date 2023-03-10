# Preparing a Kali Linux ARM chroot

Although you can [download pre-rolled Kali ARM images](https://www.kali.org/get-kali/) from our download area, there may be applications which will require building your own custom bootstrapped Kali rootfs for ARM.

The following procedure shows an example of building a fairly generic Kali **armhf** rootfs. If you wish to build for **armel**, use that value rather than “armhf” when you export the **architecture** environment variable.

You’ll need to have root privileges to do this procedure, or the ability to escalate your privileges with the command “sudo su”.

[Some Notes on This Procedure](broken-reference)

The intention in this article is more to provide a high-level overview of how the build scripts work than an actual manual procedure (although it’s completely possible to walk through this example at the command line). The style mimics that used in the build scripts used to create the pre-rolled images. Specifically, you’ll see a construct in several places that looks like:

```
:~$ cat <<EOF > kali-$architecture/etc/apt/sources.list
deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware
EOF
```

This simply amounts to creating a new file, `~/arm-stuff/rootfs/kali-armhf/etc/apt/sources.list`, with the contents:

```
deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware
```

[Real-World Custom Kali Linux Builds for ARM Devices](broken-reference)

Before we walk through our example, it’s probably good to see how a custom ARM build would actually be accomplished. Typically, to do a local build of an image for, e.g., Raspberry Pi, the process would be something like the following. As an initial one-time set-up, clone [the ARM build scripts repository on GitHub](https://gitlab.com/kalilinux/build-scripts/kali-arm) and install the build prerequisites:

```
:~$ cd ~/
:~$ git clone https://gitlab.com/kalilinux/build-scripts/kali-arm.git
:~$ dpkg --add-architecture i386
:~$ sudo apt update
:~$ sudo apt install -y debootstrap qemu-user-static device-tree-compiler lzma lzop u-boot-tools libncurses5:i386 pixz
```

To do an ARM build, you must enable cross-compilation for your current shell session:

```
:~$ export ARCH=arm
:~$ mkdir -p ~/arm-stuff/kernel/toolchains/
:~$ cd ~/arm-stuff/kernel/toolchains/
:~$ git clone git://gitlab.com/kalilinux/packages/gcc-arm-eabi-linaro-4-6-2.git
:~$ export CROSS_COMPILE=~/arm-stuff/kernel/toolchains/gcc-arm-eabi-linaro-4.6.2/bin/arm-eabi-
```

Then simply invoke the build script for the specific platform. So, for a Raspberry Pi build of Kali Linux 2016.2, execute the commands:

```
:~$ cd ~/
:~$ kali-arm-build-scripts/rpi.sh 2016.2
```

The ARM build scripts are all completely self-contained, aside from the initial one-time installation of the build prerequisites. The first time you run one of the ARM build scripts, it is _extremely important_ that you inspect the output for any errors such as missing tools, etc., correct them, and then re-run the script until you get a clean build. Only at that point can you go ahead to make any customizations you want to the basic build script to create the specific “recipe” you’re after.

It’s possible to speed up your builds by caching the packages you download using [**apt-cacher-ng**](https://packages.debian.org/testing/apt-cacher-ng), as described in [the previous article](<../../../.gitbook/assets/arm cross compilation environment>). Note that this can break some of the standard build scripts unless you uncomment certain lines before building - they’re noted in the scripts themselves. If you’re using **apt-cacher-ng**, make sure you _check your scripts_ for any necessary changes.

For reliable and predictable results, build your Kali Linix ARM chroot **from within a pre-existing and** [**up-to-date**](https://www.kali.org/docs/general-use/updating-kali/) **Kali Linux environment**. This guide assumes that you have already [set up your ARM cross-compilation environment](<../../../.gitbook/assets/arm cross compilation environment>).

[An Annotated Example of a Generic ARM Build of Kali Linux](broken-reference)

The build described here is both minimal and generic. A small number of basic packages are included, and the fuller configuration needed for a real-world platform is omitted for the sake of clarity. Use this example as a reference for understanding what’s going on in the official ARM build scripts and as a high-level guide for writing your own build scripts. It can be successfully followed as a stand-alone tutorial from the command line, but the image produced is not likely to run on any particular device. Use [the pre-rolled build scripts](https://gitlab.com/kalilinux/build-scripts/kali-arm), either as-is or with your own customizations, to produce working images for concrete hardware.

[Install Required Tools and Dependencies](broken-reference)

This is a general set-up task, and should only ever need to be done once:

```
:~$ sudo apt install -y debootstrap qemu-user-static
```

[Enable Cross-Compilation](broken-reference)

In order to enable the Linaro cross-compilation, you will need to set these environment variable at the beginning of every session:

```
:~$ export ARCH=arm
:~$ export CROSS_COMPILE=~/arm-stuff/kernel/toolchains/gcc-arm-eabi-linaro-4.6.2/bin/arm-eabi-
```

[Define Architecture and Custom Packages](broken-reference)

This is where you define some environment variables for your required ARM architecture (armel vs armhf) and list the [packages](https://pkg.kali.org/) to be installed in your image. These will be used throughout this article, so make sure to modify them to your needs:

```
:~$ export packages="xfce4 kali-menu wpasupplicant kali-defaults initramfs-tools u-boot-tools nmap openssh-server"
:~$ export architecture="armhf"
```

[Build the Kali rootfs](broken-reference)[**Set Up the Base rootfs**](broken-reference)

As our starting point, we’ll create a standard directory structure and use **debootstrap** to install a base ARM rootfs from the Kali Linux repositories. We then copy over **qemu-arm-static**, an ARM emulator, from our host machine into the rootfs in order to initiate the 2nd stage chroot:

```
:~$ mkdir -p ~/arm-stuff/kernel # should have already been created when setting up x-compilation
:~$ mkdir -p ~/arm-stuff/rootfs
:~$ cd ~/arm-stuff/rootfs/
:~$
:~$ debootstrap --foreign --arch $architecture kali-rolling kali-$architecture http://http.kali.org/kali
:~$ cp /usr/bin/qemu-arm-static kali-$architecture/usr/bin/
```

[**2nd Stage chroot**](broken-reference)

First, we’ll chroot into our newly-created base rootfs, use **debootstrap** a second time to construct our second-stage rootfs, and configure base image settings such as repositories (in `/etc/apt/sources.list`), host name (in `/etc/hostname`), default network interfaces and behavior (in `/etc/network/interfaces` and `/etc/resolv.conf`), etc. Change these to suit your requirements:

```
:~$ cd ~/arm-stuff/rootfs/
:~$ LANG=C chroot kali-$architecture /debootstrap/debootstrap --second-stage
:~$
cat <<EOF > kali-$architecture/etc/apt/sources.list
deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware
EOF
:~$
:~$ echo "kali" > kali-$architecture/etc/hostname
:~$
:~$ cat <<EOF > kali-$architecture/etc/network/interfaces
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet dhcp
EOF
:~$
:~$ cat <<EOF > kali-$architecture/etc/resolv.conf
nameserver 8.8.8.8
EOF
```

Now, we’re ready to assemble our third-stage chroot.

[**3rd Stage chroot**](broken-reference)

This is where your specific customizations come in. Your **$packages** list is installed, as are keymaps, a default kali user password of “kali” is set, and other configuration changes and fixes are applied:

```
:~$ export MALLOC_CHECK_=0 # workaround for LP: #520465
:~$ export LC_ALL=C
:~$ export DEBIAN_FRONTEND=noninteractive
:~$
:~$ mount -t proc proc kali-$architecture/proc
:~$ mount -o bind /dev/ kali-$architecture/dev/
:~$ mount -o bind /dev/pts kali-$architecture/dev/pts
:~$
:~$ cat <<EOF > kali-$architecture/debconf.set
console-common console-data/keymap/policy select Select keymap from full list
console-common console-data/keymap/full select en-latin1-nodeadkeys
EOF
```

Here, we’ll create the script to do the third-stage chroot

```
:~$ cat <<EOF > kali-$architecture/third-stage
#!/bin/sh
dpkg-divert --add --local --divert /usr/sbin/invoke-rc.d.chroot --rename /usr/sbin/invoke-rc.d
cp /bin/true /usr/sbin/invoke-rc.d

apt-get update
apt-get install -y locales-all
#locale-gen en_US.UTF-8

debconf-set-selections /debconf.set
rm -f /debconf.set
apt-get update
apt-get install -y locales-all
apt-get install -y git-core binutils ca-certificates initramfs-tools u-boot-tools
apt-get install -y locales console-common less vim git
echo "kali:kali" | chpasswd
sed -i -e 's/KERNEL\!=\"eth\*|/KERNEL\!=\"/' /lib/udev/rules.d/75-persistent-net-generator.rules
rm -f /etc/udev/rules.d/70-persistent-net.rules
apt-get install -y --force-yes ${packages}

rm -f /usr/sbin/invoke-rc.d
dpkg-divert --remove --rename /usr/sbin/invoke-rc.d

rm -f /third-stage
EOF
```

Now, we’ll run it from within our second-stage chroot:

```
:~$ chmod +x kali-$architecture/third-stage
:~$ LANG=C chroot kali-$architecture /third-stage
```

[Manual Configuration Within the chroot](broken-reference)

If you need to make any further modifications in your rootfs environment, you can do so by manually chrooting into it with the following command and making any needed changes:

```
:~$ LANG=C chroot kali-$architecture
```

Once you’ve completed your modifications, leave the chroot’ed rootfs with the command

```
:~$ exit
```

[Cleanup](broken-reference)

Lastly, we create and run a cleanup script in our chroot to free up space used by cached files and run any other cleanup jobs we may require, and unmount the directories we were using in our rootfs:

```
:~$ cat <<EOF > kali-$architecture/cleanup
#!/bin/sh
rm -rf /root/.bash_history
apt-get update
apt-get clean
rm -f cleanup
EOF
:~$
:~$ chmod +x kali-$architecture/cleanup
:~$ LANG=C chroot kali-$architecture /cleanup
:~$
:~$ umount kali-$architecture/proc
:~$ umount kali-$architecture/dev/pts
:~$ umount kali-$architecture/dev/
:~$
:~$ cd ../
```

Congratulations! Your custom Kali ARM rootfs is located in the `~/arm-stuff/rootfs/kali-$architecture` directory. You can now tar up this directory or convert it to an image file for further work.
