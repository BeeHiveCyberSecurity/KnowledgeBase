# Installing Flatpak on Kali Linux

[**Install Instructions**](broken-reference)

On Kali Linux, `flatpak` can be installed through:

```
:~$ sudo apt update
:~$
:~$ sudo apt install -y flatpak
:~$
:~$ sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

[**GUI software store**](broken-reference)

It is also a good idea to install the Flatpak plugin for GNOME Software. To do this, run:

```
:~$ sudo apt install gnome-software-plugin-flatpak
```

Now you can install new flatpak apps from the software center.

[![](<../../../.gitbook/assets/flatpak store.png>)](<../../../.gitbook/assets/flatpak store.png>)

[**Theme support**](broken-reference)

If you want to make flatpak apps look more consistent with the system you can force them to use your local themes:

```
:~$ mkdir -p ~/.themes
:~$ cp -a /usr/share/themes/* ~/.themes/
:~$ sudo flatpak override --filesystem=~/.themes/
```

[**Reference**](broken-reference)

* [Flatpak](https://flatpak.org/)
* [Debian Quick Setup](https://flatpak.org/setup/Debian/)
