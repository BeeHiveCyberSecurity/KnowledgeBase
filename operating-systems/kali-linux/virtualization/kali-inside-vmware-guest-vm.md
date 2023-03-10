# Kali inside VMware (Guest VM)

This guide is about virtualizing Kali Linux inside of VMware, allowing you to have a Kali VM. This is a great way to use Kali, as it is completely separate from the host, allows you to interact with other VMs (as well as the host, and other machines on the network), and allows you to revert to snapshots.

If you are trying to [install VMware on Kali Linux (as a host)](broken-reference), please see our guide.

The guide below is what we use to generate our [pre-made Kali Linux VMware images](https://www.kali.org/get-kali/#kali-virtual-machines). You may alter this to your needs. We always generate the images using the latest version of VMware Workstation, as Player and Fusion don’t have the same level of functionally and controls over settings.

You will need to enable virtualization in your BIOS/UEFI for (e.g. Intel VT-x/AMD-V)

[Wizard](broken-reference)

Upon starting up VMware Workstation, select “**Create a New Virtual Machine**”.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-01.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-01.png)

***

When you have the option, select “**Custom (advanced)**” for the Virtual Machine Configuration, as this will allow us to have more control over the creation of the VM.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-02.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-02.png)

***

The next screen is “Virtual Machine Hardware Compatibility”, which we use “**Workstation 8.x**”.

This allows for more users to benefit from Kali Linux out of the box (without having to edit the `.vmx` file to [downgrade](https://communities.vmware.com/thread/517825)). If you are using a later version of VMware than v8, upon start up, VMware will prompt about upgrading the VM. This will remove any limitations caused by older VMware profiles. However, most users do not have their Kali Linux VM using all these extra resources (see screenshot below), so they wouldn’t benefit from having the latest profile, **which is why we ship with a older profile**.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-03.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-03.png)

***

On this screen, we select the Kali Linux image to use to install from. We select “**Browse**”, and navigate to the location of the ISO that we [downloaded](https://www.kali.org/docs/introduction/download-official-kali-linux-images/). For more information on [what image to download, we have written up a guide](https://www.kali.org/docs/introduction/what-image-to-download/).

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-04.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-04.png)

***

When you see the “Guest Operating System” screen, select “**Linux**”, and then the **latest version of Debian** for the version (as [Kali is based on Debian](https://www.kali.org/docs/policy/kali-linux-relationship-with-debian/)). In this example, its Debian 10. We are going to be use the x64 image to install Kali, so we have selected 64-bit.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-05.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-05.png)

***

The next screen is “Virtual Machine Name”, which is where you name the VM. This name is also used as the filename (such as the configuration, hard disk and snapshot - which is not changed from this point).

We are keeping it generic in this guide, by using “**Kali Linux**” (as Kali Linux is a [rolling distribution](https://www.kali.org/docs/general-use/kali-branches/), and we [update Kali Linux](https://www.kali.org/docs/general-use/updating-kali/)). However for our releases, we use the version number in the name as it is a fixed release _(`kali-linux-YYYY.N-vmware-ARCH`. Example: `kali-linux-2022.4-vmware-amd64`)_.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-06.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-06.png)

***

The next screen is “Processors”. Here we can start to define how many resources we give the VM. Kali will be able to perform more tasks simultaneously and quicker if it is allocated more resources. We select “**2 processors**” and “**2 cores per processors**”, giving a total of 4 cores. You may wish to use more or less depending on your system requirements.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-07.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-07.png)

***

“Memory” is the next section, where we can define how much RAM to use. Again, the higher amount of RAM, the more applications can be open and at increased performance. Various tools inside of Kali can be demanding of resources. When we make the general VMs, we select 2GB (**2048 MB**) for RAM, but we often increase this for our personal machines as we have high-performing devices with spare RAM which Kali can utilize.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-08.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-08.png)

***

We are then presented with “Network Connection”. We default to using a **NAT** connection. However, this can easy be altered (even when the VM is powered on). This allows for Kali VM to talk to the Internet, as well as the rest of the LAN connection, without it taking up an additional IP address. The downside to this is it will not be able to receive reverse shells (without port forwarding inside of VMware).

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-09.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-09.png)

***

Next is “I/O Controller Types”. We accept the default value of “**LSI Logic**”.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-10.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-10.png)

***

Next is “Virtual Disk Type”. We accept the default value of “**SCSI”**

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-11.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-11.png)

***

The following screen is “Disk”, which allows us to “**create a new virtual disk”**

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-12.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-12.png)

***

This screen below, “Disk Size”, allows us to define how large the virtual hard disk will be. We use “**80 GB**” for our VMs.

We also don’t have it in a single file, but instead “**Split virtual disk into multiple files**”. The VM hard disk will grow over time, to the maximum size, as we do not enable the “Allocate all disk space”.

It is possible to increase/decrease the hard disk after the VM has been created, however, if you have installed Kali, you’ll need to then also grow or shrink the partition for the space to reflect that.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-13.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-13.png)

***

When it comes to the “Disk File” screen, we accept the default value, which has been defined from our VM name earlier in the setup process.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-14.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-14.png)

***

We are then presented the final screen for the VM setup wizard, which gives us an overview of the settings we picked.

We are happy with what’s shown to us, so we then press “**Finish**”. If you try and “Customize Hardware” at this stage, before the VM is fully created, not every setting is visible.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-15.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-15.png)

***

If this is the first time using the wizard, you may have the following prompt explaining how installing “[VMware tools](broken-reference)” will give you a better experience when using the VM.

After reading and understanding the page, you may wish to tick the “Don’t show this page again”, before pressing close.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-16.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-16.png)

***

[Edit Settings](broken-reference)

Before we start up the VM, we now edit its settings, by pressing “**Edit virtual machine settings**”.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-17.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-17.png)

***

We do not have a use for a printer, so we remove it. Navigate to the “**Printer**” section, and then press “**Remove**”.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-18.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-18.png)

***

You may wish to edit the “**USB**” settings to alter how USB devices behave. Here we have disabled “**Automatically connect new USB devices**” _(may not have the option depending on your VMware version)_ and enabled “**Show all USB input devices**”.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-usb.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-usb.png)

***

Another item to point out is in the “Display” section. Make sure that “**Accelerated 3D graphics**” is **disabled**, as people have reported that causes issues.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-gpu.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-gpu.png)

***

We then move over to the “**Options**” tab, and move down to “**Power**”. We choose to enable “**Report battery information to guests**”, as it is a handy thing for users who use Kali on a laptop/notebook.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-19.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-19.png)

***

In “**Shared folders**”, we select “**Always enable**”. At this stage, do not share any paths, as some users may not wish for it.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-20.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-20.png)

***

The final option we alter is “**VMware Tool**”, where we enable “**Synchronize guest time with host**”.

[![](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-21.png)](https://www.kali.org/docs/virtualization/install-vmware-guest-vm/vm-21.png)

***

After all this is done, we save, start up the VM, and then continue installing Kali Linux as we normally would for a [bare metal install](https://www.kali.org/docs/installation/hard-disk-install/).

During Kali Linux setup process, the [install wizard](https://gitlab.com/kalilinux/build-scripts/live-build-config/-/blob/master/simple-cdd/profiles/offline.downloads) should **detect if its inside a VM**. If it is, should then **automatically install any additional tools** (such as `open-vm-tools`) to give a better user experience. If you want to manually re-install it, you can see our [VMware Guest Tools Guide](broken-reference).
