# Frequently Asked Questions

### General

#### What is Arch Linux?

See the Arch Linux article.

#### Why would I not want to use Arch?

You may not want to use Arch, if:

* you do not have the ability/time/desire for a 'do-it-yourself' GNU/Linux distribution.
* you require support for an architecture other than x86\_64.
* you take a strong stance on using a distribution which only provides free software as defined by GNU.
* you believe an operating system should configure itself, run out of the box, and include a complete default set of software and desktop environment on the installation media.
* you do not want a rolling release GNU/Linux distribution.
* you are happy with your current OS.

#### Why would I want to use Arch?

Because Arch is the best.

#### What architectures does Arch support?

Arch only supports the [x86\_64](https://en.wikipedia.org/wiki/x86\_64) (sometimes called amd64) architecture. Support for i686 was dropped in November 2017 [\[1\]](https://archlinux.org/news/the-end-of-i686-support/).

There are _unofficial_ ports for the i686 architecture [\[2\]](https://archlinux32.org/) and [ARM](https://en.wikipedia.org/wiki/ARM\_architecture) CPUs [\[3\]](https://archlinuxarm.org/), each with their own community channels.

#### Does Arch follow the Linux Foundation's Filesystem Hierarchy Standard (FHS)?

Arch Linux follows the _file system hierarchy_ for operating systems using the systemd service manager. See [file-hierarchy(7)](https://man.archlinux.org/man/file-hierarchy.7) for an explanation of each directory along with their designations. In particular, `/bin`, `/sbin`, and `/usr/sbin` are symbolic links to `/usr/bin`, and `/lib` and `/lib64` are symbolic links to `/usr/lib`.

#### I am a complete GNU/Linux beginner. Should I use Arch?

If you are a beginner and want to use Arch, you must be willing to invest time into learning a new system, and accept that Arch is designed as a 'do-it-yourself' distribution; it is the user who assembles the system.

Before asking for help, do your own independent research by searching the Web, the forum and the superb documentation provided by the Arch Wiki. _There is a reason these resources were made available to you in the first place._ Many thousands of _volunteered_ hours have been spent compiling this excellent information.

See also Arch terminology#RTFM and the Installation guide.

#### Is Arch designed to be used as a server? A desktop? A workstation?

Arch is not designed for any particular type of use. Rather, it is designed for a particular type of _user_. Arch targets competent users who enjoy its 'do-it-yourself' nature, and who further exploit it to shape the system to fit their unique needs. Therefore, in the hands of its target user base, Arch can be used for virtually any purpose. Many use Arch on both their desktops and workstations. And of course, archlinux.org, aur.archlinux.org and almost all of Arch's [infrastructure](https://gitlab.archlinux.org/archlinux/infrastructure) runs on Arch.

#### I really like Arch, except the development team needs to implement feature X

Get involved, contribute your code/solution to the community. If it is well-regarded by the community and development team, perhaps it will be merged. The Arch community thrives on contribution and sharing of code and tools.

#### When will the new release be made available?

Arch Linux releases are simply a live environment for installation or rescue, which include the [base](https://archlinux.org/packages/?name=base) meta package and a few [other packages](https://gitlab.archlinux.org/archlinux/archiso/-/blob/master/configs/releng/packages.x86\_64). The releases are issued usually in the first half of every month.

#### Is Arch Linux a stable distribution? Will I get frequent breakage?

It is _the user_ who is ultimately responsible for the stability of their own rolling release system. The user decides when to upgrade, and merges necessary changes when required. If the user reaches out to the community, help is often provided in a timely manner. The difference between Arch and other distributions in this regard is that Arch is truly a 'do-it-yourself' distribution; complaints of breakage are misguided and unproductive, since upstream changes are not the responsibility of Arch devs.

See the System maintenance article for tips on how to make an Arch Linux system as stable as possible.

#### Arch needs more press (i.e. advertisement)

Arch gets plenty of press as it is. The goal of Arch Linux is not to be large; rather, organic, sustainable growth occurs naturally amongst the target user base.

#### Arch needs more developers

Possibly so. Feel free to volunteer your time! Visit the [forums](https://bbs.archlinux.org/), IRC channels, and [mailing lists](https://lists.archlinux.org/mailman3/lists/), and see what needs to be done. See also Getting involved for details.

### Installation

#### Arch needs an installer. Maybe a GUI installer?

Arch used to have an installer with a text-based user interface called the Arch Installation Framework (AIF). After its [last maintainer left](https://lists.archlinux.org/archives/list/arch-releng@lists.archlinux.org/thread/4BW5FZZFIOMD3RFMOM4XVHKKEDMLXWPQ/), it was deprecated in favor of [arch-install-scripts](https://archlinux.org/packages/?name=arch-install-scripts).

Since [2021-04-01](https://archlinux.org/news/installation-medium-with-installer/), Arch has an installer again. See archinstall for details.

#### I installed Arch, and now I am at a shell! What now?

See General recommendations.

#### Which desktop environment or window manager should I use?

Since many are available to you, use the one that best fits your needs. Have a look at the Desktop environment and Window manager articles.

#### What makes Arch unique amongst other "minimal" distributions?

See Arch compared to other distributions.

### System maintenance

See also System maintenance.

#### Why is my internet so slow compared to other operating systems?

Is your network configured correctly? Have a look at the Network configuration article.

Also note that Arch Linux does not come with [traffic shaping](https://en.wikipedia.org/wiki/Traffic\_shaping) enabled. Thus, it is possible that if a program on it somehow utilizes your internet connection to the full – regardless if it is over P2P or classic client-server connections – other local ones will find it clogged, resulting in severe lags and timeouts. Relief can be provided by firewalls such as _Shorewall_ or _Vuurmuur_; there are also static scripts for [iproute2](https://archlinux.org/packages/?name=iproute2) (such as [this derivative](http://serendipity.ruwenzori.net/index.php/2008/06/01/modified-wondershaper-for-better-voip-qos) of _Wondershaper_), which allow shaping on the network layer.

#### Why is Arch using all my RAM?

Essentially, unused RAM is wasted RAM.

Many new users notice how the Linux kernel handles memory differently than they are used to. Since accessing data from RAM is much faster than from a storage drive, the kernel caches recently accessed data in memory. The cached data is only cleared when the system begins to run out of available memory and new data needs to be loaded.

We could distinguish the difference from `free` command:

```
$ free -h
```

```
              total        used        free      shared  buff/cache   available
Mem:          2.8Gi       1.1Gi       283Mi       224Mi       1.4Gi       1.2Gi
Swap:         3.0Gi       881Mi       2.1Gi
```

It is important to note the difference between "free" and "available" memory. In the above example, a laptop with 2.8 GiB of total RAM appears to be using most of it, with only 283 MiB as free memory. However, 1.4 GiB of it is "buff/cache". There is still 1.2 GiB available for starting new applications, without swapping. See [free(1)](https://man.archlinux.org/man/free.1) for details. The result of all this? Performance!

See [this wonderful article](https://www.linuxjournal.com/article/2770) if your curiosity has been piqued. There is also a website dedicated to clearing this confusion: [https://www.linuxatemyram.com/](https://www.linuxatemyram.com/).

#### Where did all my free space go?

The answer to this question depends on your system. There are some fine utilities that may help you find the answer.

### Package management

See the pacman, pacman/Tips and tricks and Official repositories pages for more answers.

#### I have found an error with package X. What should I do?

First, you need to figure out if this error is something the Arch team can fix. Sometimes it is not (e.g. Firefox crashes may be the fault of the Mozilla team); this is called an _upstream error_. If it is an Arch problem, there is a series of steps you can take:

1. Search the forums for information. See if anyone else has noticed it.
2. Post a bug report with detailed information at [https://bugs.archlinux.org](https://bugs.archlinux.org/).
3. If you would like, write a forum post detailing the problem and the fact that you have reported it already. This will help prevent a lot of people from reporting the same error.

#### Arch packages need to use a unique naming convention. ".pkg.tar.zst" is too long and/or confusing

This has been discussed on the Arch mailing list. Some proposed a _.pac_ file extension, but there is no plan to change the package extension. As Tobias Kieslich, one of the Arch developers, put it, "A package is a _\[compressed]_ tarball! And it can be opened, investigated and manipulated by any tar-capable application. Moreover, the mime-type is automatically detected correctly by most applications."

#### Pacman needs a library so other applications can easily access package information

Pacman is a front-end to [libalpm(3)](https://man.archlinux.org/man/libalpm.3)—the "Arch Linux Package Management" library—which allows alternative front-ends, like a GUI front-end, to be written.

#### Pacman needs feature X!

If you think an idea has merit, you may choose to discuss it on [pacman-dev](https://lists.archlinux.org/mailman3/lists/pacman-dev.lists.archlinux.org/). Also check [https://gitlab.archlinux.org/pacman/pacman/-/issues](https://gitlab.archlinux.org/pacman/pacman/-/issues) and [https://bugs.archlinux.org/index.php?project=3](https://bugs.archlinux.org/index.php?project=3) for existing feature requests.

However, the best way to get a feature added to pacman or Arch Linux is to implement it yourself. The patch or code may or may not be officially accepted, but perhaps others will appreciate, test and contribute to your effort.

#### I just installed Package X. How do I start it?

If you are using a desktop environment like KDE or GNOME, the program should automatically show up in your menu. If you are trying to run the program from a terminal and do not know the binary name, use:

```
$ pacman -Qlq package_name | grep /usr/bin/
```

#### Why is there only a single version of each shared library in the official repositories?

Several distributions, such as Debian, have different versions of shared libraries packaged as different packages: `libfoo1`, `libfoo2`, `libfoo3` and so on. In this way it is possible to have applications compiled against different versions of `libfoo` installed on the same system.

In case of a distribution like Arch, only the latest packaged versions are officially supported. By dropping support for outdated software, package maintainers are able to spend more time ensuring that the newest versions work as expected. As soon as a new version of a shared library becomes available from upstream, it is added to the repositories and affected packages are rebuilt to use the new version.

#### What if I run a full system upgrade and there will be an update for a shared library, but not for the applications that depend on it?

This scenario should not happen at all. Assuming an application called `foobaz` is in one of the official repositories and builds successfully against a new version of a shared library called `libbaz`, it will be updated along with `libbaz`. If, however, it does not build successfully, `foobaz` package will have a versioned dependency (e.g. _libbaz 1.5_), and will be removed by pacman during `libbaz` upgrade, due to a conflict.

If `foobaz` is a package that you built yourself and installed from AUR, you should try rebuilding `foobaz` against the new version of `libbaz`. If the build fails, report the bug to the `foobaz` developers.

#### Is it possible that there is a major kernel update in the repository, and that some of the driver packages have not been updated?

No, it is not possible. Major kernel updates (e.g. _linux 3.5.0-1_ to _linux 3.6.0-1_) are always accompanied by rebuilds of all supported kernel driver packages. On the other hand, if you have an unsupported driver package (e.g. from the AUR) installed on your system, then a kernel update might break things for you if you do not rebuild it for the new kernel. Users are responsible for updating any unsupported driver packages that they have installed.

#### What to do before upgrading?

Follow the System maintenance#Upgrading the system section.

#### A package update was released, but pacman says the system is up to date

_pacman_ mirrors are not synced immediately. It may take over 24 hours before an update is available to you. The only options are be patient or use another mirror. [MirrorStatus](https://archlinux.org/mirrors/status/) can help you identify an up-to-date mirror.

#### Upstream project X has released a new version. How long will it take for the Arch package to update to that new version?

Package updates will be released when they are ready. The specific amount of time can be as short as a few hours after upstream releases a minor bugfix update to as long as several weeks after a large package group's major update. The amount of time from an upstream's new version to Arch releasing a new package depends on the specific packages and the availability of the package maintainers. Additionally, some packages spend some time in the testing repository, so this can prolong the time before a package is updated. Package maintainers attempt to work quickly to bring stable updates to the repositories. If you find a package in the official repositories that is out of date, go to that package's page at the [package website](https://archlinux.org/packages/) and flag it.

#### If I need an older version of an installed library, can I just symlink to the newer version?

If you are lucky, it might work, for a time. Regardless, it is not a proper solution, because:

* Libraries do not change versions randomly – the API/ABI will have likely changed (possibly with bits removed), and whether those changes affect the usage is just a matter of luck.
* The symlink would be untracked by a package manager. Beginners who immediately try to hack on system library files are in the greatest risk of making an unwanted change that they cannot diagnose/fix, which a package manager helps to guard against.
* A slight alternative of dumping the old library file into the filesystem, untracked, would be forgotten about, and not have potential security bugs noticed/patched.

Instead, e.g. use/write a [compat package](https://aur.archlinux.org/packages/?SeB=n\&K=compat), which provides the required library version.

### 64-bit

#### How do I determine if my processor is x86\_64 compatible?

If your processor is [x86\_64](https://en.wikipedia.org/wiki/X86-64) compatible, you will have the `lm` ([long mode](https://en.wikipedia.org/wiki/Long\_mode)) flag in `/proc/cpuinfo`. For example,

```
$ grep -w lm /proc/cpuinfo
```

Under Windows, using the freeware [CPU-Z](https://www.cpuid.com/cpuz.php) helps determine whether your CPU is 64-bit compatible. CPUs with AMD's instruction set "AMD64" or Intel's solution "EM64T" should be compatible with the x86\_64 releases and binary packages.

#### Why 64-bit?

It is faster under most circumstances and as an added bonus also inherently more secure due to the nature of [Address space layout randomization (ASLR)](https://en.wikipedia.org/wiki/Address\_space\_layout\_randomization) in combination with [Position-independent code (PIC)](https://en.wikipedia.org/wiki/Position-independent\_code) and the [NX Bit](https://en.wikipedia.org/wiki/NX\_Bit) which is not available in the stock i686 kernel due to disabled [Physical Address Extension (PAE)](https://en.wikipedia.org/wiki/Physical\_Address\_Extension). If your computer has more than 4 GiB of RAM, only a 64-bit OS will be able to fully utilize it.

Programmers also increasingly tend to care less about 32-bit ("legacy") as "new" x86 CPUs typically support the 64-bit extensions.

There are many more reasons we could list here to tell you to avoid 32-bit, but between the kernel, userspace and individual programs it is simply not viable to list every last thing that 64-bit does much better these days.
