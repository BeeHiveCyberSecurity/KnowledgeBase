# Building Custom Kali ISOs

One of the most powerful features of Kali Linux is the ability to create your own flavours of the distribution containing customized tools, desktop managers, and services. This workshop will show you how to create your own personalized Kali Linux ISO, customizing virtually every aspect using the live-build utility and making efficient use of the various [metapackages](https://www.kali.org/docs/general-use/metapackages/) available in Kali.

[The Awesomeness of Live Build](broken-reference)

**0x00 - Begin by updating the repos, installing the prerequisites,** and checking out a fresh version of `live-build-config` from the Kali Git repositories:

```
:~$ sudo apt update
:~$ sudo apt install -y git live-build cdebootstrap devscripts
:~$ git clone https://gitlab.com/kalilinux/build-scripts/live-build-config.git
:~$ cd live-build-config/
```

**0x01 - Overwrite the default Kali package list**, including only the packages you want. In the video, we simply edited the list and changed a few package names:

```
:~$ cat <<EOF > kali-config/variant-default/package-lists/kali.list.chroot
kali-root-login
kali-defaults
kali-menu
kali-debtags
kali-archive-keyring
debian-installer-launcher
alsa-tools
locales-all
dconf-tools
openssh-server
EOF
```

**0x02 - Add a customised syslinux boot entry** which includes a boot parameter for a custom preseed file:

```
:~$ cat <<EOF > kali-config/common/includes.binary/isolinux/install.cfg
label install
    menu label ^Install Automated
    linux /install/vmlinuz
    initrd /install/initrd.gz
    append vga=788 -- quiet file=/cdrom/install/preseed.cfg locale=en_US keymap=us hostname=kali domain=local.lan
EOF
```

**0x03 - Customise the ISO build**. In this example, we’ll have the SSH service start by default. To do this, we can use a chroot hook script which is placed in the “hooks” directory:

```
:~$ echo 'systemctl enable ssh' >>  kali-config/common/hooks/01-start-ssh.chroot
:~$ chmod +x kali-config/common/hooks/01-start-ssh.chroot
```

**0x04 - Next, we download a wallpaper** and overlay it. Notice how chroot overlaid files are placed in the _includes.chroot_ directory:

```
:~$ mkdir -p kali-config/common/includes.chroot/usr/share/wallpapers/kali/contents/images/
:~$ wget https://www.kali.org/dojo/blackhat-2015/wp-blue.png
:~$ mv wp-blue.png kali-config/common/includes.chroot/usr/share/wallpapers/kali/contents/images
```

**0x05 - Add a preseed file** that will run through a default Kali installation with no input (unattended). We can include a ready made preseed configuration and alter it as needed:

```
:~$ mkdir -p kali-config/common/debian-installer/
:~$ wget https://gitlab.com/kalilinux/recipes/kali-preseed-examples/-/raw/master/kali-linux-full-unattended.preseed -O kali-config/common/debian-installer/preseed.cfg
```

**0x06 - Let’s include a Nessus Debian package** into the _packages_ directory for inclusion into our final build. Since we used a 64-bit build, we’re including a 64-bit Nessus Debian package. [Download](https://www.tenable.com/products/nessus/select-your-operating-system) the Nessus .deb file and place it in the packages.chroot directory:

```
:~$ mkdir -p kali-config/common/packages.chroot/
:~$ mv Nessus-*amd64.deb kali-config/common/packages.chroot/
```

**0x07 - Now you can proceed to build your ISO**, this process may take a while depending on your hardware and internet speeds. Once completed, your ISO can be found in the live-build root directory:

```
:~$ ./build.sh -v
```

For more live-build implementations, refer to the following:

* [offensive-security.com/kali-linux/kali-linux-recipes/](https://www.offensive-security.com/kali-linux/kali-linux-recipes/)
* [gitlab.com/kalilinux/recipes/live-build-config-examples](https://gitlab.com/kalilinux/recipes/live-build-config-examples)
