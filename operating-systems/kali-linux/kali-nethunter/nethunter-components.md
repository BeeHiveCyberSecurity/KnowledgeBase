# NetHunter Components

The NetHunter ROM overlay is composed of several parts that interact and rely on each other for proper operation. These parts include a custom Android Kernel, a Kali Linux Chroot, and a NetHunter Android App.

[Custom Android Kernel](broken-reference)

The custom kernel provides each device with unique features that are not available on stock kernels. All NetHunter kernels provide HID (keyboard to computer support), OTG wireless support, and CDROM emulation support. Also, most kernels also support external SDR/Bluetooth and “y-cable charging”, which allows you to charge your device while using an external device. If you are a power Android user, then you will benefit from the Multirom support in each kernel with the KEXEC patch. Finally, the kernel provides additional patches/fixes to eliminate problems that may be caused by adding external wireless devices.

[Kali Linux chroot](broken-reference)

The Kali Linux chroot is the heart of NetHunter and has specifically modified configuration files to work well with the Android eco-system. You are given two chroot options to download or install: minimal or full. The minimal chroot, which is a little over 100mb in size, is a barebones basic Kali OS with nothing installed and is great for developers or anyone looking to customize their installation. The full chroot is what most users will want to download and comes in around 600mb. The full chroot has everything needed to integrate with the Android application.

[NetHunter Android Application](broken-reference)

The NetHunter application provides a simple interface to manage the Kali Linux chroot and is a simple but powerful GUI. The Android application contains all the configuration files that are copied to the sdcard during the first run. It also acts as a bootup service and will run the services you select when the devices starts. Additionally, the Android application allows you to interact with some preselected applications more easily such as: MANA, MPC, VNC, DuckHunter, HID attacks, and much more. The latest version even includes a custom commands builder, allowing you to easily add/remove your favorite custom commands to NetHunter.
