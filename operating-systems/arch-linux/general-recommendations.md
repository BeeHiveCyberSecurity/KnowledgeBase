# General Recommendations

This document is an annotated index of popular articles and important information for improving and adding functionalities to the installed Arch system. Readers are assumed to have read and followed the Installation guide to obtain a basic Arch Linux installation. Having read and understood the concepts explained in [#System administration](broken-reference) and [#Package management](broken-reference) is _required_ for following the other sections of this page and the other articles in the wiki.

### System administration

This section deals with administrative tasks and system management. See Core utilities and Category:System administration for more.

#### Users and groups

A new installation leaves you with only the [superuser](https://en.wikipedia.org/wiki/Superuser) account, better known as "root". Logging in as root for prolonged periods of time, possibly even exposing it via SSH on a server, [is insecure](https://apple.stackexchange.com/questions/192365/is-it-ok-to-use-the-root-user-as-a-normal-user/192422#192422). Instead, you should create and use unprivileged user account(s) for most tasks, only using the root account for system administration. See Users and groups#User management for details.

Users and groups are a mechanism for _access control_; administrators may fine-tune group membership and ownership to grant or deny users and services access to system resources. Read the Users and groups article for details and potential security risks.

#### Security

Read Security for recommendations and best practices on hardening the system.

For a list of applications to allow running commands or starting an interactive shell as another user (e.g. root), see List of applications/Security#Privilege elevation.

#### Service management

Arch Linux uses systemd as the init process, which is a system and service manager for Linux. For maintaining your Arch Linux installation, it is a good idea to learn the basics about it.

Interaction with _systemd_ is done through the _systemctl_ command. See systemd#Basic systemctl usage for more information.

A logging system is also provided, with the command _journalctl_. See journal for more information.

#### System maintenance

Arch is a rolling release system and has rapid package turnover, so users have to take some time to do system maintenance.

### Package management

This section contains helpful information related to package management. See FAQ#Package management and Category:Package management for more.

**Note:** It is imperative to keep up to date with changes in Arch Linux that require manual intervention before upgrading your system. Subscribe to the [arch-announce mailing list](https://lists.archlinux.org/mailman3/lists/arch-announce.lists.archlinux.org/) or the [recent news RSS feed](https://archlinux.org/feeds/news/). Alternatively, check the front page [Arch news](https://archlinux.org/) every time before you update.

#### pacman

pacman is the Arch Linux _pac_kage _man_ager: it is highly encouraged to become familiar with it before reading any other articles.

To enable downloading packages in parallel, see pacman#Enabling parallel downloads.

For long term handling of cached packages, see pacman#Cleaning the package cache.

See pacman/Tips and tricks for suggestions on how to improve your interaction with _pacman_ and package management in general.

#### Repositories

See the Official repositories article for details about the purpose of each officially maintained repository.

If you plan on using 32-bit applications, you will want to enable the multilib repository.

The Unofficial user repositories article lists several other unsupported repositories.

You may consider installing the pkgstats service.

#### Mirrors

Visit the Mirrors article for steps on taking full advantage of using the fastest and most up to date mirrors of the official repositories. As explained in the article, a particularly good advice is to routinely check the [Mirror Status](https://archlinux.org/mirrors/status/) page for a list of mirrors that have been recently synced. This can be automated with Reflector.

#### Arch Build System

_Ports_ is a system initially used by BSD distributions consisting of build scripts that reside in a directory tree on the local system. Simply put, each port contains a script within a directory intuitively named after the installable third-party application.

The Arch Build System offers the same functionality by providing build scripts called PKGBUILDs, which are populated with information for a given piece of software: integrity hashes, project URL, version, license and build instructions. These PKGBUILDs are parsed by makepkg, the actual program that generates packages that are cleanly manageable by _pacman_.

Every package in the repositories along with those present in the AUR are subject to recompilation with _makepkg_.

#### Arch User Repository

While the Arch Build System allows the ability of building software available in the official repositories, the Arch User Repository (AUR) is the equivalent for user submitted packages. It is an unsupported repository of build scripts accessible through the [web interface](https://aur.archlinux.org/) or through the Aurweb RPC interface.

### Booting

This section contains information pertaining to the boot process. An overview of the Arch boot process can be found at Arch boot process. See Category:Boot process for more.

#### Hardware auto-recognition

Hardware should be auto-detected by udev during the boot process by default. A potential improvement in boot time can be achieved by disabling module auto-loading and specifying required modules manually, as described in Kernel modules. Additionally, Xorg should be able to auto-detect required drivers using `udev`, but users have the option to configure the X server manually too.

#### Microcode

Processors may have [faulty behaviour](https://www.anandtech.com/show/8376/intel-disables-tsx-instructions-erratum-found-in-haswell-haswelleep-broadwelly), which the kernel can correct by updating the _microcode_ on startup. See Microcode for details.

#### Retaining boot messages

Once the login prompt appears, the messages from boot are cleared, leaving users unable to gather feedback from them. Disable clearing of boot messages to overcome this limitation.

#### Num Lock activation

[Num Lock](https://en.wikipedia.org/wiki/Num\_Lock) is a toggle key found in most keyboards. For activating Num Lock's number key-assignment during startup, see Activating numlock on bootup.

### Graphical user interface

This section provides orientation for users wishing to run graphical applications on their system. See Category:Graphical user interfaces for additional resources.

#### Display server

Xorg is the public, open-source implementation of the [X Window System](https://en.wikipedia.org/wiki/X\_Window\_System) (commonly X11, or X). It is required for running applications with graphical user interfaces (GUIs), and the majority of users will want to install it.

Wayland is a newer, alternative display server protocol with several compositors to choose from.

#### Display drivers

The default _modesetting_ display driver will work with most video cards, but performance may be improved and additional features harnessed by installing the appropriate driver for AMD or NVIDIA products.

#### Desktop environments

Although the display server provides the basic framework for building a graphical environment, additional components may be considered necessary for a complete user experience. Desktop environments such as KDE, GNOME, Xfce, Cinnamon, LXDE, bundle together a wide range of well-integrated applications, such as a window manager or compositor, panel/taskbar, file manager, terminal emulator, text editor, icons, and other utilities. Users with less experience may wish to install a desktop environment for a more familiar environment. See Category:Desktop environments for additional resources.

#### Window managers or compositors

A full-fledged desktop environment provides a complete and consistent graphical user interface, but tends to consume a good amount of system resources. Users seeking to maximize performance or otherwise simplify their environment may opt to install a window manager or compositor alone and hand-pick desired extras. Using Xorg, most desktop environments allow use of an alternative window manager as well. Dynamic, stacking, and tiling window managers differ in their handling of window placement.

#### Display manager

Most desktop environments include a display manager for automatically starting the graphical environment and managing user logins. Users without a desktop environment can install one separately. Alternatively you may start X at login as a simple alternative to a display manager.

#### User directories

Well-known user directories like Downloads or Music are created by the `xdg-user-dirs-update.service` user service, that is provided by [xdg-user-dirs](https://archlinux.org/packages/?name=xdg-user-dirs) and enabled by default upon install. If your desktop environment or window manager does not pull in the package, you can install it and run `xdg-user-dirs-update` manually as per XDG user directories#Creating default directories.

### Power management

This section may be of use to laptop owners or users otherwise seeking power management controls. See Category:Power management for more.

See Power management for more general overview.

#### ACPI events

Users can configure how the system reacts to ACPI events such as pressing the power button or closing a laptop's lid. For the new (recommended) method using systemd, see Power management with systemd. For the old method, see acpid.

#### CPU frequency scaling

Modern processors can decrease their frequency and voltage to reduce heat and power consumption. Less heat leads to more quiet system and prolongs the life of hardware. See CPU frequency scaling for details.

#### Laptops

For articles related to portable computing along with model-specific installation guides, please see Category:Laptops. For a general overview of laptop-related articles and recommendations, see Laptop.

#### Suspend and hibernate

See the main article: Power management/Suspend and hibernate.

### Multimedia

Category:Multimedia includes additional resources.

#### Sound system

ALSA is a kernel sound system that should work out the box (it just needs to be unmuted). Sound servers such as PipeWire and PulseAudio can offer additional features and support more complex audio configuration.

See Professional audio for advanced audio requirements.

### Networking

This section is confined to small networking procedures. See Network configuration for a full configuration guide and Category:Networking for related articles.

#### Clock synchronization

The [Network Time Protocol](https://en.wikipedia.org/wiki/Network\_Time\_Protocol) (NTP) is a protocol for synchronizing the clocks of computer systems over packet-switched, variable-latency data networks. See Time synchronization for implementations of such protocol.

#### DNS security

For better security while browsing the web, paying online, connecting to SSH services and similar tasks consider using DNSSEC-enabled DNS resolver that can validate signed [DNS](https://en.wikipedia.org/wiki/Domain\_Name\_System) records, and an encrypted protocol such as [DNS over TLS](https://en.wikipedia.org/wiki/DNS\_over\_TLS), [DNS over HTTPS](https://en.wikipedia.org/wiki/DNS\_over\_HTTPS) or [DNSCrypt](https://en.wikipedia.org/wiki/DNSCrypt). See Domain name resolution for details.

#### Setting up a firewall

A firewall can provide an extra layer of protection on top of the Linux networking stack. While the stock Arch kernel is capable of using [Netfilter](https://en.wikipedia.org/wiki/Netfilter)'s iptables and nftables, neither are enabled by default. It is highly recommended to set up some form of firewall. See Category:Firewalls for available guides.

#### Network shares

To share files among the machines in a network, follow the NFS or the SSHFS article.

Use Samba to join a Windows network. To configure the machine to use Active Directory for authentication, read Active Directory integration.

See also Category:Network sharing.

### Input devices

This section contains popular input device configuration tips. See Category:Input devices for more.

#### Keyboard layouts

Non-English or otherwise non-standard keyboards may not function as expected by default. The necessary steps to configure the keymap are different for virtual console and Xorg, they are described in Keyboard configuration in console and Keyboard configuration in Xorg respectively.

#### Mouse buttons

Owners of advanced or unusual mice may find that not all mouse buttons are recognized by default, or may wish to assign different actions for extra buttons. Instructions can be found in Mouse buttons.

#### Laptop touchpads

Many laptops use [Synaptics](https://www.synaptics.com/) or [ALPS](https://www.alps.com/) "touchpad" pointing devices. For these, and several other touchpad models, you can use either the Synaptics input driver or libinput; see Touchpad Synaptics and libinput for installation and configuration details.

#### TrackPoints

See the TrackPoint article to configure your TrackPoint device.

### Optimization

This section aims to summarize tweaks, tools and available options useful to improve system and application performance.

#### Benchmarking

Benchmarking is the act of measuring performance and comparing the results to another system's results or a widely accepted standard through a unified procedure.

#### Improving performance

The Improving performance article gathers information and is a basic rundown about gaining performance in Arch Linux.

#### Solid state drives

The Solid state drive article covers many aspects of solid state drives, including configuring them to maximize their lifetimes, e.g. with TRIM.

### System services

This section relates to daemons.

#### File index and search

Most distributions have a _locate_ command available to be able to quickly search files. Arch Linux provides several alternatives, see locate for details.

Desktop search engines provide a similar service, while better integrated into desktop environments.

#### Local mail delivery

A default setup does not provide a way to synchronize mail. A list of mail delivery agents is available in the Mail server article.

#### Printing

CUPS is a standards-based, open source printing system developed by OpenPrinting for Linux. See Category:Printers for printer-specific articles.

### Appearance

This section contains frequently-sought "eye candy" tweaks for an aesthetically pleasing Arch experience. See Category:Eye candy for more.

#### Fonts

You may wish to install a set of TrueType fonts, as only unscalable bitmap fonts are included in a basic Arch system. There are several general-purpose font families providing large [Unicode](https://en.wikipedia.org/wiki/Unicode) coverage and even metric compatibility with fonts from other operating systems.

A plethora of information on the subject can be found in the Fonts and Font configuration articles.

If spending a significant amount of time working from the virtual console (i.e. outside an X server), users may wish to change the console font to improve readability; see Linux console#Fonts.

#### GTK and Qt themes

A big part of the applications with a graphical interface for Linux systems are based on the GTK or the Qt toolkits. See those articles and Uniform look for Qt and GTK applications for ideas to improve the appearance of your installed programs and adapt it to your liking.

### Console improvements

This section applies to small modifications that improve console programs' practicality. See Category:Command-line shells for more.

#### Tab-completion enhancements

It is recommended to properly set up extended [tab completion](https://en.wikipedia.org/wiki/Command-line\_completion) right away, as instructed in the article of your chosen shell.

#### Aliases

Aliasing a command, or a group thereof, is a way of saving time when using the console. This is especially helpful for repetitive tasks that do not need significant alteration to their parameters between executions. Common time-saving aliases can be found in Bash#Aliases, which are easily portable to zsh as well.

#### Alternative shells

Bash is the shell installed by default in an Arch system. The live installation media, however, uses zsh with the [grml-zsh-config](https://archlinux.org/packages/?name=grml-zsh-config) addon package. See Command-line shell#List of shells for more alternatives.

#### Bash additions

A list of miscellaneous Bash settings, history search and Readline macros is available in Bash#Tips and tricks.

#### Colored output

This section is covered in Color output in console.

#### Compressed files

Compressed files, or archives, are frequently encountered on a GNU/Linux system. Tar is one of the most commonly used archiving tools, and users should be familiar with its syntax (Arch Linux packages, for example, are simply [zstd](https://archlinux.org/packages/?name=zstd) compressed tarballs). See Archiving and compression.

#### Console prompt

The console prompt (`PS1`) can be customized to a great extent. See Bash/Prompt customization or Zsh#Prompts if using Bash or Zsh, respectively.

#### Emacs shell

Emacs is known for featuring options beyond the duties of regular text editing, one of these being a full shell replacement. Consult Emacs#Colored output issues for a fix regarding garbled characters that may result from enabling colored output.

#### Mouse support

Using a mouse with the console for copy-paste operations can be preferred over GNU Screen's traditional copy mode. Refer to General purpose mouse for comprehensive directions. Note that you can already do this in terminal emulators with the clipboard.

#### Session management

Using terminal multiplexers like tmux or GNU Screen, programs may be run under sessions composed of tabs and panes that can be detached at will, so when the user either kills the terminal emulator, terminates X, or logs off, the programs associated with the session will continue to run in the background as long as the terminal multiplexer server is active. Interacting with the programs requires reattaching to the session.
