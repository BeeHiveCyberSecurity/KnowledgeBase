# Kali NetHunter

[**Kali NetHunter is a free & Open-source Mobile Penetration Testing Platform for Android devices, based on Kali Linux.**](broken-reference)

[![](<../../../.gitbook/assets/NetHunter xiaomi mi 9t.png>)](<../../../.gitbook/assets/NetHunter xiaomi mi 9t.png>)

[Content:](broken-reference)

* [Overview](broken-reference)
* [NetHunter Editions](broken-reference)
* [NetHunter Supported Devices and ROMs](broken-reference)
* [Downloading NetHunter](broken-reference)
* [Building NetHunter](broken-reference)
* [Installing NetHunter](broken-reference)
* [Post Installation Setup](broken-reference)
* [Kali NetHunter Attacks and Features](broken-reference)
* [Porting NetHunter to New Devices](broken-reference)
* [Known Working Hardware](broken-reference)
* [NetHunter App](broken-reference)

[Overview](broken-reference)

Kali NetHunter is available for un-rooted devices (NetHunter Rootless), for rooted devices that have a custom recovery (NetHunter Lite), and for rooted devices with custom recovery for which a NetHunter specific kernel is available (NetHunter).

The core of Kali NetHunter, which is included in all three editions, comprises of:

* Kali Linux container that includes all the tools and applications that Kali Linux provides
* Kali NetHunter App Store with dozens of purpose-built security apps
* Android client to access the Kali NetHunter App Store
* Kali NetHunter Desktop Experience (KeX) to run full Kali Linux desktop sessions with support for screen mirroring via HDMI or wireless screen casting

[![](<../../../.gitbook/assets/NetHunter Kex.png>)](<../../../.gitbook/assets/NetHunter Kex.png>)

Figure 2: Kali NetHunter Desktop Experience (KeX) outputting to an HDMI monitor

The Kali NetHunter App Store can be accessed through the dedicated client app or via the web interface.

[![](<../../../.gitbook/assets/nethunter store 02.png>)](<../../../.gitbook/assets/nethunter store 02.png>)

Figure 3: Kali NetHunter App Store

**Both rooted editions provide additional tools & services**. A custom kernel can extend that functionality by adding additional network and USB gadget drivers as well as wifi injection support for selected wifi chips.

[![](<../../../.gitbook/assets/NetHunter App.png>)](<../../../.gitbook/assets/NetHunter App.png>)

Figure 3: The Kali NetHunter App is available in both rooted editions (NetHunter Lite & NetHunter).

Beyond the [penetration testing tools](https://www.kali.org/tools) included in Kali Linux, NetHunter also supports several additional classes, such as **HID Keyboard Attacks**, **BadUSB attacks**, **Evil AP MANA attacks**, and many more.

For more information about the moving parts that make up NetHunter, check out our [NetHunter Components](<../../../.gitbook/assets/nethunter components>) page. Kali NetHunter is an [Open-source project](https://www.kali.org/docs/policy/kali-linux-open-source-policy/) developed by [Offensive Security](https://www.offensive-security.com/) and the community.

[1.0 NetHunter Editions](broken-reference)

NetHunter can be installed on almost every Android device under the sun using one of the following editions:

| Edition            | Usage                                                                 |
| ------------------ | --------------------------------------------------------------------- |
| NetHunter Rootless | The core of NetHunter for unrooted, unmodified devices                |
| NetHunter Lite     | The full NetHunter package for rooted phones without a custom kernel. |
| NetHunter          | The full NetHunter package with custom kernel for supported devices   |

The following table illustrates the differences in functionality:

| Feature            | NetHunter Rootless | NetHunter Lite | NetHunter |
| ------------------ | ------------------ | -------------- | --------- |
| App Store          | Yes                | Yes            | Yes       |
| Kali cli           | Yes                | Yes            | Yes       |
| All Kali packages  | Yes                | Yes            | Yes       |
| KeX                | Yes                | Yes            | Yes       |
| Metasploit w/o DB  | Yes                | Yes            | Yes       |
| Metasploit with DB | No                 | Yes            | Yes       |
| NetHunter App      | No                 | Yes            | Yes       |
| Requires TWRP      | No                 | Yes            | Yes       |
| Requires Root      | No                 | Yes            | Yes       |
| WiFi Injection     | No                 | No             | Yes       |
| HID attacks        | No                 | No             | Yes       |

The installation of NetHunter Rootless is documented here: [NetHunter-Rootless](<../../../.gitbook/assets/nethunter rootless>)

The NetHunter-App specific chapters are only applicable to the NetHunter & NetHunter Lite editions.

The Kernel specific chapters are only applicable to the NetHunter edition.

[2.0 NetHunter Supported Devices and ROMs](broken-reference)

NetHunter Lite can be installed on all Android devices that are rooted and have a custom recovery. The full NetHunter experience requires a devices specific kernel that has been purpose built for Kali NetHunter. The [NetHunter GitLab repository](https://gitlab.com/kalilinux/nethunter/) contains over 164 kernels for over 65 devices. Kali Linux publishes over 25 images for the most popular devices on the [NetHunter download page](https://www.kali.org/get-kali/). The following live reports are generated automatically by GitLab CI:

[List of quarterly published officialNetHunter images](https://nethunter.kali.org/images.html) [List of unofficial NetHunter supported kernels](https://nethunter.kali.org/kernels.html) [NetHunter kernel statistics](https://nethunter.kali.org/kernel-stats.html)

[3.0 Downloading NetHunter](broken-reference)

Official release NetHunter images for your specific supported device can be download from the Kali Linux page located at the following URL:

* [kali.org/get-kali/](https://www.kali.org/get-kali/)

Once the zip file has downloaded, verify the SHA256 sum of the NetHunter zip image against the values on the download page. If the SHA256 sums do not match, do not attempt to continue with the installation procedure.

[4.0 Building NetHunter](broken-reference)

Those of you who want to build a NetHunter image from our Gitlab repository may do so using our Python build scripts. Check out our [Building NetHunter](<../../../.gitbook/assets/building nethunter>) page for more information. You can find additional instructions on using the NetHunter installer builder or adding your own device in the [README](https://gitlab.com/kalilinux/nethunter/build-scripts/kali-nethunter-project/blob/master/nethunter-installer/README.md) located in the [nethunter-installer](https://gitlab.com/kalilinux/nethunter/build-scripts/kali-nethunter-project/blob/master/nethunter-installer) git directory.

[5.0 Installing NetHunter on top of Android](broken-reference)

Now that you’ve either downloaded a NetHunter image or built one yourself, the next steps are to prepare your Android device and then install the image. “Preparing your Android device” includes:

* **unlocking** your device and **updating it to stock** AOSP or LineageOS (CM). (Check point [2.0](broken-reference) for supported roms)
* **installing** [**Team Win Recovery Project**](https://twrp.me/) as a custom recovery.
* **installing** [**Magisk**](https://github.com/topjohnwu/Magisk) to root the device
* disabling force encryption may be required if TWRP cannot access the data partition
* Once you have a custom recovery, all that remains is to flash the NetHunter installer zip file onto your Android device.

[6.0 Post Installation Setup](broken-reference)

* Open the NetHunter App and start the Kali Chroot Manager.
* Install the Hacker Keyboard from the NetHunter Store using the NetHunter Store app.
* Install any other apps from the NetHunter Store as required.
* Configure Kali Services, such as SSH.
* Set up custom commands.
* Initialize the Exploit-Database.

[7.0 Kali NetHunter Attacks and Features](broken-reference)[**Kali NetHunter Application**](broken-reference)

* [**Home Screen**](<../../../.gitbook/assets/nethunter home screen>) - General information panel, network interfaces and HID device status.
* [**Kali Chroot Manager**](<../../../.gitbook/assets/nethunter chroot manager>) - For managing chroot metapackage installations.
* [**Kali Services**](<../../../.gitbook/assets/nethunter kali services>) - Start / stop various chrooted services. Enable or disable them at boot time.
* [**Custom Commands**](<../../../.gitbook/assets/nethunter custom commands>) - Add your own custom commands and functions to the launcher.
* [**MAC Changer**](<../../../.gitbook/assets/nethunter mac changer>) - Change your Wi-Fi MAC address (only on certain devices)
* [**KeX Manager**](<../../../.gitbook/assets/nethunter kex manager>) - Set up an instant VNC session with your Kali chroot.
* [**USB Arsenal**](<../../../.gitbook/assets/nethunter usbarsenal>) - Control the USB gadget configurations
* [**HID Attacks**](<../../../.gitbook/assets/nethunter hid attacks>) - Various HID attacks, Teensy style.
* [**DuckHunter HID**](<../../../.gitbook/assets/nethunter duckhunter>) - Rubber Ducky style HID attacks
* [**BadUSB MITM Attack**](<../../../.gitbook/assets/nethunter badusb>) - Nuff said.
* [**MANA Wireless Toolkit**](<../../../.gitbook/assets/nethunter mana wireless>) - Setup a malicious Access Point at the click of a button.
* [**Bluetooth Arsenal**](<../../../.gitbook/assets/nethunter btarsenal>) - Recon, spoof, listen to or inject audio to various Bluetooth devices.
* [**Social Engineer Toolkit**](<../../../.gitbook/assets/nethunter set>) - Build your own phishing email template for Social Engineer Toolkit.
* [**MITM Framework**](<../../../.gitbook/assets/nethunter mitmf>) - Inject binary backdoors into downloaded executables on the fly.
* [**NMap Scan**](https://www.kali.org/docs/nethunter/nethunter-nmap/) - Quick Nmap scanner interface.
* [**Metasploit Payload Generator**](https://www.kali.org/docs/nethunter/nethunter-mpg/) - Generating Metasploit payloads on the fly.
* [**Searchsploit**](https://www.kali.org/docs/nethunter/nethunter-searchsploit/) - Easy searching for exploits in [Exploit-Database](https://www.exploit-db.com/).

[**3rd Party Android Applications in the NetHunter App Store**](broken-reference)

* [**NetHunter Terminal Application**](https://www.kali.org/docs/nethunter/nethunter-terminal/)

[8.0 Porting NetHunter to New Devices](broken-reference)

If you’re interested in porting NetHunter to other Android devices, check out the following links. If your port works, make sure to tell us about it so we can include these kernels in our releases!

1. [Getting Started manually](https://www.kali.org/docs/nethunter/porting-nethunter/)
2. [Getting Started with kernel builder](https://www.kali.org/docs/nethunter/porting-nethunter-kernel-builder/)
3. [Patching a Kernel](https://www.kali.org/docs/nethunter/nethunter-kernel-1-patching/)
4. [Configuring a Kernel](https://www.kali.org/docs/nethunter/nethunter-kernel-2-config-1/)
5. [Adding Your Device](https://gitlab.com/kalilinux/nethunter/build-scripts/kali-nethunter-devices)

[9.0 Known Working Hardware](broken-reference)

1. [Wireless Cards](https://www.kali.org/docs/nethunter/wireless-cards/)
2. SDR - RTL-SDR (based on RTL2832U)
3. Bluetooth adapters - Sena UD100 or generic CSR4.0 adapter

[10.0 NetHunter Apps](broken-reference)

All apps can be installed through the NetHunter Store client.

[11.0 Useful Links](broken-reference)

1. The NetHunter Store App can be downloaded [here](https://store.nethunter.com/NetHunterStore.apk)
2. The NetHunter Web Store can be found [here](https://store.nethunter.com/)
3. The source code for building the NetHunter Apps can be found on GitLab [here](https://gitlab.com/kalilinux/nethunter/apps/)
