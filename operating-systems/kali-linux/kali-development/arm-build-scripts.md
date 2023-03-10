# ARM Build Scripts

These are the same build scripts that we use to generate the pre-generated official Kali Linux ARM images, found here: [https://www.kali.org/get-kali/](https://www.kali.org/get-kali/)

There are additional scripts included in the repository, supporting more devices, that we do not release images for, as well as archived scripts for historical purposes.

For more information, please see: [https://www.kali.org/docs/arm/](https://www.kali.org/docs/arm/)

***

[Building](broken-reference)

* These scripts are tested on Kali Linux arm64, x64 and x86 installations only _(We **recommend x64**)_
* Make sure you run the `./common.d/build_deps.sh` script before trying to build an image, as this installs all required dependencies
* You will need at **least 8GB of RAM or use a SWAP file**

An example workflow to build a [_Raspberry Pi 4_](https://www.kali.org/docs/arm/raspberry-pi-4/) _Kali Linux image_ would look like:

```
$ cd ~/
$ git clone https://gitlab.com/kalilinux/build-scripts/kali-arm
$ cd ~/kali-arm/
$ sudo ./common.d/build_deps.sh
$ sudo ./raspberry-pi.sh
```

* Depending on your system hardware & network connectivity, will depend on how long it will take to build _(4 core CPU, 8GB RAM, SSD inside a VM takes using a_ [_local repo_](https://www.kali.org/docs/community/setting-up-a-kali-linux-mirror/) _about 100 minutes per script)_
* On x64 or arm64 systems, after the script finishes running, you will have an image files located in `~/kali-arm/images/` called `kali-linux-2022.4-raspberry-pi-xfce-armhf.img.xz`
* On x86 systems, as they do not have enough RAM to compress the image, after the script finishes running, you will have an image file located in `~/kali-arm/images/` called `kali-linux-2022.4-raspberry-pi-xfce-armhf.img`
  * _Should you want to try and shrink the file to make it easier to distribute, you will need to use **your own preferred compression**_.

***

[Help](broken-reference)

On any build script, add `--help`. Example:

```
$ ./raspberry-pi.sh --help
 Usage commands:
# Architectures (arm64, armel, armhf)
./raspberry-pi.sh --arch arm64 or ./raspberry-pi.sh -a armhf

# Desktop manager (xfce, gnome, kde, i3, i3-gaps, lxde, mate, e17 or none)
./raspberry-pi.sh --desktop kde or ./raspberry-pi.sh --desktop=kde

# Minimal image - no desktop manager
./raspberry-pi.sh --minimal or ./raspberry-pi.sh -m

# Slim image - no desktop manager or cli tools
./raspberry-pi.sh --slim or ./raspberry-pi.sh -s

# Enable debug & log file (./logs/<file>.log)
./raspberry-pi.sh --debug or ./raspberry-pi.sh -d

# Perform extra checks on the images build
./raspberry-pi.sh --extra or ./raspberry-pi.sh -x

# Help screen (this)
./raspberry-pi.sh --help or ./raspberry-pi.sh -h
$
```

***

[Custom Values](broken-reference)

Editing `builder.txt`, will allow for custom values, such as using a local LAN mirror:

```
$ echo 'mirror="http://192.168.1.100/kali"' > ./builder.txt
```

A full list of values you can set:

```
# Version Kali release
#version=${version:-$(cat .release)}

# Custom hostname variable
#hostname=kali

# Choose a locale
#locale="en_US.UTF-8"

# Free space added to the rootfs in MiB
#free_space="300"

# /boot partition in MiB
#bootsize="128"

# Select compression, xz or none
#compress="xz"

# Choose filesystem format to format ( ext3 or ext4 )
#fstype="ext4"

# Disable IPV6 ( yes or no)
#disable_ipv6="yes"

# Make SWAP ( yes or no)
#swap="no"

# DNS server
#nameserver="8.8.8.8"

# To limit the number of CPU cores to use during compression
# Use 0 for unlimited CPU cores, -1 to subtract 1 cores from the total
#cpu_cores="4"

# To limit the CPU usage during compression
# 0 or 100 No limit, 10 = percentage use, 50, 75, 90, etc.
#cpu_limit="85"

# If you have your own preferred mirrors, set them here.
#mirror="http://http.kali.org/kali"

# If you use a custom mirror that your users won't have access to , you can replace_mirror to point them at the official mirrors instead.
#replace_mirror="http://http.kali.org/kali"

# Use packages from the listed components of the archive.
#components="main,contrib,non-free,non-free-firmware"

# Suite to use, valid options are:
# kali-rolling, kali-dev, kali-dev-only, kali-last-snapshot
#suite="kali-last-snapshot"

# If you build against something other than kali-rolling, you can set this so that the finished image will point to the kali-rolling suite
#replace_suite="kali-rolling"

# Default file name
# On the Raspberry Pi script, this would result in
# "kali-linux-202X-WXX-raspberry-pi-arm64" for the default filename.
# For release builds from Kali Linux, the requirements are that it start with kali-linux
# and end with the architecture.
#image_name="kali-linux-$(date +%Y)-W$(date +%U)-${hw_model}-${variant}"
```
