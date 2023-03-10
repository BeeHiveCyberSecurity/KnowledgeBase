# Troubleshooting Wireless Drivers

Troubleshooting wireless driver issues in Linux can be a frustrating experience if you don’t know what to look for. This article is meant to be used as a general guideline to better help you find the information you need to solve your wireless issues. The most thorough source for wireless driver information is the [aircrack-ng documentation](http://www.aircrack-ng.org/documentation.html).

90% of wireless issues reported to us are due to people not reading the Aircrack-ng documentation. You need to run airmon-ng check kill before putting your card in monitor mode.

Carefully read carefully ANY error message as they will VERY OFTEN tell you what’s wrong and how to fix it. If not, then use your Google-Fu.

[1. No Interface](broken-reference)

* Stupid question: Is it a wireless card? (We’ve seen that several times)
* Is the device plugged in?
* Does it show up on **lsusb** or **lspci** (with the exception of phones)? You might want to update pci ids and usb ids
* Does **dmesg** contain any information about the driver loading and/or failing
* Is Kali a VM? Then, unless your card is USB, it will not be useable (VMware/VirtualBox/QEMU will virtualize EVERY PCI device). Is it attached to the VM?
* If there is nothing in **dmesg** and it’s not in a VM, then you might want to try the latest _compat-wireless_ (and sometimes, you’ll need firmware) -> check on Linux-Wireless drivers

[2. Interface But Can’t Do Anything](broken-reference)

* Read error messages
* If there are no error messages, then run **dmesg | tail** and it will most likely tell you what’s wrong
* Firmware might be missing
* Check rfkill and any hardware switches and BIOS options

[3. No Monitor Mode](broken-reference)

* STA drivers (Ralink, Broadcom) and every other manufacturer’s provided driver doesn’t support monitor mode
* ndiswrapper doesn’t support monitor mode AND NEVER WILL.
* Airodump-ng/Wireshark don’t show any packets: check rfkill and any hardware switches and BIOS options

[4. Injection](broken-reference)

* Test with aireplay-ng -9 (Make sure the card is in monitor mode with airmon-ng)
* Airmon-ng doesn’t display chipset information: It’s not a big issue as it just didn’t get that information from the card and doesn’t change the abilities of your card
* No injection but monitor mode: Check rfkill and any hardware switches and BIOS options
* Network managers sometimes interfere with Aircrack tools. run **airmon-ng check kill** to kill these processes.

[Additional Links](broken-reference)

* [Will my card work with Aircrack-ng?](https://aircrack-ng.blogspot.com/2012/10/will-my-card-work-with-aircrack-ng.html)
* [Compat-wireless](https://aircrack-ng.blogspot.com/2012/03/compat-wireless.html)
