# Cinnamon

The Cinnamon desktop environment is a very large development project.

Between 2006 and 2010 the main desktop environment for Linux Mint was GNOME 2. It was very stable and very popular.

In 2011, Linux Mint 12 was unable to ship with GNOME 2. The upstream GNOME team had released a brand new desktop (GNOME 3 aka “Gnome Shell”) which was using new technologies (Clutter, GTK3), which had a completely different design and implemented a radically different paradigm than its predecessor but which used the same namespaces and thus it couldn’t be installed alongside GNOME 2. Following the decision from Debian to upgrade GNOME to version 3, GNOME 2 was no longer available in Linux Mint.

To tackle this issue two new projects were started:

* A project called “MATE” was started by a developer called Perberos. Its goal was to rename and repackage GNOME 2 so that it could be just as it was before.
* A project called “MGSE” was started by Linux Mint. Its goal was to develop extensions for GNOME 3 to give it back some of the functionality it had lost and which was available in GNOME 2 (a panel, a systray, an application menu, a window-centric alt-tab selector, a window-list..etc).

Linux Mint 12 shipped with both MATE and GNOME3+MGSE.

6 months later and after a huge amount of work, MATE was becoming stable, and from a set of extensions MGSE became a fork of GNOME 3 called Cinnamon.

Linux Mint 13 was the first Linux release to ship with the Cinnamon desktop. Since then Linux Mint has a MATE and a Cinnamon edition, both providing users with a conservative desktop paradigm, one forked from GNOME 2 and the other forked and derived from GNOME 3.

### Processes

[![\_images/cinnamon-design.svg](https://linuxmint-developer-guide.readthedocs.io/en/latest/\_images/cinnamon-design.svg)](https://linuxmint-developer-guide.readthedocs.io/en/latest/\_images/cinnamon-design.svg)

Binary view of the various processes within a Cinnamon session

The figure above shows the various processes at play within a Cinnamon session.

After you log in, the following processes are automatically started:

* cinnamon-session (the session manager which starts all the other processes)
* cinnamon (which is the visual part of the cinnamon desktop)
* nemo-desktop (which handles the desktop icons and desktop context menu)
* cinnamon-screensaver (the screensaver)
* various csd-\* processes (which are settings daemon plugins and run in the background)

The nemo process starts when you browse files and directories. It remains open as long as at least one file manager window is open.

The cinnamon-settings process starts when you launch the _System Settings_ and remains open as long as at least one configuration module is open.

### Libraries

#### cinnamon-menus

The _cinnamon-menus_ library provides utility functions to read and monitor the set of desktop applications installed on the computer. Thanks to _cinnamon-menus_, Cinnamon can quickly list installed applications within the application menu, fetch application icons for the menu, the alt-tab selector and the window-list and keep this data in sync whenever applications are installed or removed from the computer.

The cinnamon-menus library is developed in C and the source code is available on [Github](https://github.com/linuxmint/cinnamon-menus).

#### cinnamon-desktop

_cinnamon-desktop_ is a set of utility libraries and settings used by other Cinnamon components.

Whenever multiple desktop components need to access the same resource (whether this is a setting or a utility function), we place this resource in cinnamon-desktop.

Here’s an overview of some of the resources currently in _cinnamon-desktop_:

| cinnamon.desktop | dconf settings schemas used by several Cinnamon components                |
| ---------------- | ------------------------------------------------------------------------- |
| libcvc           | A PulseAudio utility library used to control sound volume and devices     |
| gnomerr          | An Xrandr utility library to detect, load and save monitor configurations |
| gnome-xkb        | A keyboard layout utility library                                         |
| gnome-bg         | A wallpaper utility library                                               |
| gnome-installer  | A cross-distribution library used to install software applications        |

The cinnamon-desktop library is developed in C and the source code is available on [Github](https://github.com/linuxmint/cinnamon-desktop).

#### muffin

Muffin, or _libmuffin_ to be more precise is a window management library.

Within the Cinnamon desktop environment, the Window Manager isn’t running in a separate process. The main _cinnamon_ process implements the _libmuffin_ library and therefore runs both the visible components (panel, applets..etc) and the window manager.

Note

The _muffin_ package also provides a _muffin_ binary. This binary is a small program which implements _libmuffin_ and provides a minimal window manager, sometimes used by the developers as a troubleshooting tool. Note that whether or not _muffin_ is installed by default in Linux Mint, it doesn’t run by default in a Cinnamon session. The _cinnamon_ process, which also implements _libmuffin_, is the default window manager.

The clutter and cogl libraries are also part of the muffin package now. Clutter is a library for creating and displaying both 2d and 3d graphical elements. It is used both by muffin itself (eg. for compositing and setting up the stage), and also by St in cinnamon (all St widgets are clutter actors). Cogl is a library that clutter uses for 3d rendering.

Muffin is developed in C and the source code is available on [Github](https://github.com/linuxmint/muffin).

#### cjs

CJS is Cinnamon’s Javascript interpreter. It uses MozJS (Mozilla’s [SpiderMonkey](https://spidermonkey.dev/)) and makes it possible to work with GObject and interact with GIR, GNOME and Cinnamon libraries using that language.

CJS is run by and within the main _cinnamon_ process and the parts of the desktop written in Javascript are contained in the main Cinnamon component.

CJS is developed in C++ and Javascript and the source code is available on [Github](https://github.com/linuxmint/cjs).

### Core components

#### cinnamon-session

The Cinnamon session manager is responsible for launching all the components needed by the session after you log in, and closing the session properly when you want to log out.

Among other things, the session manager launches the core components required by the session (such as the desktop itself and its components), as well as applications which are configured to start automatically.

Cinnamon-session also provides a DBus interface called the Presence interface, which makes it easy for applications such as media players to set the sessions as busy and inhibit power management (suspend, hibernate, etc…) and the screensaver during video playback.

Last but not least, the session management lets applications register so they can be closed cleanly. The text editor for instance is registered to the session when launched and interacts with it on logout. If a document isn’t saved, the session is aware of it and lets you save your work before proceeding to log out.

#### cinnamon-settings-daemon

_cinnamon-settings-daemon_ is a collection of processes which run in the background during your Cinnamon session.

Here’s a description of some of these processes.

| csd-automount           | Automatically mounts hardware devices when they are plugged in                  |
| ----------------------- | ------------------------------------------------------------------------------- |
| csd-clipboard           | Manages the additional copy-paste buffer available via Ctrl+C/Ctrl+V            |
| csd-housekeeping        | Handles the thumbnail cache and keeps an eye on the space available on the disk |
| csd-keyboard            | Handles keyboard layouts and configuration                                      |
| csd-media-keys          | Handles media keys                                                              |
| csd-mouse               | Handles mice and touch devices                                                  |
| csd-orientation         | Handles accelerometers and screen orientation                                   |
| csd-power               | Handles battery and power management                                            |
| csd-print-notifications | Handles printer notifications                                                   |
| csd-wacom               | Handles wacom devices                                                           |
| csd-xrandr              | Handles screen resolution and monitors configuration                            |
| csd-xsettings           | Handles X11 and GTK configuration                                               |

Cinnamon-settings-daemon is developed in C and the source code is available on [Github](https://github.com/linuxmint/cinnamon-settings-daemon).

### Visible desktop layer

#### cinnamon-screensaver

The Cinnamon screensaver is responsible for locking the screen and to a lesser extent for handling some power management functions (although most of these are handled by csd-power within the Cinnamon Settings Daemon).

Cinnamon-screensaver is developed in Python and the source code is available on [Github](https://github.com/linuxmint/cinnamon-screensaver).

#### cinnamon

The Cinnamon github project is the biggest and most active project within the overall project.

It contains various subcomponents written in C:

| St      | Cinnamon’s widget toolkit written on top of Clutter                                            |
| ------- | ---------------------------------------------------------------------------------------------- |
| Appsys  | An abstraction of Gio.AppInfo and cinnamon-menus, providing metadata on installed applications |
| DocInfo | An abstraction of recently opened documents                                                    |
| Tray    | A small library for managing status icons                                                      |

The visible layer of the desktop is written in Javascript:

| Cinnamon JS | The panels, window management, HUD, effects and most of what you see… |
| ----------- | --------------------------------------------------------------------- |
| Applets     | The applets within the panel                                          |
| Desklets    | The desklets on top of the desktop                                    |

The System Settings, its configuration modules and utility scripts are written in Python.

Cinnamon is developed in C, Python and Javascript and the source code is available on [Github](https://github.com/linuxmint/cinnamon).

#### nemo

Nemo is Cinnamon’s file manager. When you open up your home directory or browse files you’re running Nemo.

Another little part of Nemo is _nemo-desktop_. Its role is to handle desktop icons and the desktop context menu.

When you log in, _nemo-desktop_ is started automatically by cinnamon-session. The _nemo_ process itself only starts when you’re browsing through the directories and stops when you close the last opened file manager window.

Nemo is developed in C and the source code is available on [Github](https://github.com/linuxmint/nemo).

#### nemo-extensions

Nemo provides a set of APIs and is very easy to extend, both in C and in Python. _nemo-extensions_ is the Github project where common extensions are stored.

Some Nemo extensions are developed in C and some in Python. Their source code is available on [Github](https://github.com/linuxmint/nemo-extensions).

#### cinnamon-control-center

Although _cinnamon-settings_ (which is part of the Cinnamon project itself) and most of its modules are written in Python. A few configuration modules are still written in C.

Note

Historically, when Cinnamon was forked from GNOME 3, all configuration modules were written in C, as part of gnome-control-center. At the beginning of the Cinnamon project, all configurations modules were thus written in C and were part of cinnamon-control-center. Since then the vast majority of modules were rewritten from scratch in Python and moved to the Cinnamon project itself.

Nowadays, only a few modules are still in cinnamon-control-center:

| color           | Color profiles                     |
| --------------- | ---------------------------------- |
| datetime        | Date and Time configuration        |
| display         | Display and monitors configuration |
| network         | Network configuration              |
| online-accounts | Online Accounts configuration      |
| wacom           | Wacom devices configuration        |

Cinnamon-control-center is developed in C and the source code is available on [Github](https://github.com/linuxmint/cinnamon-control-center).
