# How to upgrade to Linux Mint 21

This page explains how to upgrade from Linux Mint 20.3 to Linux Mint 21.

First, refresh your cache and install the Upgrade Tool by typing the following commands in a terminal:

```
apt update
apt install mintupgrade
```

Then type the following command to launch the Upgrade Tool:

![\_images/upgrade21-mintupgrade.png](<../../../.gitbook/assets/upgrade21 mintupgrade.png>)

Follow the instructions on the screen.

When the tool is done and the upgrade is successful uninstall it and reboot your computer.

```
apt remove mintupgrade
sudo reboot
```

This is a major upgrade. It can take several hours.

You will be asked to be up to date and to prepare system snapshots. Do not rush, do not take shortcuts.

Don’t hesitate to seek help if you have questions or if you face problems with the upgrade.

### Troubleshooting[¶](broken-reference)

#### Installing mintupgrade[¶](broken-reference)

If you can’t find _mintupgrade_ in the repositories, switch to the default Linux Mint mirror and refresh the APT cache.

#### Repairing boot[¶](broken-reference)

If the computer no longer boots, boot from the live Linux Mint 21 ISO.

From the live session, launch _Boot Repair_ and use it to fix the boot sequence.

If this doesn’t work, boot from the live Linux Mint ISO again, and launch _Timeshift_.

Timeshift is able to scan your drives from the live session and restore your snapshot from there.

### Notes[¶](broken-reference)

The upgrade overwrites files in _/etc/_ with default configuration files. You can restore files indivually by the Timeshift snapshot you made prior to upgrading.

To restore your lightDM settings, run the Login Window configuration tool (**sudo lightdm-settings**).
