# Digital Ocean

[DigitalOcean](https://www.digitalocean.com/) is a cloud provider similar to AWS, Microsoft Azure, Google Cloud Platform, and many others. They offer instances, called “droplets”, with different Linux distributions such as Debian, Ubuntu, FreeBSD, etc. Similar to AWS, DigitalOcean has datacenters around the world and sometimes multiple datacenters in each country.

However, one feature in particular sets them apart them from their competitors. A little while ago, they added support for [custom images](https://blog.digitalocean.com/custom-images/), which allows users to import virtual machine disks and use them as droplets. This is perfect for us as we can use our own version of Kali Linux in their cloud.

While it might be possible to load the [official Kali Linux virtual images](https://www.kali.org/get-kali/#kali-virtual-machines), it wouldn’t be very efficient. Instead, we’ll build a lightweight Kali installation with the bare minimum to get it working.

[Get the netboot ISO](broken-reference)

By default, the Kali Linux ISOs on the download page have a desktop environment installed, and while we could use it to build a virtual machine, we want to minimize the amount of data we have to upload to DigitalOcean for reasons we will talk about later. Having a GUI running on a headless system is also a waste of resources so while we could uninstall it or disable it, we’ll install the virtual machine using [a netboot ISO](http://http.kali.org/kali/dists/kali-rolling/main/installer-amd64/current/images/netboot/). If you are comfortable with a text installation, grab the mini.iso in this directory. If not, head to the [gtk/](https://http.kali.org/kali/dists/kali-rolling/main/installer-amd64/current/images/netboot/gtk/) directory and grab the mini.iso in there, which will start a graphical installer.

[Create the Virtual Machine](broken-reference)

With our mini.iso , we can now begin to build our virtual machine. Create a new virtual machine setting the OS to the latest Debian 64-bit and allocating a 20 GB hard disk. If needed, detailed set-up is explained on the [Kali Training website](https://web.archive.org/web/20210922173942/https://web.archive.org/web/20210914172345/https://kali.training/topic/booting-kali-in-live-mode/). It is important to store the virtual disk as a single file that is dynamically allocated. The rest like the amount of CPU and RAM won’t matter because only the disk file will be uploaded to DigitalOcean.

Disk size matters as billing is based on disk size for custom images. It will also impact the choice of instance we can create. Let’s say a 40 GB hard disk is created, it will prevent creating an instance at the $5/month level because its maximum hard disk size is 25 GB. In that case we would be forced to use the $10/month option for instances with 50 GB disks. Don’t worry, even though the disk is 20 GB, it will get expanded depending on the droplet plan chosen.

During the installation, select manual partitioning and set it up as shown below, with all files in one partition and no swap file.

[![](<../../../.gitbook/assets/digitalocean 1.png>)](<../../../.gitbook/assets/digitalocean 1.png>)

During the installation, it will prompt for software preferences. For the sake of simplicity and to limit disk space use, we’ll just have the base system installed, therefore we’ll only select “standard system utilities” as shown below.

[![](<../../../.gitbook/assets/digitalocean 2.png>)](<../../../.gitbook/assets/digitalocean 2.png>)

[Update the System](broken-reference)

When installation is complete and after rebooting, we login at the console and [update the system](https://www.kali.org/docs/general-use/updating-kali/):

```
:~$ sudo apt update
:~$ sudo apt full-upgrade -y
```

If you don’t see it going over a mirror during `sudo apt update`, you may have accidentally forgotten to add a network mirror during the installation. Follow the [instructions on this Kali documentation page](https://www.kali.org/docs/general-use/kali-linux-sources-list-repositories/) to fix it and run both of the commands again.

[Install Required Packages](broken-reference)

In order for DigitalOcean to configure the system for us, we need to install the _**cloud-init**_ package:

```
:~$ sudo apt install -y cloud-init
:~$ sudo sh -c "echo 'datasource_list: [ ConfigDrive, DigitalOcean, NoCloud, None ]' > /etc/cloud/cloud.cfg.d/99_digitalocean.cfg"
:~$ sudo systemctl enable cloud-init --now
```

[Prepare for SSH](broken-reference)

Since we will need to use SSH to connect to the system on DigitalOcean, the _**openssh-server**_ package needs to be installed (and enabled) as well:

```
:~$ sudo apt install -y openssh-server
:~$ sudo systemctl enable ssh.service --now
```

When creating a standard droplet, you can choose to use SSH keys or not. However, when using custom images, this isn’t an option and using SSH keys is mandatory. For this reason, DigitalOcean requires us to remove the root password:

```
:~$ passwd -d root
```

We also need to create a _**/root/.ssh**_ folder:

```
:~$ mkdir -p /root/.ssh/
```

[Cleanup](broken-reference)

Before we finish with our virtual machine, we run a few commands to clean things up:

```
:~$ apt autoremove
:~$ apt autoclean
:~$ rm -rf /var/log/*
:~$ history -c
```

At this point, our virtual machine is ready so we run ‘poweroff’ to shutdown the system:

```
:~$ poweroff
```

[Uploading](broken-reference)

In the virtual machine folder, locate the _**.vmdk**_ file, then compress it using bzip2, gzip, or zip in preparation for uploading to DigitalOcean:

```
$ bzip2 kali.vmdk
```

Login to your DigitalOcean account. In the “Manage” section on the left, click on “Images”, then select the “Custom Images” tab.

[![](<../../../.gitbook/assets/digitalocean 3.png>)](<../../../.gitbook/assets/digitalocean 3.png>)

From there, we upload the compressed disk image. We’ll name it Kali, mark it as Debian, and select the region and datacenter to upload it to. Note that once uploaded to a location, droplets can only be started at that location, which is a current limitation for custom images. Another thing to remember at this stage is that uploaded images consume disk space and DigitalOcean will bill based on disk usage.

[![](<../../../.gitbook/assets/digitalocean 4.png>)](<../../../.gitbook/assets/digitalocean 4.png>)

[Starting a Droplet](broken-reference)

Once done, the “Uploaded” column will indicate how long ago it was uploaded. Now we will click on the “More” option of the image and select “Start a droplet”.

[![](<../../../.gitbook/assets/digitalocean 5.png>)](<../../../.gitbook/assets/digitalocean 5.png>)

You will be taken to the droplet settings where you can select the droplet plan, the SSH key, and the project to start it in. Since this is a custom image, it is required you use a SSH key. You can either select an existing one or upload a new one by clicking on “New SSH key”, which will open the following screen where you can paste the public key and name it:

[![](<../../../.gitbook/assets/digitalocean 6.png>)](<../../../.gitbook/assets/digitalocean 6.png>)

Once done, click “Create” as shown below. It will then take you back to the dashboard (Manage > Droplets) where all your droplets are listed. Because we are using a SSH key, DigitalOcean will not send an email with credentials for the droplet.

[![](<../../../.gitbook/assets/digitalocean 7.png>)](<../../../.gitbook/assets/digitalocean 7.png>)

Within a few seconds, and after the IP is displayed, our droplet will be ready. In order to connect, we will need to use the private SSH key we created (called MY\_KEY in this example):

```
$ ssh -i MY_KEY 
The authenticity of host '192.168.1.1 (192.168.1.1)' can't be established.
ECDSA key fingerprint is SHA256:d83fcd43d25e2a7edd291666160b47360cc85870ded.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'IP' (ECDSA) to the list of known hosts.
Linux kali-s-1vcpu-1gb-nyc3-01 4.19.0-kali5-amd64 #1 SMP Debian 4.19.37-2kali1 (2019-05-15) x86_64
The programs included with the Kali GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.
Kali GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
```

Now we have a nice, minimal Kali Linux installation that we can deploy and customize as needed:

```
:~$ lsb_release -a
No LSB modules are available.
Distributor ID: Kali
Description: Kali GNU/Linux Rolling
Release: 2019.2
Codename: n/a

:~$
:~$ uname -a
Linux kali-s-1vcpu-1gb-nyc3-01 4.19.0-kali5-amd64 #1 SMP Debian 4.19.37-2kali1 (2019-05-15) x86_64 GNU/Linux

:~$
:~$ free -h
total used free shared buff/cache available
Mem: 987Mi 51Mi 527Mi 1.0Mi 407Mi 790Mi
Swap: 0B 0B 0B
:~$
```
