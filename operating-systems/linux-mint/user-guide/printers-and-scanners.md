# Printers and Scanners

[Linux Mint User Guide](broken-reference)

### Driverless Printing and Scanning (IPP)[¶](broken-reference)

Since version 21, Linux Mint features driverless printing and scanning:

* Printers and scanners are detected and added automatically.
* Communication with the device is done via a standard protocol called _IPP_.
* No drivers are needed.
* Installed drivers are not used.

This standard protocol works with many devices, so for most printers and scanners, there is nothing to do. Everything just works out of the box.

To print a document open _File_ -> _Print…_ in your application.

To scan a document open _Document Scanner_ from the application menu.

### Manufacturer Drivers[¶](broken-reference)

If your device doesn’t work well with _IPP_ you can use drivers from your manufacturer instead.

In this case you need to:

* Disable _IPP_
* Install your manufacturer’s drivers

#### Disabling IPP[¶](broken-reference)

IPP takes priority so as long as it’s installed, drivers won’t be used.

To remove IPP support from your computer open a terminal and type:

```
apt remove ipp-usb sane-airscan
```

#### Hewlett-Packard (HP)[¶](broken-reference)

The HP drivers are called _HPLIP_.

They are open-source and they already are installed by default in Linux Mint.

**Installing hplip-gui**[**¶**](broken-reference)

In addition to the already installed _hplip_ driver, there is a package available in the Linux Mint repositories called _hplip-gui_.

This package provides the following utilities:

* An HP status tray icon
* HP Device Manager
* HPLIP Toolbox
* HPLIP Fax Utility
* Fax Address book

Although you do not need _hplip-gui_ to use your HP device, it can provide extra information (such as ink levels) and help troubleshooting.

**Installing the proprietary plug-in**[**¶**](broken-reference)

Some HP printers require proprietary software technologies to allow full access to printer features and performance. Unfortunately, these technologies cannot be open sourced, but to resolve this HP uses a binary plug-in for these printers.

To see if your printer requires the HP plugin-in, check the list of devices at the [HP Developer Website](https://developers.hp.com/hp-linux-imaging-and-printing/binary\_plugin.html).

To install the plugin-in, open a terminal and type:

```
apt install python3-pyqt5
sudo hp-setup
```

Then follow the instructions written on that website.

#### Brands which provide .deb packages[¶](broken-reference)

The following brands provide Linux drivers for their printers and scanners in the form of _.deb_ packages:

* Epson
* Lexmark
* Samsung
* Xerox

Look for Linux drivers on your manufacturer’s website, download the packages and double-click them to install them with _Gdebi_.

Hint

When you have a choice between different package options, choose _.deb_. If you have a choice for the package architecture choose _amd64_ (note that this is sometimes called _x86\_64_ or even just _64-bit_).

#### Canon[¶](broken-reference)

Canon provides Linux drivers for its printers and scanners. They have different websites for Europe, the USA and various countries.

When downloading drivers from Canon, choose the _debian Package archive_ option.

If they come as _.tar.gz_ archives, decompress them.

Canon driver archives usually contain an _install.sh_ script which already has execution permissions. Run it and follow the instructions provided by Canon.

#### Brother[¶](broken-reference)

Brother provides a utility to download and install the right driver for you.

Download the utility, choose _deb_ when asked.

Decompress it, give it permission to execute and run it in a terminal:

```
chmod a+rx ./linux-brprinter-installer*
sudo ./linux-brprinter-installer*
```

Then follow the instructions provided by Brother.

### Troubleshooting[¶](broken-reference)

#### Adding IPP support[¶](broken-reference)

In Linux Mint 20.x _IPP_ isn’t installed by default.

If you want to give it a try, remove your printer using the _Printers_ configuration tool.

Then install _ipp-usb_ and _sane-airscan_ from the repositories:

```
apt install ipp-usb sane-airscan
```

Finally reboot the computer.

#### Disabling network printers detection[¶](broken-reference)

Network printers are automatically added and reappear even if you remove them.

If you do not like this behaviour, remove the _cups-browsed_ package.

#### Removing ippusbxd[¶](broken-reference)

_ippusbxd_ was an early implementation of _IPP_ over USB. It didn’t work well and caused many issues. It was installed by default in Linux Mint 20. If this package is installed on your computer, make sure to remove it.

Then reboot your computer.
