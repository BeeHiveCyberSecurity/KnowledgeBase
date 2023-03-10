# Win-KeX ESM

[Content:](broken-reference)

* [Overview](broken-reference)
* [Usage](broken-reference)
  * [Start](broken-reference)
  * [Start Root Session](broken-reference)
  * [Session Management](broken-reference)
  * [Stop](broken-reference)

[Overview](broken-reference)[**Win-KeX in Enhanced Session Mode will run a Kali Linux desktop session in a separate window using protocols and clients native to Windows. ESM mode is the only supported mode on arm devices.**](broken-reference)

ESM mode helps to keep the Windows and Kali environments visually apart.

Win-KeX utilises [xrdp](http://xrdp.org/) server and Microsoft’s native RDP client.

Using the native Microsoft client might yield a crispier GUI on HiDPI devices. The downside is that it is not as fast as –win or –sl modes to the increased pixel density.

[![](<../../../.gitbook/assets/win kex esm arm.png>)](<../../../.gitbook/assets/win kex esm arm.png>)

[Usage](broken-reference)[Start](broken-reference)

* Start Win-KeX as normal user in ESM mode with sound via: `kex --esm --sound`
* **Note:** As of the time of this writing, Windows on Arm contains a bug causing massive packet loss when using “localhost” instead of the IP address to connect to the kali container. As a workaround, use the “–ip” command line switch on arm devices, i.e.: `kex --esm --ip --sound` The disadvantage of using “–ip” is that you have to re-enter the ESM password each time you reboot the machine, as the credentials are stored using the sessions name, which changes after every reboot. Once Microsoft fixes the bug, we can drop the “–ip” and live happily ever after without having to type in the password again.
* **NOTE:** ESM mode is the default Win-KeX mode on arm devices so “–esm” can be omitted in all commands on this page if you are running Windows on Arm.
*   You will be prompted to set an rdp server password during first launch. This is the password of the kali user you would like to login with. The password is store in the Windows credential store and can be changed later via

    `kex --esm --passwd`

    Tick “Don’t ask me again” and confirm the following warnings:

[![](<../../../.gitbook/assets/RDP Message 1.png>)](<../../../.gitbook/assets/RDP Message 1.png>)

This will start the Win-KeX server and launch the Win-KeX client in full screen mode:

[![](<../../../.gitbook/assets/win kex (1).png>)](<../../../.gitbook/assets/win kex (1).png>)

[Start Root Session](broken-reference)

* Start Win-KeX as root in window mode via: \`sudo kex –esm
*   You will be prompted to set an ESM server password during first launch. This is the password for the kali root user. The password can be changed later via

    `sudo kex --esm --passwd`

    This will start the Win-KeX server as root and launch the Win-KeX client in full screen mode.

[Session Management](broken-reference)

* You can disconnect from active sessions by closing the RDP client; this will close the client but leave the session running in the background
* You can re-connect to a session by typing `kex --esm --start-client`

[Sound Support](broken-reference)

* Win-KeX includes pulse audio support
* To start Win-KeX with sound support, add `--sound` or `-s`, e.g. `kex --esm --sound`

[Stop](broken-reference)

*   To close the Win-KeX client, log out of the Kali GUI session

    [![](<../../../.gitbook/assets/win kex 2 (1).png>)](<../../../.gitbook/assets/win kex 2 (1).png>)
* To shutdown Win-KeX in ESM mode, type `kex --esm --stop`

[**Enjoy Win-KeX!**](broken-reference)
