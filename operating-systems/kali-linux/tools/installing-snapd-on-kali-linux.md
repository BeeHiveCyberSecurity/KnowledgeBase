# Installing snapd on Kali Linux

[**Install Instructions**](broken-reference)

On Kali Linux, `snap` can be installed through:

```
:~$ sudo apt update
:~$
:~$ sudo apt install -y snapd
:~$
```

Enabling and starting `snapd` and `snapd.apparmor` services:

```
:~$ sudo systemctl enable --now snapd apparmor
```

Log out and back in again, or restart your system, to ensure snap’s paths are updated correctly.

[**Reference**](broken-reference)

* [Installing snap on Kali Linux](https://snapcraft.io/docs/installing-snap-on-kali)
