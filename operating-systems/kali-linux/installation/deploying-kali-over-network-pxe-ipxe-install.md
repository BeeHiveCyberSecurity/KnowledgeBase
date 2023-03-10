# Deploying Kali over Network PXE/iPXE Install

Booting and installing Kali Linux over the network ([PXE](https://en.wikipedia.org/wiki/Preboot\_Execution\_Environment)) can be useful from a single laptop install with no CDROM or [USB](https://www.kali.org/docs/usb/) ports, to enterprise deployments supporting pre-seeding of the Kali Linux installation.

We will cover three different ways of using PXE. The first way will be how to manually set up PXE with `dnsmasq`. The second will be a partially-automated way using Docker. The final way will utilize netbootxyz, which hosts the PXE files and uses a separate DNS server to properly direct computers. Please utilize the Table of Contents to quickly navigate to the method you want to follow.

[Manually setting up a PXE Server with `dnsmasq`](broken-reference)

First, we need to install [**dnsmasq**](https://packages.debian.org/testing/dnsmasq) to provide the DHCP/TFTP server and then edit the `dnsmasq.conf` file:

```
:~$ sudo apt install -y dnsmasq
[...]
:~$
:~$ sudo vim /etc/dnsmasq.conf
:~$
```

***

In `dnsmasq.conf`, enable **DHCP**, **TFTP** and **PXE booting** and set the `dhcp-range` to match your environment (we are using **192.168.101.100-200**). If needed you can also define your gateway and DNS servers with the `dhcp-option` directive as shown below:

```
interface=eth0
dhcp-range=192.168.101.100,192.168.101.200,12h
dhcp-boot=pxelinux.0
enable-tftp
tftp-root=/tftpboot/
dhcp-option=3,192.168.101.1
dhcp-option=6,8.8.8.8,8.8.4.4
```

***

With the edits in place, the dnsmasq service needs to be restarted in order for the changes to take effect:

```
:~$ sudo systemctl restart dnsmasq
:~$
```

[Download Kali PXE Netboot Images](broken-reference)

Now, we need to create a directory to hold the Kali Linux Netboot image and download the image we wish to serve:

```
:~$ sudo mkdir -p /tftpboot/
:~$

# 64-bit:
:~$ sudo wget https://http.kali.org/kali/dists/kali-rolling/main/installer-amd64/current/images/netboot/netboot.tar.gz -P /tftpboot/
# 32-bit:
:~$ sudo wget https://http.kali.org/kali/dists/kali-rolling/main/installer-i386/current/images/netboot/netboot.tar.gz -P /tftpboot/

:~$ sudo tar -zxpf /tftpboot/netboot.tar.gz -C /tftpboot
:~$
:~$ sudo rm -f /tftpboot/netboot.tar.gz
:~$
```

[Configure Target to Boot From Network](broken-reference)

With everything configured, you can now boot your target system and configure it to boot from the network. It should get an IP address from your PXE server and begin booting Kali Linux.

[Post Installation](broken-reference)

Now that you’ve completed installing Kali Linux, it’s time to customize your system. The [General Use section](https://www.kali.org/docs/general-use/) has more information and you can also find tips on how to get the most out of Kali Linux in our [User Forums](https://forums.kali.org/).

One last thing we need to do if we want to use this system in the future is set up a cron job to pull in the new Netboot images regularly in case of kernel updates. We will create a simple script for this purpose named pxe.sh:

```
#!/bin/sh

## We input our desired path for the PXE image to be saved to
tftp=/tftpboot
arch=amd64

## We remove the previous directory containing the PXE image and download the newest version
rm -rf $tftp/
mkdir -p $tftp/
wget https://http.kali.org/kali/dists/kali-rolling/main/installer-$arch/current/images/netboot/netboot.tar.gz -P $tftp/
tar -zxpf /tftpboot/netboot.tar.gz -C $tftp
rm -f $tftp/netboot.tar.gz
```

We save this script to `/opt` and are sure to set it’s permissions so you can only edit it with **root** or **sudo**. An example of this is to set the file to `770` or `700` with chmod, and set it to `root:root` with chown.

We can now add it to a cron job:

```
:~$ sudo crontab -e
[...]
0 5 * * 2 /opt/tftpboot.sh
[...]
:~$
```

[Using Docker and `dnsmasq` to automate setup of a PXE server](broken-reference)[Docker file and dnsmasq.conf](broken-reference)

The docker file we will use looks like the following:

```
FROM kalilinux/kali-rolling

ENV HOME /root

RUN apt update && apt install -y init

CMD ["/sbin/init"]

RUN apt install -y dnsmasq syslinux nginx iproute2 vim wget net-tools less

RUN rm /etc/dnsmasq.conf

COPY dnsmasq.conf /etc/dnsmasq.conf

RUN mkdir -p /tftpboot/

RUN wget https://http.kali.org/kali/dists/kali-rolling/main/installer-amd64/current/images/netboot/netboot.tar.gz -P /tftpboot/

RUN tar -zxpf /tftpboot/netboot.tar.gz -C /tftpboot

RUN rm -f /tftpboot/netboot.tar.gz
```

Before we can build this container we need to create the file `dnsmasq.conf`. We use the following options:

```
interface=eth0
dhcp-range=192.168.115.25,192.168.115.255,12h
dhcp-boot=pxelinux.0
enable-tftp
tftp-root=/tftpboot/
dhcp-option=3,192.168.115.2
dhcp-option=6,8.8.8.8,8.8.4.4
```

[Launch Docker container](broken-reference)

We run the following commands to create our Docker container. Please note `--privileged=true` and `--network host` is necessary for the port mapping to work properly:

```
:~$ docker build --tag="kali/systemd" .
:~$ docker run -it -d --privileged=true --network host kali/systemd /sbin/init
:~$ docker exec -it docker-container-id bash
```

[**Post-startup**](broken-reference)

Once booted and connected, we must run the following command:

```
:~$ sudo systemctl restart dnsmasq
```

We are now good to go!

[Preseeding PXE](broken-reference)[**Preseed file**](broken-reference)

We can use the following preseed file to automatically install our Kali instance. Be sure to change package selection, user information, region information, and hard drive to match what you are using. Alternatively, should you want to be prompted for any of those, just comment out the line:

```
# Package selection
d-i pkgsel/include string kali-linux-default kali-desktop-xfce

# User information
d-i passwd/user-fullname string kali
d-i passwd/username string kali
d-i passwd/user-password password kali
d-i passwd/user-password-again password kali

# Region Information
d-i time/zone string US/Eastern
d-i debian-installer/locale string en_US
d-i debian-installer/language string en
d-i debian-installer/country string US
d-i debian-installer/locale string en_US.UTF-8
d-i keyboard-configuration/xkb-keymap select us

# Hard drive
d-i grub-installer/bootdev string /dev/sda

d-i netcfg/get_hostname string kali
d-i netcfg/get_domain string unnasigned-domain
tasksel tasksel/first multiselect standard
d-i mirror/country string enter information manually
d-i mirror/suite string kali-rolling
d-i mirror/codename string kali-rolling
d-i mirror/http/hostname string http.kali.org
d-i mirror/http/directory string /kali
d-i mirror/http/proxy string
d-i partman-auto/method string regular
d-i partman-auto-lvm/guided_size string max
d-i partman-auto/choose_recipe select atomic
d-i partman-partitioning/confirm_write_new_label boolean true
d-i partman/choose_partition select finish
d-i partman/confirm boolean true
d-i partman/confirm_nooverwrite boolean true
d-i partman-md/confirm boolean true
d-i partman-partitioning/confirm_write_new_label boolean true
d-i partman/choose_partition select finish
d-i partman/confirm boolean true
d-i partman/confirm_nooverwrite boolean true
d-i grub-installer/only_debian boolean true
d-i grub-installer/with_other_os boolean true
d-i finish-install/reboot_in_progress note
d-i apt-setup/services-select multiselect
d-i apt-setup/non-free boolean true
d-i apt-setup/contrib boolean true
d-i apt-setup/disable-cdrom-entries boolean true
d-i apt-setup/enable-source-repositories boolean false
d-i pkgsel/upgrade select full-upgrade
d-i passwd/root-login boolean false
d-i preseed/early_command string anna-install eatmydata-udeb
d-i pkgsel/update-policy select none
popularity-contest popularity-contest/participate boolean false
encfs encfs/security-information boolean true
encfs encfs/security-information seen true
console-setup console-setup/charmap47 select UTF-8
samba-common samba-common/dhcp boolean false
macchanger macchanger/automatically_run boolean false
kismet-capture-common kismet-capture-common/install-users string
kismet-capture-common kismet-capture-common/install-setuid boolean true
wireshark-common wireshark-common/install-setuid boolean true
sslh sslh/inetd_or_standalone select standalone
atftpd atftpd/use_inetd boolean false
```

[**Preseed integration to initrd**](broken-reference)

To incorporate this into our initrd to automatically run we must do the following:

```
:~$ gunzip initrd.gz
:~$ echo preseed.cfg | cpio -H newc -o -A -F initrd
:~$ gzip initrd
:~$ systemctl restart dnsmasq
```

[Using netbootxyz to host our PXE files](broken-reference)

To install netbootxyz we will follow the [official documentation](https://netboot.xyz/docs/docker). Using this method will allow us to set up a server and use our existing DHCP server to point to it, rather than creating a new DHCP server.
