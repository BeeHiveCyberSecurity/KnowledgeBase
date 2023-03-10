# Import Pre-Made Kali VirtualBox VM

Importing the [Kali VirtualBox image](https://www.kali.org/get-kali/#kali-virtual-machines) is very easy.

We first need to extract the VirtualBox image:

```
:~$ 7z x kali-linux-2022.4-virtualbox-amd64.7z
[...]
:~$
```

If we are using Windows we can instead use the [official 7z app](https://www.7-zip.org/).

We then launch VirtualBox:

[![](https://www.kali.org/docs/virtualization/import-premade-virtualbox/import-vbox-weekly-1.png)](https://www.kali.org/docs/virtualization/import-premade-virtualbox/import-vbox-weekly-1.png)

From here we will be wanting to select ‘Add’. We then navigate to the location our VM is downloaded and find the `.vbox` file:

[![](https://www.kali.org/docs/virtualization/import-premade-virtualbox/import-vbox-weekly-2.png)](https://www.kali.org/docs/virtualization/import-premade-virtualbox/import-vbox-weekly-2.png)

We select this then we are able to continue forward:

[![](https://www.kali.org/docs/virtualization/import-premade-virtualbox/import-vbox-weekly-3.png)](https://www.kali.org/docs/virtualization/import-premade-virtualbox/import-vbox-weekly-3.png)

We can verify the settings that will be set here, and if we need to change any we can. Once we are happy we can select boot the VM and use it as normal. Remember the default login is kali for the user and kali for the password!
