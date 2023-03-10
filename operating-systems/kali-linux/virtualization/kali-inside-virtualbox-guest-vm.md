# Kali inside VirtualBox (Guest VM)

This guide is about virtualizing Kali Linux inside of VirtualBox, allowing you to have a Kali VM. This is a great way to use Kali, as it is completely separate from the host, allows you to interact with other VMs (as well as the host machine and other machines on the network), and allows you to revert to snapshots.

You may wish to follow our other guide if you are trying to install VirtualBox on Kali Linux (as a [host](broken-reference)).

The guide below is what we use to generate our [pre-made Kali Linux VirtualBox images](https://www.kali.org/get-kali/#kali-virtual-machines). You may alter this to your needs. We always generate the images using the [latest version of VirtualBox](https://www.virtualbox.org/wiki/Downloads).

You may need to enable virtualization in your BIOS/UEFI for (e.g. Intel VT-x/AMD-V)

[Wizard](broken-reference)

Upon starting up VirtualBox, select “New” (Machine -> New).

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-01.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-01.png)

***

The next screen is “Name and operating system” which is where you name the VM. This name is also used in any filenames (such as the configuration, hard disk and snapshot - which isn’t changed from this point).

We are keeping it generic in this guide (as Kali is a [rolling distribution](https://www.kali.org/docs/general-use/kali-branches/), and we update it), however for our releases, we use the version number in the name as it is a fixed release _(`kali-linux-YYYY.N-vbox-ARCH`. Example: `kali-linux-2022.4-vbox-amd64`)_.

For the “Type”, we set it as `Linux`. For the “Version”, we are going to be using the x64 desktop image, so we are going to select `Debian (64-bit)`.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-02.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-02.png)

***

“Memory size” is the next section, where we can define how much RAM to use. Again, the higher the amount of RAM, the more applications can be open and at increased performance. Various tools inside of Kali can be demanding of resources. When we make the general VMs, we select `2048 MB` (2GB) for RAM, but we often increase this for our personal machines as we have high-performing devices with spare RAM which Kali can utilize.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-03.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-03.png)

***

This screen below, “Hard disk”, allows us to `Create a new virtual disk now`.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-04.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-04.png)

***

For the “Hard disk file type”, we select `VDI (VirtualBox Disk Image)` (and its the default option).

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-05.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-05.png)

***

For the following screen, “Storage on physical hard disk”, we go with the default option of `Dynamically allocated`.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-06.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-06.png)

***

Now with “File location and size”, we can now define how large the virtual hard disk will be. We use `80.00 GB` for our VMs.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-07.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-07.png)

***

After clicking on “Create”, the wizard is complete.

Now we click on “Settings”, to customize the VM further.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-08.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-08.png)

***

In “General” -> “Advanced”, we make sure to set “Shared Clipboard” to `bidirectional`, as well as “Drag’n’Drop” to `bidirectional`

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-09.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-09.png)

***

In “System” -> “Motherboard”, we change the “Boot Order” to make sure `Hard Disk` is top and `Optical` is the second. Everything else is disabled.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-10.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-10.png)

***

In “System” -> “Processor”, we increase the “Processor(s)” to be `2`.

At the same time, we also enable “Extended Features” for `Enable PAE/NX`.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-11.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-11.png)

***

In “Display” -> “Screen”, we make sure to have “Video Memory” set to `128 MB`

Another item to point out is to make sure that “Accelerated 3D graphics” is **disabled**, as people have reported that causes issues.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-12.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-12.png)

***

The final settings view looks like the following:

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-13.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-13.png)

***

When we are ready to go, press “Start”.

The first time we run it, we will get a prompt saying do we wish to mount an image to use as a “start-up disk”. We want to use our Kali image, rather than a physical drive, so we select the icon to the side of the drop down.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-14.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-14.png)

***

A new pop up will open, “Optical Disk Selector”. We will now press “Add”, then navigate to where our ISO is located.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-15.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-15.png)

***

After pressing “Open”, we can see its been added, so we make sure its selected and press “Choose”.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-16.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-16.png)

***

All that is left now to do is press “Start”.

[![](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-17.png)](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/vb-17.png)

***

After all this is done, we save, start up the VM, and then continue installing Kali Linux as we normally would for a [bare metal install](https://www.kali.org/docs/installation/hard-disk-install/).

During Kali Linux setup process, the [install wizard](https://gitlab.com/kalilinux/build-scripts/live-build-config/-/blob/master/simple-cdd/profiles/offline.downloads) should **detect if its inside a VM**. If it is, should then **automatically install any additional tools** (such as `virtualbox-guest-x11`) to give a better user experience. If you want to manually re-install it, you can see our [VirtualBox Guest Guide](broken-reference).
