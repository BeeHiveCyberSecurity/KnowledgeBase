# Installing NetHunter On the TicWatch Pro 3

[![](https://www.kali.org/docs/nethunter/installing-nethunter-on-the-ticwatch-pro3/NetHunter-TicWatchPro3.png)](https://www.kali.org/docs/nethunter/installing-nethunter-on-the-ticwatch-pro3/NetHunter-TicWatchPro3.png)

All variants are supported (TicWatch Pro 3 GPS/LTE/Ultra GPS/Ultra LTE) with a generic installer as of now.

### From unpacking to running NetHunter in 5 steps: <a href="#from-unpacking-to-running-nethunter-in-5-steps" id="from-unpacking-to-running-nethunter-in-5-steps"></a>

1. Unlock the bootloader
2. Flash TWRP, WearOS image, Magisk, dm-verity disabler
3. Finalise Magisk app to finish the rooting process
4. Install NetHunter
5. Set NetHunter watch face

[1. Unlock the bootloader](broken-reference)

* Connect your watch to your PC with a DIY USB cable or a [3D printed data dock](https://social.thangs.com/m/59021), and fire up a terminal.
* If you have set up your watch on the phone you can access settings, otherwise hold both buttons for a few seconds on the welcome screen.
* Enable developer settings by going to System -> About -> tap Build number 10 times
* Enable ADB, re-plug USB and accept debug from PC
* Reboot into bootloader with `adb reboot bootloader` from the terminal
* Unlock bootloader with `fastboot oem unlock`

[2. Flash TWRP, WearOS image, Magisk, dm-verity disabler](broken-reference)

Please note that Magisk 24.3 is recommended.

* Again enable ADB, and reboot to bootloader with `adb reboot bootloader`
* Disable vbmeta verification: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img`
* Flash recovery `fastboot flash recovery recovery.img`
* Boot into recovery by selecting it with the side buttons (switch with bottom one, select with upper button)
* Select Wipe -> Advanced Wipe -> select Format Data
* Reboot to recovery
* Select “Install -> ADB Sideload” If you want OneOS:
* Flash OneOS with `adb sideload`
* Flash Mobvoi Apps package with `adb sideload`
* If you have an Ultra, `adb sideload` the Ultra addon package (TWRP-OEM\_FOR\_TICWATCH\_PRO\_3\_ULTRA\_x) If you want to keep stock WearOS, continue from here.
* Make a copy of your Magisk apk file to Magisk-v24.3.zip
* Flash Magisk with `adb sideload Magisk-v24.3.zip`
* Flash DM-Verity\_ForceEncrpyt Disabler with `adb push disabler.zip /sdcard/` and Install via TWRP
* Reboot & do initial setup (pair with your phone through WearOS app)

[3. Finalise Magisk app to finish the rooting process](broken-reference)

* Enable ADB again
* Finalise Magisk installation with app install `adb install Magisk-v24.3.apk`
* Launch Magisk Manager
* You might want to disable auto-update, set grant access in auto response, and disable toast notifications for easier navigation in the future

[4. Install NetHunter](broken-reference)

* Reboot to recovery
* Select Install -> ADB Sideload
* Flash NetHunter image with `adb sideload`
* Reboot
* Start NetHunter app & chroot
* Reboot

[5. Set NetHunter watch face](broken-reference)

* Install Facer onto your phone and watch from Play Store
* Search for NetHunter
* Select & Sync
* Set density so NetHunter app menu buttons will be reachable on OneOS `adb shell wm density 300`

[Enjoy Kali NetHunter on the TicWatch Pro 3](broken-reference)[Downloads](broken-reference)

* [Magisk](https://build.nethunter.com/contributors/re4son/catfish/TicWatch-Pro-3-files/Magisk-v24.3.apk)
* [TWRP image for rover](https://build.nethunter.com/contributors/re4son/catfish/TicWatch-Pro-3-files/rover\_recovery.img)
* [TWRP image for rubyfish](https://build.nethunter.com/contributors/re4son/catfish/TicWatch-Pro-3-files/rubyfish\_recovery.img)
* [OneOS, Stock ROMs and Mobvoi packages](https://build.nethunter.com/contributors/re4son/catfish/TicWatch-Pro-3-files/OS) (not required if you want to stick with stock Wear OS)
* [vbmeta image](https://build.nethunter.com/contributors/re4son/catfish/TicWatch-Pro-3-files/vbmeta.img)
* [dm-verity disabler](https://build.nethunter.com/contributors/re4son/catfish/TicWatch-Pro-3-files/Disable-DM-Verity\_ForceEncrypt.zip)
* [WearOS NetHunter zip](https://build.nethunter.com/contributors/re4son/catfish/nethunter-2022.2b-generic-armhf-kalifs-nano.zip)

[Additional recommended apps](broken-reference)

* TotalCommander: useful for selecting eg. a Ducky script, use “adb install” method Download link: [https://www.totalcommander.ch/android/tcandroid323-armeabi.apk](https://www.totalcommander.ch/android/tcandroid323-armeabi.apk)

[Supported features](broken-reference)

* Kali services
* Custom Commands
* MAC Changer
* HID Attacks
* DuckHunter
* Nmap Scan
* WPS Attacks

[Upcoming features (not guaranteed)](broken-reference)

* Nexmon, as the chipset is supported, needs some time
* Bluetooth Arsenal (internal bluetooth via blueblinder, as carwhisperer fails to r/w when SCO channel is connected)
* Router Keygen (to be optimised)
* Hijacker (if nexmon succeeds)
* Mifare Classic Tool (need to build OS with android.hardware.nfc enabled)

[Hardware limitations](broken-reference)

* Power resource is not enough for any external adapters, although this kernel might support Y cable in the future!
