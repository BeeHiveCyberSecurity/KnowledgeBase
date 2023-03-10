# Using Kali Linux Podman Images

Podman has very nice documentation on [how to install it](https://podman.io/getting-started/installation) on various systems. We recommend to follow the official documentation, however for a Debian-based system it is a very simple command:

```
:~$ sudo apt update && sudo apt install -y podman
[...]
:~$
```

The Kali images are in the [containers shortnames list](https://github.com/containers/shortnames). This allows the functionality of only calling `kali-rolling`, rather than using the full image name `docker.io/kalilinux/kali-rolling`. This works if the host system provides an up-to-date shortnames list in `/etc/containers/registries.conf.d/shortnames.conf`. As we are using Kali Linux, which does, we can utilize this functionality.

To use the Kali Linux Podman image, we will do the following commands:

```
:~$ podman pull kali-rolling
:~$
:~$ podman run --tty --interactive kali-rolling
┌──(root㉿7df5f0dbe6b7)-[/]
└─#

┌──(root㉿7df5f0dbe6b7)-[/]
└─# exit
:~$
```

Please note, that this does not allow for systemd functionality, which would allow access to items such as `systemctl`.

Please also note, **the images do not come with the “default”** [**metapackage**](https://www.kali.org/docs/general-use/metapackages/). You will need to `apt update && apt -y install kali-linux-headless`.

To resume an exited container we will complete the following:

```
:~$ podman ps -a
CONTAINER ID  IMAGE                                    COMMAND     CREATED        STATUS                   PORTS       NAMES
7df5f0dbe6b7  docker.io/kalilinux/kali-rolling:latest  /bin/bash   2 seconds ago  Exited (0) 1 second ago              cool_tharp
:~$
:~$ podman start 7df5f0dbe6b7
:~$
```

After you execute the following command you will attach to the Podman container, however you must press return once to fully see the prompt:

```
:~$ podman attach 7df5f0dbe6b7

┌──(root㉿7df5f0dbe6b7)-[/]
└─#
```

This will resume the container in whatever state you left it after running the initial `podman run` command or the last `podman start` and `podman attach` sequence.

Finally, if you’re done with the container you can remove it with the following command:

```
:~$ podman rm 7df5f0dbe6b7
7df5f0dbe6b7
:~$
```
