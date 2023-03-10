# Troubleshooting Installations Failures

There can be a wide variety of reasons for a Kali Linux installation to fail. This could include issues such as a corrupt or incomplete ISO download, not enough disk space on the target machine, etc. The following article will give you some pointers on what to look for when your Kali Linux installation has failed. The following is an example of the dreaded “Red Screen”, indicating the installation encountered a problem.

[![](<../../../.gitbook/assets/failed kali install.png>)](<../../../.gitbook/assets/failed kali install.png>)

Hitting the **continue** button should take you to the **Debian installer main menu**. From that main menu, browse to the “**save debug logs**”:

[![](<../../../.gitbook/assets/failed install kali linux 001.png>)](<../../../.gitbook/assets/failed install kali linux 001.png>)

Going into the debug logs, you are presented with several ways of transferring the installation log files away from the failed installation. The most convenient way is usually to start a web server on the machine undergoing the installation.

[![](<../../../.gitbook/assets/failed linux installed transfer method.png>)](<../../../.gitbook/assets/failed linux installed transfer method.png>)

Once you choose this option, a web server is started from which you are able to download or view several installation log files.

[![](<../../../.gitbook/assets/install log download.png>)](<../../../.gitbook/assets/install log download.png>)

Look over the logs files for anything irregular, or any error messages which look like they might be the cause of your failed installation. In this case, the target machine did not have enough disk space to install Kali Linux, as was seen towards the end of the **syslinux** log file

```
Aug 19 23:45:05 base-installer: error: The tar process copying the live system failed (only 152937 out of 286496 files have been copied, last file was ).
Aug 19 23:45:05 main-menu[927]: (process:7553): tar: write error: No space left on device
Aug 19 23:45:05 main-menu[927]: WARNING **: Configuring 'live-installer' failed with error code 1
Aug 19 23:45:05 main-menu[927]: WARNING **: Menu item 'live-installer' failed.
Aug 19 23:50:23 main-menu[927]: INFO: Modifying debconf priority limit from 'high' to 'medium'
Aug 19 23:50:23 debconf: Setting debconf/priority to medium
Aug 19 23:56:49 main-menu[927]: INFO: Menu item 'save-logs' selected
```
