# Where

The Linux Mint operating system is made up of thousands of software components. Once you’ve identified the component responsible for your issue, you need to identify who’s maintaining it.

### Mint and upstream components[¶](broken-reference)

There are two types of components within Linux Mint:

* Mint components are maintained or patched by Linux Mint.
* Upstream components are maintained by Ubuntu (or Debian in the case of LMDE).

You can use the terminal to get information about a particular component.

Use `apt contains` to find the name of the package containing a particular file.

For instance, if you are chasing an issue in the file `/usr/share/polkit-1/actions/org.gnome.gnome-system-monitor.policy`, you can type:

```
apt contains /usr/share/polkit-1/actions/org.gnome.gnome-system-monitor.policy

gnome-system-monitor: /usr/share/polkit-1/actions/org.gnome.gnome-system-monitor.policy
```

The output tells you that this file is part of the `gnome-system-monitor` package.

Once you know the name of the package, you can use `apt policy` to see who’s maintaining it:

```
apt policy gnome-system-monitor

gnome-system-monitor:
  Installed: 3.18.2-1ubuntu1
  Candidate: 3.18.2-1ubuntu1
  Version table:
 *** 3.18.2-1ubuntu1 500
        500 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 Packages
        100 /var/lib/dpkg/status
     3.18.2-1 500
        500 http://archive.ubuntu.com/ubuntu xenial/main amd64 Packages
```

As you can see above, gnome-system-monitor comes from the Ubuntu repositories and is therefore an upstream component. Bugs related to it should be reported to Ubuntu.

Here’s another example:

```
apt policy gnome-calculator

gnome-calculator:
  Installed: 1:3.18.3-0ubuntu1.16.04.1.mint1
  Candidate: 1:3.18.3-0ubuntu1.16.04.1.mint1
  Version table:
 *** 1:3.18.3-0ubuntu1.16.04.1.mint1 700
        700 http://packages.linuxmint.com sylvia/upstream amd64 Packages
        100 /var/lib/dpkg/status
     1:3.18.3-0ubuntu1.16.04.1 500
        500 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 Packages
     1:3.18.3-0ubuntu1 500
        500 http://archive.ubuntu.com/ubuntu xenial/main amd64 Packages
```

This time we’re looking at gnome-calculator. As you can see above, Linux Mint provides version 1:3.18.3-0ubuntu1.16.04.1.mint1, and that’s the version which is installed. In this example, our version of gnome-calculator is therefore a Mint component and bugs related to it should be reported to Linux Mint.

### Upstream bugs: Launchpad and Debbugs[¶](broken-reference)

If the bug relates to an Ubuntu component, it should be reported on [Launchpad](https://bugs.launchpad.net/).

If the bug relates to a Debian component, it should be reported on [Debian’s bug tracking system](https://www.debian.org/Bugs/).

Important

Before reporting upstream bugs to Ubuntu and/or Debian, you should always make sure the issue can be reproduced in Ubuntu and/or Debian. Install Ubuntu (or Debian) in a virtual machine and try to reproduce the issue. If the issue is specific to Linux Mint, it should be reported to Linux Mint directly (whether the component is upstream or not).

### MATE bugs: Github/mate-desktop[¶](broken-reference)

MATE is co-developed by Linux Mint.

Bugs which affect MATE or one of its components should be reported on the [MATE Github site](https://github.com/mate-desktop).

One exception to this are bugs which are specific to Linux Mint. For instance, if a bug relates to mintmenu, mintdesktop or a mint theme in MATE, please report it to Linux Mint directly.

### Cinnamon, X-Apps and Linux Mint bugs[¶](broken-reference)

Linux Mint has three development teams:

* The Cinnamon development team maintains all Cinnamon components, including nemo and muffin.
* The X-App development teams maintains all cross-distribution projects such as the X-App applications (pix, xed, xreader, xplayer, xviewer), libraries, and slick-greeter, blueberry, etc.
* The Linux Mint development team maintains all the Mint tools and other components distributed via the Mint repositories.

When reporting a bug to one of these teams, try to find the component on the [Linux Mint Github site](http://github.com/linuxmint).

For instance, a nemo bug should be reported on [Nemo](http://github.com/linuxmint/nemo), a mintmenu bug should be reported on [Mintmenu](http://github.com/linuxmint/mintmenu), an xplayer bug on [Xplayer](http://github.com/linuxmint/xplayer), etc.

If you want to report a general issue about Cinnamon, you can use [Cinnamon](http://github.com/linuxmint/Cinnamon).

If you want to report a general issue about Linux Mint, an issue about an upstream component which is patched by Linux Mint, or an issue about an upstream component which is specific to Linux Mint, you can use [Linux Mint](http://github.com/linuxmint/linuxmint).
