# Installing NetHunter On the OnePlus 7

[![](https://www.kali.org/docs/nethunter/installing-nethunter-on-the-oneplus-7/one-plus-7p.png)](https://www.kali.org/docs/nethunter/installing-nethunter-on-the-oneplus-7/one-plus-7p.png)

### From a reset to running NetHunter in 4 steps: <a href="#from-a-reset-to-running-nethunter-in-4-steps" id="from-a-reset-to-running-nethunter-in-4-steps"></a>

1. Flash latest Android 10 with the unbrick tool
2. Flash TWRP and Magisk
3. Disable force encryption of data partition
4. Install NetHunter
5. Disable OnePlus update service

[1. Flash latest stock (OOS) Android 10](broken-reference)

1.01. Download and unzip [guacamoleb\_14\_P.32\_210127.zip](https://build.nethunter.com/contributors/re4son/guacamole/guacamoleb\_14\_P.32\_210127.zip) on your Windows computer\
1.02 Open admin cmd and type: “bcdedit /set testsigning on”, reboot\
1.03 Run MsmDownloadTool V4.0.exe\
1.04 Power off OnePlus 7, press vol + & vol - at the same time, count to 5 and connect phone to laptop\
1.05 When device is detected (bing) press start\
1.06 reboot and set up device\
1.07 In developer options, enable OEM unlock & USB debugging\
1.08 sudo apt install adb\
1.09 adb kill-server && ./adb start-server\
1.10 adb reboot bootloader\
1.11 sudo fastboot oem unlock\
1.12 Reboot and set up phone

[2. Flash TWRP and Magisk](broken-reference)

2.01 Copy to Oneplus7\
2.02 Download [https://github.com/topjohnwu/Magisk/releases/download/v19.3/Magisk-v19.3.zip](https://github.com/topjohnwu/Magisk/releases/download/v19.3/Magisk-v19.3.zip) to Oneplus7\
2.03 Download [https://dl.twrp.me/guacamoleb/twrp-3.3.1-1-guacamoleb.img.html](https://dl.twrp.me/guacamoleb/twrp-3.3.1-1-guacamoleb.img.html) to your PC\
2.04 Install Android platform tools\
2.05 In developer options of your phone, enable USB debugging\
2.06 adb kill-server && ./adb start-server\
2.07 adb reboot bootloader\
2.08 sudo fastboot boot twrp-3.3.1-1-guacamoleb.img\
2.09 Device automatically reboots into trwp\
2.10 In twrp, install twrp-installer-3.3.1-1-guacamoleb.zip & Magisk-v19.3.zip, reboot\
2.11 Reboot

[3. Disable force ecryption of data partition](broken-reference)

3.01 Reboot into recovery\
3.02 format /data\
3.03 reboot into recovery\
3.04 install magisk\
3.05 install Disable\_Dm-Verity\_ForceEncrypt\_11.02.2020.zip\
3.06 reboot to system\
3.07 set up phone but skip fingerprint or any other security. Set up later (not sure if that re-encrypts the phone)

[4. Install NetHunter](broken-reference)

4.01 Download image from [our download page](https://www.kali.org/get-kali/#kali-mobile)\
4.02 there is a bug in the current installer requiring to install the kernel separately, [download it here](https://build.nethunter.com/contributors/re4son/guacamole/kernel-nethunter-2021.3-oneplus7-oos-ten.zip)\
4.03 reboot into recovery\
4.04 install nethunter zip\
4.06 install magisk again\
4.07 install disable-force-encrypter again\
4.08 reboot\
4.09 run NetHunter app, wait for the initial setup to finish then reboot\
4.10 update NetHunter app from store

[5. Disable OnePlus update service](broken-reference)

5.01 Open Android terminal as root\
5.02 su -c pm disable com.oneplus.opbackup\
5.03 “System Update” service is now disabled

[Enjoy Kali NetHunter on the OnePlus 7](broken-reference)

Please help with the development by submitting issues and pull requests. We much appreciate it.
