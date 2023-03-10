# Win-KeX SL

[Content:](broken-reference)

* [Overview](broken-reference)
* [Prerequisites](broken-reference)
* [Usage](broken-reference)
  * [Start](broken-reference)
  * [Sound Support](broken-reference)
  * [Multiscreen Support](broken-reference)
  * [Stop](broken-reference)

[Overview](broken-reference)[**Win-KeX in Seamless Mode will launch a Kali Linux panel on the screen top of the Windows desktop.**](broken-reference)

Seamless mode removes the visual segregation between Linux and Window apps and offers a great platform to run a penetration test in Kali Linux and copy the results straight into a Windows app for the final report.

Win-KeX utilises [VcXsrv Windows X Server](https://sourceforge.net/projects/vcxsrv/) to achieve seamless desktop integration.

[![](<../../../.gitbook/assets/win kex sl (1).png>)](<../../../.gitbook/assets/win kex sl (1).png>)

[Prerequisites](broken-reference)

* VcXsrv requires [Visual C++ Redistributable for Visual Studio 2015](https://www.microsoft.com/en-US/download/details.aspx?id=48145) (vcredist140). It should be included in standard Windows installations but if you receive an error complaining that it is missing, just download and install it.

[Usage](broken-reference)[Start](broken-reference)

*   Start Win-KeX as normal user in seamless mode via: `kex --sl`

    When starting Win-KeX SL for the first time, ensure to select

    “**Public networks**”

    when asked for authorisation to allow traffic through the Windows Defender firewall

[![](../../../.gitbook/assets/firewall.png)](../../../.gitbook/assets/firewall.png)

This will start Win-KeX in seamless mode:

[![](<../../../.gitbook/assets/win kex sl (1).png>)](<../../../.gitbook/assets/win kex sl (1).png>)

The Kali panel is placed at the top of the screen and the Windows Start menu at the bottom.

* **Tip:** The Kali panel might cover the title bar of maximised windows. To prevent it getting in the way you may prefer to set it to “Automatically hide” in the panel preferences.

[Sound Support](broken-reference)

* Win-KeX includes pulse audio support
* To start Win-KeX with sound support, add `--sound` or `-s`, e.g. `kex --win -s`
* When starting Win-KeX with sounds support for the first time, ensure to select

“**Public networks**”

when asked for authorization to allow traffic through the Windows Defender firewall

[![](<../../../.gitbook/assets/win kex pulseaudio\_firewall (1).png>)](<../../../.gitbook/assets/win kex pulseaudio\_firewall (1).png>)

[Multiscreen Support](broken-reference)

*   Win-KeX supports multiscreen setups:

    Open “Panel Preference” to reduce the panel length, untick “Lock panel” and move the panel to the desired screen.

[Stop](broken-reference)

* To close Win-KeX SL, simply log out of the session via the “Logout” button in the panel.
* To optionally shutdown the Win-KeX SL server, type `kex --sl --stop`

[**Enjoy Win-KeX!**](broken-reference)
