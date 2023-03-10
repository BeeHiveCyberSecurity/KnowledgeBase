# Win-KeX Win

[Content:](broken-reference)

* [Overview](broken-reference)
* [Usage](broken-reference)
  * [Start](broken-reference)
  * [Start Root Session](broken-reference)
  * [Session Management](broken-reference)
  * [Sound Support](broken-reference)
  * [Multiscreen Support](broken-reference)
  * [Stop](broken-reference)

[Overview](broken-reference)[**Win-KeX in Window Mode will run a Kali Linux desktop session in a separate window.**](broken-reference)

Window mode helps keeping the Windows and Kali environments visually apart.

Win-KeX utilises [TigerVNC](https://tigervnc.org/) for its client and server components.

[![](<../../../.gitbook/assets/win kex full.png>)](<../../../.gitbook/assets/win kex full.png>)

[Usage](broken-reference)[Start](broken-reference)

* Start Win-KeX as normal user in window mode via: `kex --win` or simply via `kex`
* **NOTE:** Window mode is the default Win-KeX mode so “–win” can be omitted in all commands on this page.
*   You will be prompted to set a vnc server password during first launch. The password can be changed later via

    `kex --passwd`

    This will start the Win-KeX server and launch the Win-KeX client in full screen mode:

    [![](<../../../.gitbook/assets/win kex.png>)](<../../../.gitbook/assets/win kex.png>)

[Start Root Session](broken-reference)

* Start Win-KeX as root in window mode via: `sudo kex --win`
*   You will be prompted to set a vnc server password during first launch. The password can be changed later via

    `sudo kex --passwd`

    This will start the Win-KeX server as root and launch the Win-KeX client in full screen mode. **Note:** The Win-KeX client always prompts for the vnc server password when connecting to a root session.

[Session Management](broken-reference)

* Pressing “F8” will open the client’s context menu, which allows to manage the client sessions, e.g. close the client, switch between full screen and window, etc.)
* You can disconnect from active sessions by pressing “F8” -> “Exit viewer”, this will close the client but leave the session running in the background
* You can re-connect to a session by typing `kex --win --start-client`

[Sound Support](broken-reference)

* Win-KeX includes pulse audio support
* To start Win-KeX with sound support, add `--sound` or `-s`, e.g. `kex --win -s`
*   When starting Win-KeX with sounds support for the first time, ensure to select

    “**Public networks**”

    when asked for authorisation to allow traffic through the Windows Defender firewall

[![](<../../../.gitbook/assets/win kex pulseaudio\_firewall.png>)](<../../../.gitbook/assets/win kex pulseaudio\_firewall.png>)

[Multiscreen Support](broken-reference)

*   Win-KeX supports mutiscreen setups: Press “F8” an go to “Options” -> “Screen” then untick “Enable full-screen mode over all monitors” & “Full screen mode”, move Win-KeX to the desired screen and re-enable full-screen mode

    [![](<../../../.gitbook/assets/win kex multiscreen.png>)](<../../../.gitbook/assets/win kex multiscreen.png>)

[Stop](broken-reference)

* To close the Win-KeX client, press “F8” and select “Exit viewer”
* To shutdown Win-KeX in window mode, type `kex --win --stop`

[**Enjoy Win-KeX!**](broken-reference)
