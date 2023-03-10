# Installing VMware Tools (Guest Tools)

Installing “Guest Tools”, gives a better user experience with VMware VMs. This is why since Kali Linux 2019.3, during the [setup process](https://gitlab.com/kalilinux/build-scripts/live-build-config/-/blob/master/simple-cdd/profiles/offline.downloads) it should **detect if Kali Linux is inside a VM**. If it is, then **automatically install any additional tools** (in VMware case, `open-vm-tools` and `open-vm-tools-desktop`). The Guest Tools are also pre-installed in the Live image since Kali Linux 2021.3.

As of September 2015, **VMware** [**recommends**](https://blogs.vmware.com/vsphere/2015/09/open-vm-tools-ovt-the-future-of-vmware-tools-for-linux.html) **using the distribution-specific** [**open-vm-tools**](https://packages.debian.org/testing/open-vm-tools) **(OVT)** instead of the VMware Tools package for guest machines.

Should you decide to [create your own VMware installation of Kali Linux](broken-reference) _(rather than using our_ [_pre-made VMware images_](https://www.kali.org/get-kali/#kali-virtual-machines)_)_, and you want to force a manual reinstall of `open-vm-tools` (as something has gone wrong), first make sure you are [fully updated](https://www.kali.org/docs/general-use/updating-kali/), then enter the following:

```
:~$ sudo apt update
[...]
:~$
:~$ sudo apt install -y --reinstall open-vm-tools-desktop fuse
[...]
:~$
:~$ sudo reboot -f
:~$
```

Unfortunately, shared folders will not work out of the box, some additional scripts are needed. Those can be installed easily with `kali-tweaks`:

```
:~$ kali-tweaks
```

In the Kali Tweaks menu, select _Virtualization_, then _Install additional packages and scripts for VMware_. Congratulations, you now have two additional tools in your toolbox!

The first one is a little script to **mount the VMware Shared Folders**. Invoke it with:

```
:~$ sudo mount-shared-folders
```

And with a bit of luck, checking `/mnt/hgfs/` you should see your shared folders.

The second script is a helper to **restart the VM tools**. Indeed, it’s not uncommon for OVT to stops functioning correctly (e.g. such as copy/paste between the host OS and guest VM stops working). In this case, running this script can help to fix the issues:

```
:~$ sudo restart-vm-tools
```

***

For older versions of Kali Linux, here is our [previous guide](https://www.kali.org/docs/virtualization/install-vmware-guest-tools-legacy/).
