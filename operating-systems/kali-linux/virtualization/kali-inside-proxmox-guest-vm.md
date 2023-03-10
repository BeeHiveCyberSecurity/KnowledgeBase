# Kali inside Proxmox (Guest VM)

Due to the type of hypervisor Proxmox is we do not have a documentation page on how to install it. However, this can be found through [Proxmox’s official page](https://www.proxmox.com/en/proxmox-ve/get-started).

Proxmox has two ways of accessing a nested environment. The first is through virtualization, using QEMU. The other is through containerization using LXC. We will discuss both methods.

[Kali as a Proxmox VM (Virtualization)](broken-reference)

We will go over the steps and discuss some of the changes that can be made.

* Download the latest ISO from [get Kali](https://www.kali.org/get-kali/#kali-installer-images)
* Select “Create VM”
* Assign the VM a name and ID
* Select the ISO we downloaded previously
* We can skip past “System” using the defaults
* Create a disk with at least 20 GiB, you may need more so think about your needs when selecting storage
* Select 2 for both “Sockets” and “Cores” to get our total cores to 4, you may be able to use less or may need more, again think about your needs
* Use at least 2048 MiB
* Be sure to select the proper network device, if you are unsure which to select leave it as default
* Confirm your settings

From here we select the new VM under our node and after selecting “Console” we select “Start Now”. From here we can proceed as though it is a [normal install](https://www.kali.org/docs/installation/hard-disk-install/).

[Kali as a Proxmox CT (Containerization)](broken-reference)

We will go over the steps and discuss some of the changes that can be made.

We first need to install the container template to be used. To do this we navigate to [a LXD repo](https://us.lxd.images.canonical.com/images/kali/current/) and determine what our requirements are. For this guide, we have a Proxmox system that is run on amd64 hardware, so we select that. We are going to select default, this will go for all hardware options. Next we select the most recent date. Now we download the “rootfs.tar.xz”. We can alternatively copy this link and in Proxmox under “CT Templates” select “Download from URL” and supply this URL and then query it.

* Select “Create CT”
* Assign the container a hostname and a password. If relevant, supply a SSH public key as well.
* Select the template we downloaded previously
* Depending on the use-case of this container, you may want to give the system more storage. A good balance would be to give it 20 GiB for a typical Kali install.
* Up the “Cores” to be 2, you may be able to use less or may need more, think about your needs
* Again, depending on the use case you may want to up the amount of memory. A good balance would be to give it 2048 for a typical Kali install, with 1024 swap.
* Select network settings if necessary, otherwise leave as default.
* If necessary change the DNS settings
* Confirm settings and finish setup

From here we wait for the container to be created and finish with “TASK OK”. Once this is complete we can close this window, select the container under our node, select console, and select “Start” on the top bar. We login with “root” user and the password we input earlier.
