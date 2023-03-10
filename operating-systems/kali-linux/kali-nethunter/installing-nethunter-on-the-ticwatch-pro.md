# Installing NetHunter On the TicWatch Pro

[![](https://www.kali.org/docs/nethunter/installing-nethunter-on-the-ticwatch-pro/NetHunter-TicWatch.png)](https://www.kali.org/docs/nethunter/installing-nethunter-on-the-ticwatch-pro/NetHunter-TicWatch.png)

All variants are supported (TicWatch Pro, Pro 2020, Pro 4G/LTE)

### From unpacking to running NetHunter in 6 steps: <a href="#from-unpacking-to-running-nethunter-in-6-steps" id="from-unpacking-to-running-nethunter-in-6-steps"></a>

1. Unlock the bootloader
2. Flash vendor image, TWRP, and optimized WearOS
3. Resize system partition in TWRP
4. Flash and launch Magisk app to finish the rooting process
5. Flash NetHunter
6. Set NetHunter watch face

[1. Unlock the bootloader](broken-reference)

* Connect your watch to your PC with it’s USB cable, and fire up a terminal.
* If you have set up your watch on the phone you can access settings, otherwise hold both buttons for a few seconds on the welcome screen.
* Enable developer settings by going to System -> About -> tap Build number 10 times
* Enable ADB, re-plug USB and accept debug from PC
* Reboot into bootloader with `adb reboot bootloader` from the terminal
* Unlock bootloader with `fastboot flashing unlock`

[2. Flash vendor image, TWRP, and optimized WearOS](broken-reference)

Download and extract the installation files into a folder. Please note Magisk 21.0 is recommended, included in the following link.

Download link for ROM, vendor, TWRP, and Magisk: [https://build.nethunter.com/contributors/re4son/catfish/](https://build.nethunter.com/contributors/re4son/catfish/)

* Again enable ADB, and reboot to bootloader with `adb reboot bootloader`
* `fastboot flash vendor vendor.img`
* `fastboot flash recovery twrp-3.4.0-0-catfish.img`
* Boot into recovery by selecting it with the side buttons (switch with bottom one, select with upper button)
* Select “Wipe -> next page -> Format Data”
* Reboot to Recovery
* Select “Install -> ADB Sideload” and tick “Wipe Dalvik Cache, Wipe Cache”
* `adb sideload 2-ROM-PWDD.190617.074-AUG-09.zip`
* Reboot & do initial setup (pair with your phone through WearOS app)

[3. Resize system partition in TWRP](broken-reference)

* Again enable ADB
* `adb reboot recovery`
* Select Wipe -> next page -> File System Options - select System - Resize (to have \~175MB free on /system instead of 0)

[4. Flash and launch Magisk app to finish the rooting process](broken-reference)

* `adb sideload Magisk-v21.0.zip`
* Reboot to System
* Launch Magisk Manager
* You might want to disable auto-update, set grant access in auto response, and disable toast notifications for easier navigation in the future

[5. Flash NetHunter](broken-reference)

* `adb reboot recovery`
* Make sure that the system partition is mounted: Mount -> System (make sure that “mount as RO” is disabled), some users report /system is not being mounted by NetHunter installer
* Select Install -> ADB Sideload
* `adb sideload` NetHunter image
* Reboot
* Start NetHunter app & chroot
* Reboot

[6. Set NetHunter watch face](broken-reference)

* Install Facer onto your phone from Play Store
* Search for NetHunter
* Install Facer companion app to watch
* Select & Sync

[Enjoy Kali NetHunter on the TicWatch Pro](broken-reference)[Download link](broken-reference)

[https://build.nethunter.com/contributors/re4son/catfish/nethunter-2022.2b-ticwatchpro-wearos-kalifs-nano.zip](https://build.nethunter.com/contributors/re4son/catfish/nethunter-2022.2b-ticwatchpro-wearos-kalifs-nano.zip)

[Additional supported apps](broken-reference)

* Drivedroid: use `adb install` to install the latest version Download link: [https://store.nethunter.com/repo/com.softwarebakery.drivedroid\_105000.apk](https://store.nethunter.com/repo/com.softwarebakery.drivedroid\_105000.apk)
* TotalCommander: useful for selecting eg. a Ducky script, use `adb install` method Download link: [https://www.totalcommander.ch/android/tcandroid323-armeabi.apk](https://www.totalcommander.ch/android/tcandroid323-armeabi.apk)

[Supported features](broken-reference)

* Kali services
* Custom Commands
* MAC Changer
* HID Attacks
* DuckHunter
* Bad USB
* Nmap Scan
* WPS Attacks

[Upcoming features (not guaranteed)](broken-reference)

* Nexmon, as the chipset is supported, needs some time
* Bluetooth Arsenal (internal bluetooth via blueblinder, as carwhisperer fails to r/w when SCO channel is connected)
* Router Keygen (to be optimised)
* Hijacker (if nexmon succeeds)
* Mifare Classic Tool (need to build OS with android.hardware.nfc enabled)

[Hardware limitations](broken-reference)

* Power resource is not enough for any external adapters
