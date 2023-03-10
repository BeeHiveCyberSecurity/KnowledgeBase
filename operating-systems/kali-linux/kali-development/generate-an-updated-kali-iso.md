# Generate an Updated Kali ISO

Kali Linux allows you to generate updated ISOs of Kali using Debian [live-build](http://live.debian.net/devel/live-build/) scripts on the fly. The easiest way to generate these images is **from within a pre existing Kali Linux environment**. You will first need to install the `live-build` and `cdebootstrap` packages:

```
:~$ sudo apt update
:~$ sudo apt install -y git live-build cdebootstrap
```

Next, we clone the Kali `cdimage` Git repository as follows:

```
:~$ git clone git://gitlab.com/kalilinux/build-scripts/live-build-config.git
```

Now you can change to the `live` directory under `cdimage.kali.org` and build your ISO:

```
:~$ cd live-build-config/
:~$ lb clean --purge
:~$ lb config
:~$ lb build
```

The live build scripts allow for complete customization of Kali Linux images. For more information about Kali live build scripts, check out our [Kali customization page](broken-reference).
