# Preparing a system for WSL

[What version of Windows?](broken-reference)

Depending on what version of Windows we have, we may need to follow different directions when setting up WSL. Windows 11 will be able to skip ahead to [Windows 11](broken-reference) as it comes with all of the necessary patches.

[Windows 10](broken-reference)

We can check our build version by pressing WIN+R and then typing in ‘winver’. We will be shown a page like this:

[![](<../../../.gitbook/assets/wsl prep 1.png>)](<../../../.gitbook/assets/wsl prep 1.png>)

What we are looking for is the number after ‘OS Build’. If we see the number ‘19041’ or a number higher, like is shown in the screenshot, we note this down and proceed to [Windows 10](broken-reference). If we see a number lower than this, we will be unable to use WSL2.

[Setting up WSL](broken-reference)[Windows 11](broken-reference)

To install and setup WSL we can run the command `wsl --install -d kali-linux`. We may need to perform a computer restart, but once complete we will have the latest version of Kali Linux installed.

[Windows 10](broken-reference)

We will need to open Powershell as Administrator for the following.

We first will run the following command to enable WSL:

```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

If we are setting up WSL2 we will want to skip to the next section. If we don’t then we can restart now and install Kali through the Microsoft Store.

[Setting up WSL2](broken-reference)

We can choose to enable WSL2 if we are the proper version of Windows. [WSL2](https://docs.microsoft.com/en-us/windows/wsl/compare-versions) enables some very helpful features and so it is recommended to enable it if your system supports it.

If we have a Windows 11 system or are build 19041 and higher, which we discovered in the previous section, then we are able to skip to [enabling WSL2 with set version](broken-reference). Otherwise, we press WIN+R and launch ‘winver’ again. This time we are checking to see if we fall under the following:

For x64 systems: Version 1903 or later, with Build 18362 or later. For ARM64 systems: Version 2004 or later, with Build 19041 or later.

[Enabling WSL2 with set version](broken-reference)

We first check to see if we are already set to WSL2 with the following command ran through Powershell:

```
Get-ItemPropertyValue `
      -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion\Lxss `
      -Name DefaultVersion
```

The output will either be a `1` or a `2`. If it is two then we can leave it be. Otherwise we run the following command:

```
wsl --set-default-version 2
```

Once we are happy we can choose to install Kali through the command `wsl --install -d kali-linux` if we are using Windows 11 or otherwise we can install it through the Microsoft Store!

[Enabling WSL2 manually](broken-reference)

```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

After this we restart our computer.

Next we download an update for Windows from the following: [Here if we are on an x64 system](https://wslstorestorage.blob.core.windows.net/wslblob/wsl\_update\_x64.msi) or [Here if we are on an ARM64 system](https://wslstorestorage.blob.core.windows.net/wslblob/wsl\_update\_arm64.msi)

Now we launch Powershell as administrator and run the following command:

```
wsl --set-default-version 2
```

Now just install Kali through the Microsoft Store to finish setup!
