---
description: >-
  Util-linux is an open-source collection of Linux utilities that provides
  various security-related features, including password management and disk
  encryption.
---

# ⚙ util-linux

Util-linux is a popular open-source collection of Linux utilities that provides various essential system tools to manage and maintain the Linux operating system. It includes more than 70 different utilities, such as fdisk, login, mount, and many others, that are commonly used by system administrators and end-users alike.

One of the critical utilities included in Util-linux is the security tool, which provides several security-related features for Linux systems. These features aim to secure the system against unauthorized access, prevent data loss, and maintain the system's integrity. In this article, we will discuss the different security-related features provided by the security tool in Util-linux.

One of the most crucial security features of the security tool is the password management utility. This utility allows administrators to manage user passwords and ensure that they are stored securely. It provides different password management options, such as setting password expiration dates, password length, and password complexity requirements. Additionally, the utility also provides a way to create new passwords, modify existing passwords, and verify password strength.

Another essential security feature provided by the security tool is the cryptsetup utility. This utility allows administrators to encrypt and decrypt the file system to protect sensitive data stored on the system. It supports different encryption methods, such as AES and Twofish, and provides various authentication options, such as passwords, keyfiles, and tokens. Additionally, cryptsetup also supports creating encrypted volumes on external devices such as USB drives.

Util-linux's security tool also includes a number of utilities that can be used to secure the boot process. The mkinitrd utility, for example, allows administrators to create a custom initramfs image, which can include different kernel modules and scripts that are required to boot the system. This can be used to ensure that only authorized users can boot the system, and that the system is protected against unauthorized modifications.

Finally, Util-linux's security tool also includes several utilities that can be used to audit the system and monitor its security. For example, the auditctl utility allows administrators to configure the Linux Audit System, which can be used to track system events and detect security-related issues. Additionally, the logname utility can be used to display the current user's login name, which can be useful for auditing purposes.

In conclusion, Util-linux's security tool provides several critical security-related features for Linux systems. These features aim to protect the system against unauthorized access, prevent data loss, and maintain the system's integrity. By using these tools, administrators can ensure that their Linux systems are secure and protected against potential security threats.

### Packages and Binaries:

This package contains some extra BSD utilities: col, colcrt, colrm, column, hd, hexdump, look, ul and write. Other BSD utilities are provided by bsdutils and calendar.

**Installed size:** `337 KB`\
**How to install:** `sudo apt install bsdextrautils`

<details>

<summary>Dependencies:</summary>

* libc6
* libsmartcols1
* libtinfo6

</details>

**col**

Filter reverse line feeds from input

```
:~# col --help

Usage:
 col [options]

Filter out reverse line feeds from standard input.

Options:
 -b, --no-backspaces    do not output backspaces
 -f, --fine             permit forward half line feeds
 -p, --pass             pass unknown control sequences
 -h, --tabs             convert spaces to tabs
 -x, --spaces           convert tabs to spaces
 -l, --lines NUM        buffer at least NUM lines
 -H, --help             display this help
 -v, --version          display version

For more details see col(1).
```

***

**colcrt**

Filter nroff output for CRT previewing

```
:~# colcrt -h

Usage:
 colcrt [options] [<file>...]

Filter nroff output for CRT previewing.

Options:
 -,  --no-underlining    suppress all underlining
 -2, --half-lines        print all half-lines

 -h, --help              display this help
 -V, --version           display version

For more details see colcrt(1).
```

***

**colrm**

Remove columns from a file

```
:~# colrm -h

Usage:
 colrm [startcol [endcol]]

Filter out the specified columns.

Options:
 -h, --help     display this help
 -V, --version  display version
colrm reads from standard input and writes to standard output


For more details see colrm(1).
```

***

**column**

Columnate lists

```
:~# column -h

Usage:
 column [options] [<file>...]

Columnate lists.

Options:
 -t, --table                      create a table
 -n, --table-name <name>          table name for JSON output
 -O, --table-order <columns>      specify order of output columns
 -N, --table-columns <names>      comma separated columns names
 -l, --table-columns-limit <num>  maximal number of input columns
 -E, --table-noextreme <columns>  don't count long text from the columns to column width
 -d, --table-noheadings           don't print header
 -e, --table-header-repeat        repeat header for each page
 -H, --table-hide <columns>       don't print the columns
 -R, --table-right <columns>      right align text in these columns
 -T, --table-truncate <columns>   truncate text in the columns when necessary
 -W, --table-wrap <columns>       wrap text in the columns when necessary
 -L, --keep-empty-lines           don't ignore empty lines
 -J, --json                       use JSON output format for table

 -r, --tree <column>              column to use tree-like output for the table
 -i, --tree-id <column>           line ID to specify child-parent relation
 -p, --tree-parent <column>       parent to specify child-parent relation

 -c, --output-width <width>       width of output in number of characters
 -o, --output-separator <string>  columns separator for table output (default is two spaces)
 -s, --separator <string>         possible table delimiters
 -x, --fillrows                   fill rows before columns

 -h, --help                       display this help
 -V, --version                    display version

For more details see column(1).
```

***

**hd**

Display file contents in hexadecimal, decimal, octal, or ascii MFM/IDE hard disk devices

```
:~# hd -h

Usage:
 hd [options] <file>...

Display file contents in hexadecimal, decimal, octal, or ascii.

Options:
 -b, --one-byte-octal      one-byte octal display
 -c, --one-byte-char       one-byte character display
 -C, --canonical           canonical hex+ASCII display
 -d, --two-bytes-decimal   two-byte decimal display
 -o, --two-bytes-octal     two-byte octal display
 -x, --two-bytes-hex       two-byte hexadecimal display
 -L, --color[=<mode>]      interpret color formatting specifiers
                             colors are enabled by default
 -e, --format <format>     format string to be used for displaying data
 -f, --format-file <file>  file that contains format strings
 -n, --length <length>     interpret only length bytes of input
 -s, --skip <offset>       skip offset bytes from the beginning
 -v, --no-squeezing        output identical lines

 -h, --help                display this help
 -V, --version             display version

Arguments:
 <length> and <offset> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

For more details see hexdump(1).
```

***

**hexdump**

Display file contents in hexadecimal, decimal, octal, or ascii

```
:~# hexdump -h

Usage:
 hexdump [options] <file>...

Display file contents in hexadecimal, decimal, octal, or ascii.

Options:
 -b, --one-byte-octal      one-byte octal display
 -c, --one-byte-char       one-byte character display
 -C, --canonical           canonical hex+ASCII display
 -d, --two-bytes-decimal   two-byte decimal display
 -o, --two-bytes-octal     two-byte octal display
 -x, --two-bytes-hex       two-byte hexadecimal display
 -L, --color[=<mode>]      interpret color formatting specifiers
                             colors are enabled by default
 -e, --format <format>     format string to be used for displaying data
 -f, --format-file <file>  file that contains format strings
 -n, --length <length>     interpret only length bytes of input
 -s, --skip <offset>       skip offset bytes from the beginning
 -v, --no-squeezing        output identical lines

 -h, --help                display this help
 -V, --version             display version

Arguments:
 <length> and <offset> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

For more details see hexdump(1).
```

***

**look**

Display lines beginning with a given string

```
:~# look -h

Usage:
 look [options] <string> [<file>...]

Display lines beginning with a specified string.

Options:
 -a, --alternative        use the alternative dictionary
 -d, --alphanum           compare only blanks and alphanumeric characters
 -f, --ignore-case        ignore case differences when comparing
 -t, --terminate <char>   define the string-termination character

 -h, --help               display this help
 -V, --version            display version

For more details see look(1).
```

***

**ul**

Do underlining

```
:~# ul -h

Usage:
 ul [options] [<file> ...]

Do underlining.

Options:
 -t, -T, --terminal TERMINAL  override the TERM environment variable
 -i, --indicated              underlining is indicated via a separate line
 -h, --help                   display this help
 -V, --version                display version

For more details see ul(1).
```

***

**write**

Send a message to another user

```
:~# write -h

Usage:
 write [options] <user> [<ttyname>]

Send a message to another user.

Options:
 -h, --help     display this help
 -V, --version  display version

For more details see write(1).
```

***

#### bsdutils <a href="#bsdutils" id="bsdutils"></a>

This package contains the bare minimum of BSD utilities needed for a Debian system: logger, renice, script, scriptlive, scriptreplay and wall. The remaining standard BSD utilities are provided by bsdextrautils.

**Installed size:** `355 KB`\
**How to install:** `sudo apt install bsdutils`

<details>

<summary>Dependencies:</summary>

* libc6
* libsystemd0

</details>

**logger**

Enter messages into the system log

```
:~# logger -h

Usage:
 logger [options] [<message>]

Enter messages into the system log.

Options:
 -i                       log the logger command's PID
     --id[=<id>]          log the given <id>, or otherwise the PID
 -f, --file <file>        log the contents of this file
 -e, --skip-empty         do not log empty lines when processing files
     --no-act             do everything except the write the log
 -p, --priority <prio>    mark given message with this priority
     --octet-count        use rfc6587 octet counting
     --prio-prefix        look for a prefix on every line read from stdin
 -s, --stderr             output message to standard error as well
 -S, --size <size>        maximum size for a single message
 -t, --tag <tag>          mark every line with this tag
 -n, --server <name>      write to this remote syslog server
 -P, --port <port>        use this port for UDP or TCP connection
 -T, --tcp                use TCP only
 -d, --udp                use UDP only
     --rfc3164            use the obsolete BSD syslog protocol
     --rfc5424[=<snip>]   use the syslog protocol (the default for remote);
                            <snip> can be notime, or notq, and/or nohost
     --sd-id <id>         rfc5424 structured data ID
     --sd-param <data>    rfc5424 structured data name=value
     --msgid <msgid>      set rfc5424 message id field
 -u, --socket <socket>    write to this Unix socket
     --socket-errors[=<on|off|auto>]
                          print connection errors when using Unix sockets
     --journald[=<file>]  write journald entry

 -h, --help               display this help
 -V, --version            display version

For more details see logger(1).
```

***

**renice**

Alter priority of running processes

```
:~# renice -h

Usage:
 renice [-n] <priority> [-p|--pid] <pid>...
 renice [-n] <priority>  -g|--pgrp <pgid>...
 renice [-n] <priority>  -u|--user <user>...

Alter the priority of running processes.

Options:
 -n, --priority <num>   specify the nice value
 -p, --pid              interpret arguments as process ID (default)
 -g, --pgrp             interpret arguments as process group ID
 -u, --user             interpret arguments as username or user ID

 -h, --help             display this help
 -V, --version          display version

For more details see renice(1).
```

***

**script**

Make typescript of terminal session

```
:~# script -h

Usage:
 script [options] [file]

Make a typescript of a terminal session.

Options:
 -I, --log-in <file>           log stdin to file
 -O, --log-out <file>          log stdout to file (default)
 -B, --log-io <file>           log stdin and stdout to file

 -T, --log-timing <file>       log timing information to file
 -t[<file>], --timing[=<file>] deprecated alias to -T (default file is stderr)
 -m, --logging-format <name>   force to 'classic' or 'advanced' format

 -a, --append                  append to the log file
 -c, --command <command>       run command rather than interactive shell
 -e, --return                  return exit code of the child process
 -f, --flush                   run flush after each write
     --force                   use output file even when it is a link
 -E, --echo <when>             echo input in session (auto, always or never)
 -o, --output-limit <size>     terminate if output files exceed size
 -q, --quiet                   be quiet

 -h, --help                    display this help
 -V, --version                 display version

For more details see script(1).
```

***

**scriptlive**

Re-run session typescripts, using timing information

```
:~# scriptlive -h

Usage:
 scriptlive [options]
 scriptlive [-t] timingfile [-I|-B] typescript

Execute terminal typescript.

Options:
 -t, --timing <file>     script timing log file
 -T, --log-timing <file> alias to -t
 -I, --log-in <file>     script stdin log file
 -B, --log-io <file>     script stdin and stdout log file

 -c, --command <command> run command rather than interactive shell
 -d, --divisor <num>     speed up or slow down execution with time divisor
 -m, --maxdelay <num>    wait at most this many seconds between updates
 -h, --help              display this help
 -V, --version           display version

For more details see scriptlive(1).
```

***

**scriptreplay**

Play back typescripts, using timing information

```
:~# scriptreplay -h

Usage:
 scriptreplay [options]
 scriptreplay [-t] timingfile [typescript] [divisor]

Play back terminal typescripts, using timing information.

Options:
 -t, --timing <file>     script timing log file
 -T, --log-timing <file> alias to -t
 -I, --log-in <file>     script stdin log file
 -O, --log-out <file>    script stdout log file (default)
 -B, --log-io <file>     script stdin and stdout log file

 -s, --typescript <file> deprecated alias to -O

     --summary           display overview about recorded session and exit
 -d, --divisor <num>     speed up or slow down execution with time divisor
 -m, --maxdelay <num>    wait at most this many seconds between updates
 -x, --stream <name>     stream type (out, in, signal or info)
 -c, --cr-mode <type>    CR char mode (auto, never, always)
 -h, --help              display this help
 -V, --version           display version

For more details see scriptreplay(1).
```

***

**wall**

Write a message to all users

```
:~# wall -h

Usage:
 wall [options] [<file> | <message>]

Write a message to all users.

Options:
 -g, --group <group>     only send message to group
 -n, --nobanner          do not print banner, works only for root
 -t, --timeout <timeout> write timeout in seconds

 -h, --help              display this help
 -V, --version           display version

For more details see wall(1).
```

***

#### eject <a href="#eject" id="eject"></a>

This program will eject CD-ROMs (assuming your drive supports the CDROMEJECT ioctl). It also allows setting the autoeject feature.

On supported ATAPI/IDE multi-disc CD-ROM changers, it allows changing the active disc.

You can also use eject to properly disconnect external mass-storage devices like digital cameras or portable music players.

**Installed size:** `132 KB`\
**How to install:** `sudo apt install eject`

<details>

<summary>Dependencies:</summary>

* libc6
* libmount1

</details>

**eject**

Eject removable media

```
:~# eject -h

Usage:
 eject [options] [<device>|<mountpoint>]

Eject removable media.

Options:
 -a, --auto <on|off>         turn auto-eject feature on or off
 -c, --changerslot <slot>    switch discs on a CD-ROM changer
 -d, --default               display default device
 -f, --floppy                eject floppy
 -F, --force                 don't care about device type
 -i, --manualeject <on|off>  toggle manual eject protection on/off
 -m, --no-unmount            do not unmount device even if it is mounted
 -M, --no-partitions-unmount do not unmount another partitions
 -n, --noop                  don't eject, just show device found
 -p, --proc                  use /proc/mounts instead of /etc/mtab
 -q, --tape                  eject tape
 -r, --cdrom                 eject CD-ROM
 -s, --scsi                  eject SCSI device
 -t, --trayclose             close tray
 -T, --traytoggle            toggle tray
 -v, --verbose               enable verbose output
 -x, --cdspeed <speed>       set CD-ROM max speed
 -X, --listspeed             list CD-ROM available speeds

 -h, --help                  display this help
 -V, --version               display version

By default tries -r, -s, -f, and -q in order until success.

For more details see eject(1).
```

***

#### fdisk <a href="#fdisk" id="fdisk"></a>

This package contains the classic fdisk, sfdisk and cfdisk partitioning utilities from the util-linux suite.

The utilities included in this package allow you to partition your hard disk. The utilities supports both modern and legacy partition tables (eg. GPT, MBR, etc).

The fdisk utility is the classical text-mode utility. The cfdisk utilitity gives a more userfriendly curses based interface. The sfdisk utility is mostly for automation and scripting uses.

**Installed size:** `479 KB`\
**How to install:** `sudo apt install fdisk`

<details>

<summary>Dependencies:</summary>

* libc6
* libfdisk1
* libmount1
* libncursesw6
* libreadline8
* libsmartcols1
* libtinfo6

</details>

**cfdisk**

Display or manipulate a disk partition table

```
:~# cfdisk -h

Usage:
 cfdisk [options] <disk>

Display or manipulate a disk partition table.

Options:
 -L, --color[=<when>]     colorize output (auto, always or never)
                            colors are enabled by default
 -z, --zero               start with zeroed partition table
     --lock[=<mode>]      use exclusive device lock (yes, no or nonblock)
 -r, --read-only          forced open cfdisk in read-only mode

 -h, --help               display this help
 -V, --version            display version

For more details see cfdisk(8).
```

***

**fdisk**

Manipulate disk partition table

```
:~# fdisk -h

Usage:
 fdisk [options] <disk>         change partition table
 fdisk [options] -l [<disk>...] list partition table(s)

Display or manipulate a disk partition table.

Options:
 -b, --sector-size <size>      physical and logical sector size
 -B, --protect-boot            don't erase bootbits when creating a new label
 -c, --compatibility[=<mode>]  mode is 'dos' or 'nondos' (default)
 -L, --color[=<when>]          colorize output (auto, always or never)
                                 colors are enabled by default
 -l, --list                    display partitions and exit
 -x, --list-details            like --list but with more details
 -n, --noauto-pt               don't create default partition table on empty devices
 -o, --output <list>           output columns
 -t, --type <type>             recognize specified partition table type only
 -u, --units[=<unit>]          display units: 'cylinders' or 'sectors' (default)
 -s, --getsz                   display device size in 512-byte sectors [DEPRECATED]
     --bytes                   print SIZE in bytes rather than in human readable format
     --lock[=<mode>]           use exclusive device lock (yes, no or nonblock)
 -w, --wipe <mode>             wipe signatures (auto, always or never)
 -W, --wipe-partitions <mode>  wipe signatures from new partitions (auto, always or never)

 -C, --cylinders <number>      specify the number of cylinders
 -H, --heads <number>          specify the number of heads
 -S, --sectors <number>        specify the number of sectors per track

 -h, --help                    display this help
 -V, --version                 display version

Available output columns:
 gpt: Device Start End Sectors Size Type Type-UUID Attrs Name UUID
 dos: Device Start End Sectors Cylinders Size Type Id Attrs Boot End-C/H/S
      Start-C/H/S
 bsd: Slice Start End Sectors Cylinders Size Type Bsize Cpg Fsize
 sgi: Device Start End Sectors Cylinders Size Type Id Attrs
 sun: Device Start End Sectors Cylinders Size Type Id Flags

For more details see fdisk(8).
```

***

**sfdisk**

Display or manipulate a disk partition table

```
:~# sfdisk -h

Usage:
 sfdisk [options] <dev> [[-N] <part>]
 sfdisk [options] <command>

Display or manipulate a disk partition table.

Commands:
 -A, --activate <dev> [<part> ...] list or set bootable (P)MBR partitions
 -d, --dump <dev>                  dump partition table (usable for later input)
 -J, --json <dev>                  dump partition table in JSON format
 -B, --backup-pt-sectors <dev>     binary partition table backup (see -b and -O)
 -g, --show-geometry [<dev> ...]   list geometry of all or specified devices
 -l, --list [<dev> ...]            list partitions of each device
 -F, --list-free [<dev> ...]       list unpartitioned free areas of each device
 -r, --reorder <dev>               fix partitions order (by start offset)
 -s, --show-size [<dev> ...]       list sizes of all or specified devices
 -T, --list-types                  print the recognized types (see -X)
 -V, --verify [<dev> ...]          test whether partitions seem correct
     --delete <dev> [<part> ...]   delete all or specified partitions

 --part-label <dev> <part> [<str>] print or change partition label
 --part-type <dev> <part> [<type>] print or change partition type
 --part-uuid <dev> <part> [<uuid>] print or change partition uuid
 --part-attrs <dev> <part> [<str>] print or change partition attributes

 --disk-id <dev> [<str>]           print or change disk label ID (UUID)
 --relocate <oper> <dev>           move partition header

Arguments:
 <dev>                     device (usually disk) path
 <part>                    partition number
 <type>                    partition type, GUID for GPT, hex for MBR

Options:
 -a, --append              append partitions to existing partition table
 -b, --backup              backup partition table sectors (see -O)
     --bytes               print SIZE in bytes rather than in human readable format
     --move-data[=<typescript>] move partition data after relocation (requires -N)
     --move-use-fsync      use fsync after each write when move data
 -f, --force               disable all consistency checking
     --color[=<when>]      colorize output (auto, always or never)
                             colors are enabled by default
     --lock[=<mode>]       use exclusive device lock (yes, no or nonblock)
 -N, --partno <num>        specify partition number
 -n, --no-act              do everything except write to device
     --no-reread           do not check whether the device is in use
     --no-tell-kernel      do not tell kernel about changes
 -O, --backup-file <path>  override default backup file name
 -o, --output <list>       output columns
 -q, --quiet               suppress extra info messages
 -w, --wipe <mode>         wipe signatures (auto, always or never)
 -W, --wipe-partitions <mode>  wipe signatures from new partitions (auto, always or never)
 -X, --label <name>        specify label type (dos, gpt, ...)
 -Y, --label-nested <name> specify nested label type (dos, bsd)

 -G, --show-pt-geometry    deprecated, alias to --show-geometry
 -L, --Linux               deprecated, only for backward compatibility
 -u, --unit S              deprecated, only sector unit is supported

 -h, --help                display this help
 -v, --version             display version

Available output columns:
 gpt: Device Start End Sectors Size Type Type-UUID Attrs Name UUID
 dos: Device Start End Sectors Cylinders Size Type Id Attrs Boot End-C/H/S
      Start-C/H/S
 bsd: Slice Start End Sectors Cylinders Size Type Bsize Cpg Fsize
 sgi: Device Start End Sectors Cylinders Size Type Id Attrs
 sun: Device Start End Sectors Cylinders Size Type Id Flags

For more details see sfdisk(8).
```

***

#### libblkid-dev <a href="#libblkid-dev" id="libblkid-dev"></a>

The blkid library allows system programs such as fsck and mount to quickly and easily find block devices by filesystem UUID or label. This allows system administrators to avoid specifying filesystems by hard-coded device names and use a logical naming system instead.

This package contains the development environment for the blkid library.

**Installed size:** `875 KB`\
**How to install:** `sudo apt install libblkid-dev`

<details>

<summary>Dependencies:</summary>

* libblkid1
* libc6-dev | libc-dev
* uuid-dev

</details>

***

#### libblkid1 <a href="#libblkid1" id="libblkid1"></a>

The blkid library allows system programs such as fsck and mount to quickly and easily find block devices by filesystem UUID or label. This allows system administrators to avoid specifying filesystems by hard-coded device names and use a logical naming system instead.

**Installed size:** `398 KB`\
**How to install:** `sudo apt install libblkid1`

<details>

<summary>Dependencies:</summary>

* libc6

</details>

***

#### libfdisk-dev <a href="#libfdisk-dev" id="libfdisk-dev"></a>

The libfdisk library is used for manipulating partition tables. It is the core of the fdisk, cfdisk, and sfdisk tools.

This package contains the development environment for the fdisk library.

**Installed size:** `77 KB`\
**How to install:** `sudo apt install libfdisk-dev`

<details>

<summary>Dependencies:</summary>

* libblkid-dev
* libc6-dev | libc-dev
* libfdisk1
* uuid-dev

</details>

***

#### libfdisk1 <a href="#libfdisk1" id="libfdisk1"></a>

The libfdisk library is used for manipulating partition tables. It is the core of the fdisk, cfdisk, and sfdisk tools.

**Installed size:** `533 KB`\
**How to install:** `sudo apt install libfdisk1`

<details>

<summary>Dependencies:</summary>

* libblkid1
* libc6
* libuuid1

</details>

***

#### libmount-dev <a href="#libmount-dev" id="libmount-dev"></a>

This device mounting library is used by mount and umount helpers.

This package contains the development environment for the mount library.

**Installed size:** `81 KB`\
**How to install:** `sudo apt install libmount-dev`

<details>

<summary>Dependencies:</summary>

* libblkid-dev
* libc6-dev | libc-dev
* libmount1
* libselinux1-dev

</details>

***

#### libmount1 <a href="#libmount1" id="libmount1"></a>

This device mounting library is used by mount and umount helpers.

**Installed size:** `454 KB`\
**How to install:** `sudo apt install libmount1`

<details>

<summary>Dependencies:</summary>

* libblkid1
* libc6
* libselinux1

</details>

***

#### libsmartcols-dev <a href="#libsmartcols-dev" id="libsmartcols-dev"></a>

This smart column output alignment library is used by fdisk utilities.

This package contains the development environment for the mount library.

**Installed size:** `61 KB`\
**How to install:** `sudo apt install libsmartcols-dev`

<details>

<summary>Dependencies:</summary>

* libc6-dev | libc-dev
* libsmartcols1

</details>

***

#### libsmartcols1 <a href="#libsmartcols1" id="libsmartcols1"></a>

This smart column output alignment library is used by fdisk utilities.

**Installed size:** `289 KB`\
**How to install:** `sudo apt install libsmartcols1`

<details>

<summary>Dependencies:</summary>

* libc6

</details>

***

#### libuuid1 <a href="#libuuid1" id="libuuid1"></a>

The libuuid library generates and parses 128-bit Universally Unique IDs (UUIDs). A UUID is an identifier that is unique within the space of all such identifiers across both space and time. It can be used for multiple purposes, from tagging objects with an extremely short lifetime to reliably identifying very persistent objects across a network.

See RFC 4122 for more information.

**Installed size:** `79 KB`\
**How to install:** `sudo apt install libuuid1`

<details>

<summary>Dependencies:</summary>

* libc6

</details>

***

#### mount <a href="#mount" id="mount"></a>

This package provides the mount(8), umount(8), swapon(8), swapoff(8), and losetup(8) commands.

**Installed size:** `393 KB`\
**How to install:** `sudo apt install mount`

<details>

<summary>Dependencies:</summary>

* libblkid1
* libc6
* libmount1
* libselinux1
* libsmartcols1

</details>

**losetup**

Set up and control loop devices

```
:~# losetup -h

Usage:
 losetup [options] [<loopdev>]
 losetup [options] -f | <loopdev> <file>

Set up and control loop devices.

Options:
 -a, --all                     list all used devices
 -d, --detach <loopdev>...     detach one or more devices
 -D, --detach-all              detach all used devices
 -f, --find                    find first unused device
 -c, --set-capacity <loopdev>  resize the device
 -j, --associated <file>       list all devices associated with <file>
 -L, --nooverlap               avoid possible conflict between devices

 -o, --offset <num>            start at offset <num> into file
     --sizelimit <num>         device is limited to <num> bytes of the file
 -b, --sector-size <num>       set the logical sector size to <num>
 -P, --partscan                create a partitioned loop device
 -r, --read-only               set up a read-only loop device
     --direct-io[=<on|off>]    open backing file with O_DIRECT
     --show                    print device name after setup (with -f)
 -v, --verbose                 verbose mode

 -J, --json                    use JSON --list output format
 -l, --list                    list info about all or specified (default)
 -n, --noheadings              don't print headings for --list output
 -O, --output <cols>           specify columns to output for --list
     --output-all              output all columns
     --raw                     use raw --list output format

 -h, --help                    display this help
 -V, --version                 display version

Available output columns:
         NAME  loop device name
    AUTOCLEAR  autoclear flag set
    BACK-FILE  device backing file
     BACK-INO  backing file inode number
 BACK-MAJ:MIN  backing file major:minor device number
      MAJ:MIN  loop device major:minor number
       OFFSET  offset from the beginning
     PARTSCAN  partscan flag set
           RO  read-only device
    SIZELIMIT  size limit of the file in bytes
          DIO  access backing file with direct-io
      LOG-SEC  logical sector size in bytes

For more details see losetup(8).
```

***

**mount**

Mount a filesystem

```
:~# mount -h

Usage:
 mount [-lhV]
 mount -a [options]
 mount [options] [--source] <source> | [--target] <directory>
 mount [options] <source> <directory>
 mount <operation> <mountpoint> [<target>]

Mount a filesystem.

Options:
 -a, --all               mount all filesystems mentioned in fstab
 -c, --no-canonicalize   don't canonicalize paths
 -f, --fake              dry run; skip the mount(2) syscall
 -F, --fork              fork off for each device (use with -a)
 -T, --fstab <path>      alternative file to /etc/fstab
 -i, --internal-only     don't call the mount.<type> helpers
 -l, --show-labels       show also filesystem labels
 -m, --mkdir[=<mode>]    alias to '-o X-mount.mkdir[=<mode>]'
 -n, --no-mtab           don't write to /etc/mtab
     --options-mode <mode>
                         what to do with options loaded from fstab
     --options-source <source>
                         mount options source
     --options-source-force
                         force use of options from fstab/mtab
 -o, --options <list>    comma-separated list of mount options
 -O, --test-opts <list>  limit the set of filesystems (use with -a)
 -r, --read-only         mount the filesystem read-only (same as -o ro)
 -t, --types <list>      limit the set of filesystem types
     --source <src>      explicitly specifies source (path, label, uuid)
     --target <target>   explicitly specifies mountpoint
     --target-prefix <path>
                         specifies path used for all mountpoints
 -v, --verbose           say what is being done
 -w, --rw, --read-write  mount the filesystem read-write (default)
 -N, --namespace <ns>    perform mount in another namespace

 -h, --help              display this help
 -V, --version           display version

Source:
 -L, --label <label>     synonym for LABEL=<label>
 -U, --uuid <uuid>       synonym for UUID=<uuid>
 LABEL=<label>           specifies device by filesystem label
 UUID=<uuid>             specifies device by filesystem UUID
 PARTLABEL=<label>       specifies device by partition label
 PARTUUID=<uuid>         specifies device by partition UUID
 ID=<id>                 specifies device by udev hardware ID
 <device>                specifies device by path
 <directory>             mountpoint for bind mounts (see --bind/rbind)
 <file>                  regular file for loopdev setup

Operations:
 -B, --bind              mount a subtree somewhere else (same as -o bind)
 -M, --move              move a subtree to some other place
 -R, --rbind             mount a subtree and all submounts somewhere else
 --make-shared           mark a subtree as shared
 --make-slave            mark a subtree as slave
 --make-private          mark a subtree as private
 --make-unbindable       mark a subtree as unbindable
 --make-rshared          recursively mark a whole subtree as shared
 --make-rslave           recursively mark a whole subtree as slave
 --make-rprivate         recursively mark a whole subtree as private
 --make-runbindable      recursively mark a whole subtree as unbindable

For more details see mount(8).
```

***

**swapoff**

Enable/disable devices and files for paging and swapping

```
:~# swapoff -h

Usage:
 swapoff [options] [<spec>]

Disable devices and files for paging and swapping.

Options:
 -a, --all              disable all swaps from /proc/swaps
 -v, --verbose          verbose mode

 -h, --help             display this help
 -V, --version          display version

The <spec> parameter:
 -L <label>             LABEL of device to be used
 -U <uuid>              UUID of device to be used
 LABEL=<label>          LABEL of device to be used
 UUID=<uuid>            UUID of device to be used
 <device>               name of device to be used
 <file>                 name of file to be used

For more details see swapoff(8).
```

***

**swapon**

Enable/disable devices and files for paging and swapping

```
:~# swapon -h

Usage:
 swapon [options] [<spec>]

Enable devices and files for paging and swapping.

Options:
 -a, --all                enable all swaps from /etc/fstab
 -d, --discard[=<policy>] enable swap discards, if supported by device
 -e, --ifexists           silently skip devices that do not exist
 -f, --fixpgsz            reinitialize the swap space if necessary
 -o, --options <list>     comma-separated list of swap options
 -p, --priority <prio>    specify the priority of the swap device
 -s, --summary            display summary about used swap devices (DEPRECATED)
     --show[=<columns>]   display summary in definable table
     --noheadings         don't print table heading (with --show)
     --raw                use the raw output format (with --show)
     --bytes              display swap size in bytes in --show output
 -v, --verbose            verbose mode

 -h, --help               display this help
 -V, --version            display version

The <spec> parameter:
 -L <label>             synonym for LABEL=<label>
 -U <uuid>              synonym for UUID=<uuid>
 LABEL=<label>          specifies device by swap area label
 UUID=<uuid>            specifies device by swap area UUID
 PARTLABEL=<label>      specifies device by partition label
 PARTUUID=<uuid>        specifies device by partition UUID
 <device>               name of device to be used
 <file>                 name of file to be used

Available discard policy types (for --discard):
 once    : only single-time area discards are issued
 pages   : freed pages are discarded before they are reused
If no policy is selected, both discard types are enabled (default).

Available output columns:
 NAME   device file or partition path
 TYPE   type of the device
 SIZE   size of the swap area
 USED   bytes in use
 PRIO   swap priority
 UUID   swap uuid
 LABEL  swap label

For more details see swapon(8).
```

***

**umount**

Unmount filesystems

```
:~# umount -h

Usage:
 umount [-hV]
 umount -a [options]
 umount [options] <source> | <directory>

Unmount filesystems.

Options:
 -a, --all               unmount all filesystems
 -A, --all-targets       unmount all mountpoints for the given device in the
                           current namespace
 -c, --no-canonicalize   don't canonicalize paths
 -d, --detach-loop       if mounted loop device, also free this loop device
     --fake              dry run; skip the umount(2) syscall
 -f, --force             force unmount (in case of an unreachable NFS system)
 -i, --internal-only     don't call the umount.<type> helpers
 -n, --no-mtab           don't write to /etc/mtab
 -l, --lazy              detach the filesystem now, clean up things later
 -O, --test-opts <list>  limit the set of filesystems (use with -a)
 -R, --recursive         recursively unmount a target with all its children
 -r, --read-only         in case unmounting fails, try to remount read-only
 -t, --types <list>      limit the set of filesystem types
 -v, --verbose           say what is being done
 -q, --quiet             suppress 'not mounted' error messages
 -N, --namespace <ns>    perform umount in another namespace

 -h, --help              display this help
 -V, --version           display version

For more details see umount(8).
```

***

#### rfkill <a href="#rfkill" id="rfkill"></a>

rfkill is a simple tool for accessing the Linux rfkill device interface, which is used to enable and disable wireless networking devices, typically WLAN, Bluetooth and mobile broadband.

**Installed size:** `97 KB`\
**How to install:** `sudo apt install rfkill`

<details>

<summary>Dependencies:</summary>

* libc6
* libsmartcols1

</details>

**rfkill**

Tool for enabling and disabling wireless devices

```
:~# rfkill -h

Usage:
 rfkill [options] command [identifier ...]

Tool for enabling and disabling wireless devices.

Options:
 -J, --json             use JSON output format
 -n, --noheadings       don't print headings
 -o, --output <list>    define which output columns to use
     --output-all       output all columns
 -r, --raw              use the raw output format

 -h, --help             display this help
 -V, --version          display version

Available output columns:
 DEVICE      kernel device name
 ID          device identifier value
 TYPE        device type name that can be used as identifier
 TYPE-DESC   device type description
 SOFT        status of software block
 HARD        status of hardware block

Commands:
 help
 event
 list   [identifier]
 block   identifier
 unblock identifier
 toggle  identifier

For more details see rfkill(8).
```

***

#### util-linux <a href="#util-linux" id="util-linux"></a>

This package contains a number of important utilities, most of which are oriented towards maintenance of your system. Some of the more important utilities included in this package allow you to view kernel messages, create new filesystems, view block device information, interface with real time clock, etc.

**Installed size:** `4.85 MB`\
**How to install:** `sudo apt install util-linux`

<details>

<summary>Dependencies:</summary>

* libblkid1
* libc6
* libcap-ng0
* libcrypt1
* libmount1
* libpam0g
* libselinux1
* libsmartcols1
* libsystemd0
* libtinfo6
* libudev1
* libuuid1
* util-linux-extra
* zlib1g

</details>

**addpart**

Tell the kernel about the existence of a partition

```
:~# addpart -h

Usage:
 addpart <disk device> <partition number> <start> <length>

Tell the kernel about the existence of a specified partition.

Options:
 -h, --help     display this help
 -V, --version  display version

For more details see addpart(8).
```

***

**agetty**

Alternative Linux getty

```
:~# agetty --help

Usage:
 agetty [options] <line> [<baud_rate>,...] [<termtype>]
 agetty [options] <baud_rate>,... <line> [<termtype>]

Open a terminal and set its mode.

Options:
 -8, --8bits                assume 8-bit tty
 -a, --autologin <user>     login the specified user automatically
 -c, --noreset              do not reset control mode
 -E, --remote               use -r <hostname> for login(1)
 -f, --issue-file <list>    display issue files or directories
     --show-issue           display issue file and exit
 -h, --flow-control         enable hardware flow control
 -H, --host <hostname>      specify login host
 -i, --noissue              do not display issue file
 -I, --init-string <string> set init string
 -J  --noclear              do not clear the screen before prompt
 -l, --login-program <file> specify login program
 -L, --local-line[=<mode>]  control the local line flag
 -m, --extract-baud         extract baud rate during connect
 -n, --skip-login           do not prompt for login
 -N  --nonewline            do not print a newline before issue
 -o, --login-options <opts> options that are passed to login
 -p, --login-pause          wait for any key before the login
 -r, --chroot <dir>         change root to the directory
 -R, --hangup               do virtually hangup on the tty
 -s, --keep-baud            try to keep baud rate after break
 -t, --timeout <number>     login process timeout
 -U, --detect-case          detect uppercase terminal
 -w, --wait-cr              wait carriage-return
     --nohints              do not print hints
     --nohostname           no hostname at all will be shown
     --long-hostname        show full qualified hostname
     --erase-chars <string> additional backspace chars
     --kill-chars <string>  additional kill chars
     --chdir <directory>    chdir before the login
     --delay <number>       sleep seconds before prompt
     --nice <number>        run login with this priority
     --reload               reload prompts on running agetty instances
     --list-speeds          display supported baud rates
     --help                 display this help
     --version              display version

For more details see agetty(8).
```

***

**blkdiscard**

Discard sectors on a device

```
:~# blkdiscard -h

Usage:
 blkdiscard [options] <device>

Discard the content of sectors on a device.

Options:
 -f, --force         disable all checking
 -o, --offset <num>  offset in bytes to discard from
 -l, --length <num>  length of bytes to discard from the offset
 -p, --step <num>    size of the discard iterations within the offset
 -s, --secure        perform secure discard
 -z, --zeroout       zero-fill rather than discard
 -v, --verbose       print aligned length and offset

 -h, --help          display this help
 -V, --version       display version

Arguments:
 <num> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

For more details see blkdiscard(8).
```

***

**blkid**

Locate/print block device attributes

```
:~# blkid -h

Usage:
 blkid --label <label> | --uuid <uuid>

 blkid [--cache-file <file>] [-ghlLv] [--output <format>] [--match-tag <tag>] 
       [--match-token <token>] [<dev> ...]

 blkid -p [--match-tag <tag>] [--offset <offset>] [--size <size>] 
       [--output <format>] <dev> ...

 blkid -i [--match-tag <tag>] [--output <format>] <dev> ...

Options:
 -c, --cache-file <file>    read from <file> instead of reading from the default
                              cache file (-c /dev/null means no cache)
 -d, --no-encoding          don't encode non-printing characters
 -g, --garbage-collect      garbage collect the blkid cache
 -o, --output <format>      output format; can be one of:
                              value, device, export or full; (default: full)
 -k, --list-filesystems     list all known filesystems/RAIDs and exit
 -s, --match-tag <tag>      show specified tag(s) (default show all tags)
 -t, --match-token <token>  find device with a specific token (NAME=value pair)
 -l, --list-one             look up only first device with token specified by -t
 -L, --label <label>        convert LABEL to device name
 -U, --uuid <uuid>          convert UUID to device name

Low-level probing options:
 -p, --probe                low-level superblocks probing (bypass cache)
 -i, --info                 gather information about I/O limits
 -H, --hint <value>         set hint for probing function
 -S, --size <size>          overwrite device size
 -O, --offset <offset>      probe at the given offset
 -u, --usages <list>        filter by "usage" (e.g. -u filesystem,raid)
 -n, --match-types <list>   filter by filesystem type (e.g. -n vfat,ext3)
 -D, --no-part-details      don't print info from partition table

 -h, --help                 display this help
 -V, --version              display version

Arguments:
 <size> and <offset> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

 <dev> specify device(s) to probe (default: all devices)

For more details see blkid(8).
```

***

**blkzone**

Run zone command on a device

```
:~# blkzone -h

Usage:
 blkzone <command> [options] <device>

Run zone command on the given block device.

Commands:
 report       Report zone information about the given device
 capacity     Report sum of zone capacities for the given device
 reset        Reset a range of zones.
 open         Open a range of zones.
 close        Close a range of zones.
 finish       Set a range of zones to Full.

Options:
 -o, --offset <sector>  start sector of zone to act (in 512-byte sectors)
 -l, --length <sectors> maximum sectors to act (in 512-byte sectors)
 -c, --count <number>   maximum number of zones
 -f, --force            enforce on block devices used by the system
 -v, --verbose          display more details

 -h, --help             display this help
 -V, --version          display version

Arguments:
 <sector> and <sectors> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

For more details see blkzone(8).
```

***

**blockdev**

Call block device ioctls from the command line

```
:~# blockdev -h

Usage:
 blockdev [-v|-q] commands devices
 blockdev --report [devices]
 blockdev -h|-V

Call block device ioctls from the command line.

Options:
 -q             quiet mode
 -v             verbose mode
     --report   print report for specified (or all) devices

 -h, --help     display this help
 -V, --version  display version

Available commands:
 --getsz                   get size in 512-byte sectors
 --setro                   set read-only
 --setrw                   set read-write
 --getro                   get read-only
 --getdiscardzeroes        get discard zeroes support status
 --getss                   get logical block (sector) size
 --getpbsz                 get physical block (sector) size
 --getiomin                get minimum I/O size
 --getioopt                get optimal I/O size
 --getalignoff             get alignment offset in bytes
 --getmaxsect              get max sectors per request
 --getbsz                  get blocksize
 --setbsz <bytes>          set blocksize on file descriptor opening the block device
 --getsize                 get 32-bit sector count (deprecated, use --getsz)
 --getsize64               get size in bytes
 --setra <sectors>         set readahead
 --getra                   get readahead
 --setfra <sectors>        set filesystem readahead
 --getfra                  get filesystem readahead
 --flushbufs               flush buffers
 --rereadpt                reread partition table

For more details see blockdev(8).
```

***

**chcpu**

Configure CPUs

```
:~# chcpu -h

Usage:
 chcpu [options]

Configure CPUs in a multi-processor system.

Options:
 -e, --enable <cpu-list>       enable cpus
 -d, --disable <cpu-list>      disable cpus
 -c, --configure <cpu-list>    configure cpus
 -g, --deconfigure <cpu-list>  deconfigure cpus
 -p, --dispatch <mode>         set dispatching mode
 -r, --rescan                  trigger rescan of cpus
 -h, --help                    display this help
 -V, --version                 display version

For more details see chcpu(8).
```

***

**chmem**

Configure memory

```
:~# chmem -h

Usage:
 chmem [options] [SIZE|RANGE|BLOCKRANGE]

Set a particular size or range of memory online or offline.

Options:
 -e, --enable       enable memory
 -d, --disable      disable memory
 -b, --blocks       use memory blocks
 -z, --zone <name>  select memory zone (see below)
 -v, --verbose      verbose output
 -h, --help         display this help
 -V, --version      display version

Supported zones:
 DMA
 DMA32
 Normal
 Highmem
 Movable
 Device

For more details see chmem(8).
```

***

**choom**

Display and adjust OOM-killer score.

```
:~# choom -h

Usage:
 choom [options] -p pid
 choom [options] -n number -p pid
 choom [options] -n number [--] command [args...]]

Display and adjust OOM-killer score.

Options:
 -n, --adjust <num>     specify the adjust score value
 -p, --pid <num>        process ID

 -h, --help             display this help
 -V, --version          display version

For more details see choom(1).
```

***

**chrt**

Manipulate the real-time attributes of a process

```
:~# chrt -h
Show or change the real-time scheduling attributes of a process.

Set policy:
 chrt [options] <priority> <command> [<arg>...]
 chrt [options] --pid <priority> <pid>

Get policy:
 chrt [options] -p <pid>

Policy options:
 -b, --batch          set policy to SCHED_BATCH
 -d, --deadline       set policy to SCHED_DEADLINE
 -f, --fifo           set policy to SCHED_FIFO
 -i, --idle           set policy to SCHED_IDLE
 -o, --other          set policy to SCHED_OTHER
 -r, --rr             set policy to SCHED_RR (default)

Scheduling options:
 -R, --reset-on-fork       set reset-on-fork flag
 -T, --sched-runtime <ns>  runtime parameter for DEADLINE
 -P, --sched-period <ns>   period parameter for DEADLINE
 -D, --sched-deadline <ns> deadline parameter for DEADLINE

Other options:
 -a, --all-tasks      operate on all the tasks (threads) for a given pid
 -m, --max            show min and max valid priorities
 -p, --pid            operate on existing given pid
 -v, --verbose        display status information

 -h, --help           display this help
 -V, --version        display version

For more details see chrt(1).
```

***

**ctrlaltdel**

Set the function of the Ctrl-Alt-Del combination

```
:~# ctrlaltdel -h

Usage:
 ctrlaltdel hard|soft

Set the function of the Ctrl-Alt-Del combination.

Options:
 -h, --help     display this help
 -V, --version  display version

For more details see ctrlaltdel(8).
```

***

**delpart**

Tell the kernel to forget about a partition

```
:~# delpart -h

Usage:
 delpart <disk device> <partition number>

Tell the kernel to forget about a specified partition.

Options:
 -h, --help     display this help
 -V, --version  display version

For more details see delpart(8).
```

***

**dmesg**

Print or control the kernel ring buffer

```
:~# dmesg -h

Usage:
 dmesg [options]

Display or control the kernel ring buffer.

Options:
 -C, --clear                 clear the kernel ring buffer
 -c, --read-clear            read and clear all messages
 -D, --console-off           disable printing messages to console
 -E, --console-on            enable printing messages to console
 -F, --file <file>           use the file instead of the kernel log buffer
 -f, --facility <list>       restrict output to defined facilities
 -H, --human                 human readable output
 -J, --json                  use JSON output format
 -k, --kernel                display kernel messages
 -L, --color[=<when>]        colorize messages (auto, always or never)
                               colors are enabled by default
 -l, --level <list>          restrict output to defined levels
 -n, --console-level <level> set level of messages printed to console
 -P, --nopager               do not pipe output into a pager
 -p, --force-prefix          force timestamp output on each line of multi-line messages
 -r, --raw                   print the raw message buffer
     --noescape              don't escape unprintable character
 -S, --syslog                force to use syslog(2) rather than /dev/kmsg
 -s, --buffer-size <size>    buffer size to query the kernel ring buffer
 -u, --userspace             display userspace messages
 -w, --follow                wait for new messages
 -W, --follow-new            wait and print only new messages
 -x, --decode                decode facility and level to readable string
 -d, --show-delta            show time delta between printed messages
 -e, --reltime               show local time and time delta in readable format
 -T, --ctime                 show human-readable timestamp (may be inaccurate!)
 -t, --notime                don't show any timestamp with messages
     --time-format <format>  show timestamp using the given format:
                               [delta|reltime|ctime|notime|iso]
Suspending/resume will make ctime and iso timestamps inaccurate.
     --since <time>          display the lines since the specified time
     --until <time>          display the lines until the specified time

 -h, --help                  display this help
 -V, --version               display version

Supported log facilities:
    kern - kernel messages
    user - random user-level messages
    mail - mail system
  daemon - system daemons
    auth - security/authorization messages
  syslog - messages generated internally by syslogd
     lpr - line printer subsystem
    news - network news subsystem

Supported log levels (priorities):
   emerg - system is unusable
   alert - action must be taken immediately
    crit - critical conditions
     err - error conditions
    warn - warning conditions
  notice - normal but significant condition
    info - informational
   debug - debug-level messages

For more details see dmesg(1).
```

***

**fallocate**

Preallocate or deallocate space to a file

```
:~# fallocate -h

Usage:
 fallocate [options] <filename>

Preallocate space to, or deallocate space from a file.

Options:
 -c, --collapse-range remove a range from the file
 -d, --dig-holes      detect zeroes and replace with holes
 -i, --insert-range   insert a hole at range, shifting existing data
 -l, --length <num>   length for range operations, in bytes
 -n, --keep-size      maintain the apparent size of the file
 -o, --offset <num>   offset for range operations, in bytes
 -p, --punch-hole     replace a range with a hole (implies -n)
 -z, --zero-range     zero and ensure allocation of a range
 -x, --posix          use posix_fallocate(3) instead of fallocate(2)
 -v, --verbose        verbose mode

 -h, --help           display this help
 -V, --version        display version

Arguments:
 <num> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

For more details see fallocate(1).
```

***

**findfs**

Find a filesystem by label or UUID

```
:~# findfs -h

Usage:
 findfs [options] {LABEL,UUID,PARTUUID,PARTLABEL}=<value>

Find a filesystem by label or UUID.

Options:
 -h, --help     display this help
 -V, --version  display version

For more details see findfs(8).
```

***

**findmnt**

Find a filesystem

```
:~# findmnt -h

Usage:
 findmnt [options]
 findmnt [options] <device> | <mountpoint>
 findmnt [options] <device> <mountpoint>
 findmnt [options] [--source <device>] [--target <path> | --mountpoint <dir>]

Find a (mounted) filesystem.

Options:
 -s, --fstab            search in static table of filesystems
 -m, --mtab             search in table of mounted filesystems
                          (includes user space mount options)
 -k, --kernel           search in kernel table of mounted
                          filesystems (default)

 -p, --poll[=<list>]    monitor changes in table of mounted filesystems
 -w, --timeout <num>    upper limit in milliseconds that --poll will block

 -A, --all              disable all built-in filters, print all filesystems
 -a, --ascii            use ASCII chars for tree formatting
 -b, --bytes            print sizes in bytes rather than in human readable format
 -C, --nocanonicalize   don't canonicalize when comparing paths
 -c, --canonicalize     canonicalize printed paths
 -D, --df               imitate the output of df(1)
 -d, --direction <word> direction of search, 'forward' or 'backward'
 -e, --evaluate         convert tags (LABEL,UUID,PARTUUID,PARTLABEL) 
                          to device names
 -F, --tab-file <path>  alternative file for -s, -m or -k options
 -f, --first-only       print the first found filesystem only
 -i, --invert           invert the sense of matching
 -J, --json             use JSON output format
 -l, --list             use list format output
 -N, --task <tid>       use alternative namespace (/proc/<tid>/mountinfo file)
 -n, --noheadings       don't print column headings
 -O, --options <list>   limit the set of filesystems by mount options
 -o, --output <list>    the output columns to be shown
     --output-all       output all available columns
 -P, --pairs            use key="value" output format
     --pseudo           print only pseudo-filesystems
     --shadowed         print only filesystems over-mounted by another filesystem
 -R, --submounts        print all submounts for the matching filesystems
 -r, --raw              use raw output format
     --real             print only real filesystems
 -S, --source <string>  the device to mount (by name, maj:min, 
                          LABEL=, UUID=, PARTUUID=, PARTLABEL=)
 -T, --target <path>    the path to the filesystem to use
     --tree             enable tree format output if possible
 -M, --mountpoint <dir> the mountpoint directory
 -t, --types <list>     limit the set of filesystems by FS types
 -U, --uniq             ignore filesystems with duplicate target
 -u, --notruncate       don't truncate text in columns
 -v, --nofsroot         don't print [/dir] for bind or btrfs mounts
 -y, --shell            use column names to be usable as shell variable identifiers

 -x, --verify           verify mount table content (default is fstab)
     --verbose          print more details
     --vfs-all          print all VFS options

 -h, --help             display this help
 -V, --version          display version

Available output columns:
      ACTION  action detected by --poll
       AVAIL  filesystem size available
        FREQ  dump(8) period in days [fstab only]
      FSROOT  filesystem root
      FSTYPE  filesystem type
  FS-OPTIONS  FS specific mount options
          ID  mount ID
       LABEL  filesystem label
     MAJ:MIN  major:minor device number
 OLD-OPTIONS  old mount options saved by --poll
  OLD-TARGET  old mountpoint saved by --poll
     OPTIONS  all mount options
  OPT-FIELDS  optional mount fields
      PARENT  mount parent ID
   PARTLABEL  partition label
    PARTUUID  partition UUID
      PASSNO  pass number on parallel fsck(8) [fstab only]
 PROPAGATION  VFS propagation flags
        SIZE  filesystem size
      SOURCE  source device
     SOURCES  all possible source devices
      TARGET  mountpoint
         TID  task ID
        USED  filesystem size used
        USE%  filesystem use percentage
        UUID  filesystem UUID
 VFS-OPTIONS  VFS specific mount options

For more details see findmnt(8).
```

***

**flock**

Manage locks from shell scripts

```
:~# flock -h

Usage:
 flock [options] <file>|<directory> <command> [<argument>...]
 flock [options] <file>|<directory> -c <command>
 flock [options] <file descriptor number>

Manage file locks from shell scripts.

Options:
 -s, --shared             get a shared lock
 -x, --exclusive          get an exclusive lock (default)
 -u, --unlock             remove a lock
 -n, --nonblock           fail rather than wait
 -w, --timeout <secs>     wait for a limited amount of time
 -E, --conflict-exit-code <number>  exit code after conflict or timeout
 -o, --close              close file descriptor before running command
 -c, --command <command>  run a single command string through the shell
 -F, --no-fork            execute command without forking
     --verbose            increase verbosity

 -h, --help               display this help
 -V, --version            display version

For more details see flock(1).
```

***

**fsck**

Check and repair a Linux filesystem

```
:~# fsck --help

Usage:
 fsck [options] -- [fs-options] [<filesystem> ...]

Check and repair a Linux filesystem.

Options:
 -A         check all filesystems
 -C [<fd>]  display progress bar; file descriptor is for GUIs
 -l         lock the device to guarantee exclusive access
 -M         do not check mounted filesystems
 -N         do not execute, just show what would be done
 -P         check filesystems in parallel, including root
 -R         skip root filesystem; useful only with '-A'
 -r [<fd>]  report statistics for each device checked;
            file descriptor is for GUIs
 -s         serialize the checking operations
 -T         do not show the title on startup
 -t <type>  specify filesystem types to be checked;
            <type> is allowed to be a comma-separated list
 -V         explain what is being done

 -?, --help     display this help
     --version  display version

See the specific fsck.* commands for available fs-options.
For more details see fsck(8).
```

***

**fsck.cramfs**

Fsck compressed ROM file system

```
:~# fsck.cramfs -h

Usage:
 fsck.cramfs [options] <file>

Check and repair a compressed ROM filesystem.

Options:
 -a                       for compatibility only, ignored
 -v, --verbose            be more verbose
 -y                       for compatibility only, ignored
 -b, --blocksize <size>   use this blocksize, defaults to page size
     --extract[=<dir>]    test uncompression, optionally extract into <dir>

 -h, --help               display this help
 -V, --version            display version

For more details see fsck.cramfs(8).
```

***

**fsck.minix**

Check consistency of Minix filesystem

```
:~# fsck.minix -h

Usage:
 fsck.minix [options] <device>

Check the consistency of a Minix filesystem.

Options:
 -l, --list       list all filenames
 -a, --auto       automatic repair
 -r, --repair     interactive repair
 -v, --verbose    be verbose
 -s, --super      output super-block information
 -m, --uncleared  activate mode not cleared warnings
 -f, --force      force check

 -h, --help       display this help
 -V, --version    display version

For more details see fsck.minix(8).
```

***

**fsfreeze**

Suspend access to a filesystem (Ext3/4, ReiserFS, JFS, XFS)

```
:~# fsfreeze -h

Usage:
 fsfreeze [options] <mountpoint>

Suspend access to a filesystem.

Options:
 -f, --freeze      freeze the filesystem
 -u, --unfreeze    unfreeze the filesystem

 -h, --help        display this help
 -V, --version     display version

For more details see fsfreeze(8).
```

***

**fstrim**

Discard unused blocks on a mounted filesystem

```
:~# fstrim -h

Usage:
 fstrim [options] <mount point>

Discard unused blocks on a mounted filesystem.

Options:
 -a, --all                trim mounted filesystems
 -A, --fstab              trim filesystems from /etc/fstab
 -I, --listed-in <list>   trim filesystems listed in specified files
 -o, --offset <num>       the offset in bytes to start discarding from
 -l, --length <num>       the number of bytes to discard
 -m, --minimum <num>      the minimum extent length to discard
 -v, --verbose            print number of discarded bytes
     --quiet-unsupported  suppress error messages if trim unsupported
 -n, --dry-run            does everything, but trim

 -h, --help          display this help
 -V, --version       display version

Arguments:
 <num> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

For more details see fstrim(8).
```

***

**getopt**

Parse command options (enhanced)

```
:~# getopt -h

Usage:
 getopt <optstring> <parameters>
 getopt [options] [--] <optstring> <parameters>
 getopt [options] -o|--options <optstring> [options] [--] <parameters>

Parse command options.

Options:
 -a, --alternative             allow long options starting with single -
 -l, --longoptions <longopts>  the long options to be recognized
 -n, --name <progname>         the name under which errors are reported
 -o, --options <optstring>     the short options to be recognized
 -q, --quiet                   disable error reporting by getopt(3)
 -Q, --quiet-output            no normal output
 -s, --shell <shell>           set quoting conventions to those of <shell>
 -T, --test                    test for getopt(1) version
 -u, --unquoted                do not quote the output

 -h, --help                    display this help
 -V, --version                 display version

For more details see getopt(1).
```

***

**getty**

Alternative Linux getty

```
:~# getty --help

Usage:
 getty [options] <line> [<baud_rate>,...] [<termtype>]
 getty [options] <baud_rate>,... <line> [<termtype>]

Open a terminal and set its mode.

Options:
 -8, --8bits                assume 8-bit tty
 -a, --autologin <user>     login the specified user automatically
 -c, --noreset              do not reset control mode
 -E, --remote               use -r <hostname> for login(1)
 -f, --issue-file <list>    display issue files or directories
     --show-issue           display issue file and exit
 -h, --flow-control         enable hardware flow control
 -H, --host <hostname>      specify login host
 -i, --noissue              do not display issue file
 -I, --init-string <string> set init string
 -J  --noclear              do not clear the screen before prompt
 -l, --login-program <file> specify login program
 -L, --local-line[=<mode>]  control the local line flag
 -m, --extract-baud         extract baud rate during connect
 -n, --skip-login           do not prompt for login
 -N  --nonewline            do not print a newline before issue
 -o, --login-options <opts> options that are passed to login
 -p, --login-pause          wait for any key before the login
 -r, --chroot <dir>         change root to the directory
 -R, --hangup               do virtually hangup on the tty
 -s, --keep-baud            try to keep baud rate after break
 -t, --timeout <number>     login process timeout
 -U, --detect-case          detect uppercase terminal
 -w, --wait-cr              wait carriage-return
     --nohints              do not print hints
     --nohostname           no hostname at all will be shown
     --long-hostname        show full qualified hostname
     --erase-chars <string> additional backspace chars
     --kill-chars <string>  additional kill chars
     --chdir <directory>    chdir before the login
     --delay <number>       sleep seconds before prompt
     --nice <number>        run login with this priority
     --reload               reload prompts on running agetty instances
     --list-speeds          display supported baud rates
     --help                 display this help
     --version              display version

For more details see agetty(8).
```

***

**hardlink**

Link multiple copies of a file

```
:~# hardlink -h

Usage:
 hardlink [options] <directory>|<file> ...

Consolidate duplicate files using hardlinks.

Options:
 -v, --verbose              verbose output (repeat for more verbosity)
 -q, --quiet                quiet mode - don't print anything
 -n, --dry-run              don't actually link anything
 -y, --method <name>        file content comparison method
 -f, --respect-name         filenames have to be identical
 -p, --ignore-mode          ignore changes of file mode
 -o, --ignore-owner         ignore owner changes
 -t, --ignore-time          ignore timestamps (when testing for equality)
 -c, --content              compare only file contents, same as -pot
 -X, --respect-xattrs       respect extended attributes
     --reflink[=<when>]     create clone/CoW copies (auto, always, never)
     --skip-reflinks        skip already cloned files (enabled on --reflink)
 -m, --maximize             maximize the hardlink count, remove the file with
                              lowest hardlink count
 -M, --minimize             reverse the meaning of -m
 -O, --keep-oldest          keep the oldest file of multiple equal files
                              (lower precedence than minimize/maximize)
 -x, --exclude <regex>      regular expression to exclude files
 -i, --include <regex>      regular expression to include files/dirs
 -s, --minimum-size <size>  minimum size for files.
 -S, --maximum-size <size>  maximum size for files.
 -b, --io-size <size>       I/O buffer size for file reading (speedup, using more RAM)
 -r, --cache-size <size>    memory limit for cached file content data

 -h, --help                 display this help
 -V, --version              display version

For more details see hardlink(1).
```

***

**i386**

Change reported architecture in new program environment and/or set personality flags

```
:~# i386 -h

Usage:
 i386 [options] [<program> [<argument>...]]

Change the reported architecture and set personality flags.

Options:
 -B, --32bit              turns on ADDR_LIMIT_32BIT
 -F, --fdpic-funcptrs     makes function pointers point to descriptors
 -I, --short-inode        turns on SHORT_INODE
 -L, --addr-compat-layout changes the way virtual memory is allocated
 -R, --addr-no-randomize  disables randomization of the virtual address space
 -S, --whole-seconds      turns on WHOLE_SECONDS
 -T, --sticky-timeouts    turns on STICKY_TIMEOUTS
 -X, --read-implies-exec  turns on READ_IMPLIES_EXEC
 -Z, --mmap-page-zero     turns on MMAP_PAGE_ZERO
 -3, --3gb                limits the used address space to a maximum of 3 GB
     --4gb                ignored (for backward compatibility only)
     --uname-2.6          turns on UNAME26
 -v, --verbose            say what options are being switched on

 -h, --help               display this help
 -V, --version            display version

For more details see setarch(8).
```

***

**ionice**

Set or get process I/O scheduling class and priority

```
:~# ionice -h

Usage:
 ionice [options] -p <pid>...
 ionice [options] -P <pgid>...
 ionice [options] -u <uid>...
 ionice [options] <command>

Show or change the I/O-scheduling class and priority of a process.

Options:
 -c, --class <class>    name or number of scheduling class,
                          0: none, 1: realtime, 2: best-effort, 3: idle
 -n, --classdata <num>  priority (0..7) in the specified scheduling class,
                          only for the realtime and best-effort classes
 -p, --pid <pid>...     act on these already running processes
 -P, --pgid <pgrp>...   act on already running processes in these groups
 -t, --ignore           ignore failures
 -u, --uid <uid>...     act on already running processes owned by these users

 -h, --help             display this help
 -V, --version          display version

For more details see ionice(1).
```

***

**ipcmk**

Make various IPC resources

```
:~# ipcmk -h

Usage:
 ipcmk [options]

Create various IPC resources.

Options:
 -M, --shmem <size>       create shared memory segment of size <size>
 -S, --semaphore <number> create semaphore array with <number> elements
 -Q, --queue              create message queue
 -p, --mode <mode>        permission for the resource (default is 0644)

 -h, --help               display this help
 -V, --version            display version

Arguments:
 <size> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

For more details see ipcmk(1).
```

***

**ipcrm**

Remove certain IPC resources

```
:~# ipcrm -h

Usage:
 ipcrm [options]
 ipcrm shm|msg|sem <id>...

Remove certain IPC resources.

Options:
 -m, --shmem-id <id>        remove shared memory segment by id
 -M, --shmem-key <key>      remove shared memory segment by key
 -q, --queue-id <id>        remove message queue by id
 -Q, --queue-key <key>      remove message queue by key
 -s, --semaphore-id <id>    remove semaphore by id
 -S, --semaphore-key <key>  remove semaphore by key
 -a, --all[=shm|msg|sem]    remove all (in the specified category)
 -v, --verbose              explain what is being done

 -h, --help                 display this help
 -V, --version              display version

For more details see ipcrm(1).
```

***

**ipcs**

Show information on IPC facilities

```
:~# ipcs -h

Usage:
 ipcs [resource-option...] [output-option]
 ipcs -m|-q|-s -i <id>

Show information on IPC facilities.

Options:
 -i, --id <id>  print details on resource identified by <id>
 -h, --help     display this help
 -V, --version  display version

Resource options:
 -m, --shmems      shared memory segments
 -q, --queues      message queues
 -s, --semaphores  semaphores
 -a, --all         all (default)

Output options:
 -t, --time        show attach, detach and change times
 -p, --pid         show PIDs of creator and last operator
 -c, --creator     show creator and owner
 -l, --limits      show resource limits
 -u, --summary     show status summary
     --human       show sizes in human-readable format
 -b, --bytes       show sizes in bytes

For more details see ipcs(1).
```

***

**isosize**

Output the length of an iso9660 filesystem

```
:~# isosize -h

Usage:
 isosize [options] <iso9660_image_file> ...

Show the length of an ISO-9660 filesystem.

Options:
 -d, --divisor=<number>  divide the amount of bytes by <number>
 -x, --sectors           show sector count and size
 -h, --help              display this help
 -V, --version           display version

For more details see isosize(8).
```

***

**last**

Show a listing of last logged in users

```
:~# last -h

Usage:
 last [options] [<username>...] [<tty>...]

Show a listing of last logged in users.

Options:
 -<number>            how many lines to show
 -a, --hostlast       display hostnames in the last column
 -d, --dns            translate the IP number back into a hostname
 -f, --file <file>    use a specific file instead of /var/log/wtmp
 -F, --fulltimes      print full login and logout times and dates
 -i, --ip             display IP numbers in numbers-and-dots notation
 -n, --limit <number> how many lines to show
 -R, --nohostname     don't display the hostname field
 -s, --since <time>   display the lines since the specified time
 -t, --until <time>   display the lines until the specified time
 -p, --present <time> display who were present at the specified time
 -w, --fullnames      display full user and domain names
 -x, --system         display system shutdown entries and run level changes
     --time-format <format>  show timestamps in the specified <format>:
                               notime|short|full|iso

 -h, --help           display this help
 -V, --version        display version

For more details see last(1).
```

***

**lastb**

Show a listing of last logged in users

```
:~# lastb -h

Usage:
 lastb [options] [<username>...] [<tty>...]

Show a listing of last logged in users.

Options:
 -<number>            how many lines to show
 -a, --hostlast       display hostnames in the last column
 -d, --dns            translate the IP number back into a hostname
 -f, --file <file>    use a specific file instead of /var/log/btmp
 -F, --fulltimes      print full login and logout times and dates
 -i, --ip             display IP numbers in numbers-and-dots notation
 -n, --limit <number> how many lines to show
 -R, --nohostname     don't display the hostname field
 -s, --since <time>   display the lines since the specified time
 -t, --until <time>   display the lines until the specified time
 -p, --present <time> display who were present at the specified time
 -w, --fullnames      display full user and domain names
 -x, --system         display system shutdown entries and run level changes
     --time-format <format>  show timestamps in the specified <format>:
                               notime|short|full|iso

 -h, --help           display this help
 -V, --version        display version

For more details see last(1).
```

***

**ldattach**

Attach a line discipline to a serial line

```
:~# ldattach -h

Usage:
 ldattach [options] <ldisc> <device>

Attach a line discipline to a serial line.

Options:
 -d, --debug             print verbose messages to stderr
 -s, --speed <value>     set serial line speed
 -c, --intro-command <string> intro sent before ldattach
 -p, --pause <seconds>   pause between intro and ldattach
 -7, --sevenbits         set character size to 7 bits
 -8, --eightbits         set character size to 8 bits
 -n, --noparity          set parity to none
 -e, --evenparity        set parity to even
 -o, --oddparity         set parity to odd
 -1, --onestopbit        set stop bits to one
 -2, --twostopbits       set stop bits to two
 -i, --iflag [-]<iflag>  set input mode flag

 -h, --help              display this help
 -V, --version           display version

Known <ldisc> names:
  TTY           SLIP          MOUSE         PPP           STRIP       
  AX25          X25           6PACK         R3964         IRDA        
  HDLC          SYNC_PPP      SYNCPPP       HCI           GIGASET_M101
  M101          GIGASET       PPS           GSM0710     

Known <iflag> names:
  IGNBRK        BRKINT        IGNPAR        PARMRK        INPCK       
  ISTRIP        INLCR         IGNCR         ICRNL         IUCLC       
  IXON          IXANY         IXOFF         IMAXBEL       IUTF8       

For more details see ldattach(8).
```

***

**linux32**

Change reported architecture in new program environment and/or set personality flags

```
:~# linux32 -h

Usage:
 linux32 [options] [<program> [<argument>...]]

Change the reported architecture and set personality flags.

Options:
 -B, --32bit              turns on ADDR_LIMIT_32BIT
 -F, --fdpic-funcptrs     makes function pointers point to descriptors
 -I, --short-inode        turns on SHORT_INODE
 -L, --addr-compat-layout changes the way virtual memory is allocated
 -R, --addr-no-randomize  disables randomization of the virtual address space
 -S, --whole-seconds      turns on WHOLE_SECONDS
 -T, --sticky-timeouts    turns on STICKY_TIMEOUTS
 -X, --read-implies-exec  turns on READ_IMPLIES_EXEC
 -Z, --mmap-page-zero     turns on MMAP_PAGE_ZERO
 -3, --3gb                limits the used address space to a maximum of 3 GB
     --4gb                ignored (for backward compatibility only)
     --uname-2.6          turns on UNAME26
 -v, --verbose            say what options are being switched on

 -h, --help               display this help
 -V, --version            display version

For more details see setarch(8).
```

***

**linux64**

Change reported architecture in new program environment and/or set personality flags

```
:~# linux64 -h

Usage:
 linux64 [options] [<program> [<argument>...]]

Change the reported architecture and set personality flags.

Options:
 -B, --32bit              turns on ADDR_LIMIT_32BIT
 -F, --fdpic-funcptrs     makes function pointers point to descriptors
 -I, --short-inode        turns on SHORT_INODE
 -L, --addr-compat-layout changes the way virtual memory is allocated
 -R, --addr-no-randomize  disables randomization of the virtual address space
 -S, --whole-seconds      turns on WHOLE_SECONDS
 -T, --sticky-timeouts    turns on STICKY_TIMEOUTS
 -X, --read-implies-exec  turns on READ_IMPLIES_EXEC
 -Z, --mmap-page-zero     turns on MMAP_PAGE_ZERO
 -3, --3gb                limits the used address space to a maximum of 3 GB
     --4gb                ignored (for backward compatibility only)
     --uname-2.6          turns on UNAME26
 -v, --verbose            say what options are being switched on

 -h, --help               display this help
 -V, --version            display version

For more details see setarch(8).
```

***

**lsblk**

List block devices

```
:~# lsblk -h

Usage:
 lsblk [options] [<device> ...]

List information about block devices.

Options:
 -A, --noempty        don't print empty devices
 -D, --discard        print discard capabilities
 -E, --dedup <column> de-duplicate output by <column>
 -I, --include <list> show only devices with specified major numbers
 -J, --json           use JSON output format
 -M, --merge          group parents of sub-trees (usable for RAIDs, Multi-path)
 -O, --output-all     output all columns
 -P, --pairs          use key="value" output format
 -S, --scsi           output info about SCSI devices
 -T, --tree[=<column>] use tree format output
 -a, --all            print all devices
 -b, --bytes          print SIZE in bytes rather than in human readable format
 -d, --nodeps         don't print slaves or holders
 -e, --exclude <list> exclude devices by major number (default: RAM disks)
 -f, --fs             output info about filesystems
 -i, --ascii          use ascii characters only
 -l, --list           use list format output
 -m, --perms          output info about permissions
 -n, --noheadings     don't print headings
 -o, --output <list>  output columns
 -p, --paths          print complete device path
 -r, --raw            use raw output format
 -s, --inverse        inverse dependencies
 -t, --topology       output info about topology
 -w, --width <num>    specifies output width as number of characters
 -x, --sort <column>  sort output by <column>
 -y, --shell          use column names to be usable as shell variable identifiers
 -z, --zoned          print zone related information
     --sysroot <dir>  use specified directory as system root

 -h, --help           display this help
 -V, --version        display version

Available output columns:
    ALIGNMENT  alignment offset
     DISC-ALN  discard alignment offset
          DAX  dax-capable device
    DISC-GRAN  discard granularity
     DISC-MAX  discard max bytes
    DISC-ZERO  discard zeroes data
      FSAVAIL  filesystem size available
      FSROOTS  mounted filesystem roots
       FSSIZE  filesystem size
       FSTYPE  filesystem type
       FSUSED  filesystem size used
       FSUSE%  filesystem use percentage
        FSVER  filesystem version
        GROUP  group name
         HCTL  Host:Channel:Target:Lun for SCSI
      HOTPLUG  removable or hotplug device (usb, pcmcia, ...)
        KNAME  internal kernel device name
        LABEL  filesystem LABEL
      LOG-SEC  logical sector size
      MAJ:MIN  major:minor device number
       MIN-IO  minimum I/O size
         MODE  device node permissions
        MODEL  device identifier
         NAME  device name
       OPT-IO  optimal I/O size
        OWNER  user name
    PARTFLAGS  partition flags
    PARTLABEL  partition LABEL
     PARTTYPE  partition type code or UUID
 PARTTYPENAME  partition type name
     PARTUUID  partition UUID
         PATH  path to the device node
      PHY-SEC  physical sector size
       PKNAME  internal parent kernel device name
       PTTYPE  partition table type
       PTUUID  partition table identifier (usually UUID)
           RA  read-ahead of the device
         RAND  adds randomness
          REV  device revision
           RM  removable device
           RO  read-only device
         ROTA  rotational device
      RQ-SIZE  request queue size
        SCHED  I/O scheduler name
       SERIAL  disk serial number
         SIZE  size of the device
        START  partition start offset
        STATE  state of the device
   SUBSYSTEMS  de-duplicated chain of subsystems
   MOUNTPOINT  where the device is mounted
  MOUNTPOINTS  all locations where device is mounted
         TRAN  device transport type
         TYPE  device type
         UUID  filesystem UUID
       VENDOR  device vendor
        WSAME  write same max bytes
          WWN  unique storage identifier
        ZONED  zone model
      ZONE-SZ  zone size
   ZONE-WGRAN  zone write granularity
     ZONE-APP  zone append max bytes
      ZONE-NR  number of zones
    ZONE-OMAX  maximum number of open zones
    ZONE-AMAX  maximum number of active zones

For more details see lsblk(8).
```

***

**lscpu**

Display information about the CPU architecture

```
:~# lscpu -h

Usage:
 lscpu [options]

Display information about the CPU architecture.

Options:
 -a, --all               print both online and offline CPUs (default for -e)
 -b, --online            print online CPUs only (default for -p)
 -B, --bytes             print sizes in bytes rather than in human readable format
 -C, --caches[=<list>]   info about caches in extended readable format
 -c, --offline           print offline CPUs only
 -J, --json              use JSON for default or extended format
 -e, --extended[=<list>] print out an extended readable format
 -p, --parse[=<list>]    print out a parsable format
 -s, --sysroot <dir>     use specified directory as system root
 -x, --hex               print hexadecimal masks rather than lists of CPUs
 -y, --physical          print physical instead of logical IDs
     --output-all        print all available columns for -e, -p or -C

 -h, --help              display this help
 -V, --version           display version

Available output columns for -e or -p:
      BOGOMIPS  crude measurement of CPU speed
           CPU  logical CPU number
          CORE  logical core number
        SOCKET  logical socket number
       CLUSTER  logical cluster number
          NODE  logical NUMA node number
          BOOK  logical book number
        DRAWER  logical drawer number
         CACHE  shows how caches are shared between CPUs
  POLARIZATION  CPU dispatching mode on virtual hardware
       ADDRESS  physical address of a CPU
    CONFIGURED  shows if the hypervisor has allocated the CPU
        ONLINE  shows if Linux currently makes use of the CPU
           MHZ  shows the currently MHz of the CPU
      SCALMHZ%  shows scaling percentage of the CPU frequency
        MAXMHZ  shows the maximum MHz of the CPU
        MINMHZ  shows the minimum MHz of the CPU

Available output columns for -C:
      ALL-SIZE  size of all system caches
         LEVEL  cache level
          NAME  cache name
      ONE-SIZE  size of one cache
          TYPE  cache type
          WAYS  ways of associativity
  ALLOC-POLICY  allocation policy
  WRITE-POLICY  write policy
      PHY-LINE  number of physical cache line per cache t
          SETS  number of sets in the cache; set lines has the same cache index
 COHERENCY-SIZE  minimum amount of data in bytes transferred from memory to cache

For more details see lscpu(1).
```

***

**lsipc**

Show information on IPC facilities currently employed in the system

```
:~# lsipc -h

Usage:
 lsipc [options]

Show information on IPC facilities.

Resource options:
 -m, --shmems      shared memory segments
 -q, --queues      message queues
 -s, --semaphores  semaphores
 -g, --global      info about system-wide usage (may be used with -m, -q and -s)
 -i, --id <id>     print details on resource identified by <id>

Options:
     --noheadings         don't print headings
     --notruncate         don't truncate output
     --time-format=<type> display dates in short, full or iso format
 -b, --bytes              print SIZE in bytes rather than in human readable format
 -c, --creator            show creator and owner
 -e, --export             display in an export-able output format
 -J, --json               use the JSON output format
 -n, --newline            display each piece of information on a new line
 -l, --list               force list output format (for example with --id)
 -o, --output[=<list>]    define the columns to output
 -P, --numeric-perms      print numeric permissions (PERMS column)
 -r, --raw                display in raw mode
 -t, --time               show attach, detach and change times
 -y, --shell              use column names to be usable as shell variable identifiers

 -h, --help               display this help
 -V, --version            display version

Generic columns:
            KEY  Resource key
             ID  Resource ID
          OWNER  Owner's username or UID
          PERMS  Permissions
           CUID  Creator UID
          CUSER  Creator user
           CGID  Creator GID
         CGROUP  Creator group
            UID  User ID
           USER  User name
            GID  Group ID
          GROUP  Group name
          CTIME  Time of the last change

Shared-memory columns (--shmems):
           SIZE  Segment size
         NATTCH  Number of attached processes
         STATUS  Status
         ATTACH  Attach time
         DETACH  Detach time
        COMMAND  Creator command line
           CPID  PID of the creator
           LPID  PID of last user

Message-queue columns (--queues):
      USEDBYTES  Bytes used
           MSGS  Number of messages
           SEND  Time of last msg sent
           RECV  Time of last msg received
          LSPID  PID of the last msg sender
          LRPID  PID of the last msg receiver

Semaphore columns (--semaphores):
          NSEMS  Number of semaphores
          OTIME  Time of the last operation

Summary columns (--global):
       RESOURCE  Resource name
    DESCRIPTION  Resource description
          LIMIT  System-wide limit
           USED  Currently used
           USE%  Currently use percentage

For more details see lsipc(1).
```

***

**lslocks**

List local system locks

```
:~# lslocks -h

Usage:
 lslocks [options]

List local system locks.

Options:
 -b, --bytes            print SIZE in bytes rather than in human readable format
 -J, --json             use JSON output format
 -i, --noinaccessible   ignore locks without read permissions
 -n, --noheadings       don't print headings
 -o, --output <list>    define which output columns to use
     --output-all       output all columns
 -p, --pid <pid>        display only locks held by this process
 -r, --raw              use the raw output format
 -u, --notruncate       don't truncate text in columns

 -h, --help             display this help
 -V, --version          display version

Available output columns:
     COMMAND  command of the process holding the lock
         PID  PID of the process holding the lock
        TYPE  kind of lock
        SIZE  size of the lock
       INODE  inode number
     MAJ:MIN  major:minor device number
        MODE  lock access mode
           M  mandatory state of the lock: 0 (none), 1 (set)
       START  relative byte offset of the lock
         END  ending offset of the lock
        PATH  path of the locked file
     BLOCKER  PID of the process blocking the lock

For more details see lslocks(8).
```

***

**lslogins**

Display information about known users in the system

```
:~# lslogins -h

Usage:
 lslogins [options] [<username>]

Display information about known users in the system.

Options:
 -a, --acc-expiration     display info about passwords expiration
 -c, --colon-separate     display data in a format similar to /etc/passwd
 -e, --export             display in an export-able output format
 -f, --failed             display data about the users' last failed logins
 -G, --supp-groups        display information about groups
 -g, --groups=<groups>    display users belonging to a group in <groups>
 -L, --last               show info about the users' last login sessions
 -l, --logins=<logins>    display only users from <logins>
 -n, --newline            display each piece of information on a new line
     --noheadings         don't print headings
     --notruncate         don't truncate output
 -o, --output[=<list>]    define the columns to output
     --output-all         output all columns
 -p, --pwd                display information related to login by password.
 -r, --raw                display in raw mode
 -s, --system-accs        display system accounts
     --time-format=<type> display dates in short, full or iso format
 -u, --user-accs          display user accounts
 -y, --shell              use column names to be usable as shell variable identifiers
 -Z, --context            display SELinux contexts
 -z, --print0             delimit user entries with a nul character
     --wtmp-file <path>   set an alternate path for wtmp
     --btmp-file <path>   set an alternate path for btmp
     --lastlog <path>     set an alternate path for lastlog

 -h, --help               display this help
 -V, --version            display version

Available output columns:
           USER  user name
            UID  user ID
          GECOS  full user name
        HOMEDIR  home directory
          SHELL  login shell
        NOLOGIN  log in disabled by nologin(8) or pam_nologin(8)
       PWD-LOCK  password defined, but locked
      PWD-EMPTY  password not defined
       PWD-DENY  login by password disabled
     PWD-METHOD  password encryption method
          GROUP  primary group name
            GID  primary group ID
    SUPP-GROUPS  supplementary group names
      SUPP-GIDS  supplementary group IDs
     LAST-LOGIN  date of last login
       LAST-TTY  last tty used
  LAST-HOSTNAME  hostname during the last session
   FAILED-LOGIN  date of last failed login
     FAILED-TTY  where did the login fail?
         HUSHED  user's hush settings
       PWD-WARN  days user is warned of password expiration
     PWD-CHANGE  date of last password change
        PWD-MIN  number of days required between changes
        PWD-MAX  max number of days a password may remain unchanged
      PWD-EXPIR  password expiration date
        CONTEXT  the user's security context
           PROC  number of processes run by the user

For more details see lslogins(1).
```

***

**lsmem**

List the ranges of available memory with their online status

```
:~# lsmem -h

Usage:
 lsmem [options]

List the ranges of available memory with their online status.

Options:
 -J, --json           use JSON output format
 -P, --pairs          use key="value" output format
 -a, --all            list each individual memory block
 -b, --bytes          print SIZE in bytes rather than in human readable format
 -n, --noheadings     don't print headings
 -o, --output <list>  output columns
     --output-all     output all columns
 -r, --raw            use raw output format
 -S, --split <list>   split ranges by specified columns
 -s, --sysroot <dir>  use the specified directory as system root
     --summary[=when] print summary information (never,always or only)

 -h, --help           display this help
 -V, --version        display version

Available output columns:
      RANGE  start and end address of the memory range
       SIZE  size of the memory range
      STATE  online status of the memory range
  REMOVABLE  memory is removable
      BLOCK  memory block number or blocks range
       NODE  numa node of memory
      ZONES  valid zones for the memory range

For more details see lsmem(1).
```

***

**lsns**

List namespaces

```
:~# lsns -h

Usage:
 lsns [options] [<namespace>]

List system namespaces.

Options:
 -J, --json             use JSON output format
 -l, --list             use list format output
 -n, --noheadings       don't print headings
 -o, --output <list>    define which output columns to use
     --output-all       output all columns
 -p, --task <pid>       print process namespaces
 -r, --raw              use the raw output format
 -u, --notruncate       don't truncate text in columns
 -W, --nowrap           don't use multi-line representation
 -t, --type <name>      namespace type (mnt, net, ipc, user, pid, uts, cgroup, time)
 -T, --tree <rel>       use tree format (parent, owner, or process)

 -h, --help             display this help
 -V, --version          display version

Available output columns:
          NS  namespace identifier (inode number)
        TYPE  kind of namespace
        PATH  path to the namespace
      NPROCS  number of processes in the namespace
         PID  lowest PID in the namespace
        PPID  PPID of the PID
     COMMAND  command line of the PID
         UID  UID of the PID
        USER  username of the PID
     NETNSID  namespace ID as used by network subsystem
        NSFS  nsfs mountpoint (usually used network subsystem)
         PNS  parent namespace identifier (inode number)
         ONS  owner namespace identifier (inode number)

For more details see lsns(8).
```

***

**mcookie**

Generate magic cookies for xauth

```
:~# mcookie -h

Usage:
 mcookie [options]

Generate magic cookies for xauth.

Options:
 -f, --file <file>     use file as a cookie seed
 -m, --max-size <num>  limit how much is read from seed files
 -v, --verbose         explain what is being done

 -h, --help            display this help
 -V, --version         display version

Arguments:
 <num> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

For more details see mcookie(1).
```

***

**mesg**

Display (or do not display) messages from other users

```
:~# mesg -h

Usage:
 mesg [options] [y | n]

Control write access of other users to your terminal.

Options:
 -v, --verbose  explain what is being done
 -h, --help     display this help
 -V, --version  display version

For more details see mesg(1).
```

***

**mkfs**

Build a Linux filesystem

```
:~# mkfs -h

Usage:
 mkfs [options] [-t <type>] [fs-options] <device> [<size>]

Make a Linux filesystem.

Options:
 -t, --type=<type>  filesystem type; when unspecified, ext2 is used
     fs-options     parameters for the real filesystem builder
     <device>       path to the device to be used
     <size>         number of blocks to be used on the device
 -V, --verbose      explain what is being done;
                      specifying -V more than once will cause a dry-run
 -h, --help         display this help
 -V, --version      display version

For more details see mkfs(8).
```

***

**mkfs.bfs**

Make an SCO bfs filesystem

```
:~# mkfs.bfs -h
Usage: mkfs.bfs [options] device [block-count]

Make an SCO bfs filesystem.

Options:
 -N, --inodes=NUM    specify desired number of inodes
 -V, --vname=NAME    specify volume name
 -F, --fname=NAME    specify file system name
 -v, --verbose       explain what is being done
 -c                  this option is silently ignored
 -l                  this option is silently ignored
 -h, --help          display this help
 -V, --version       display version

For more details see mkfs.bfs(8).
```

***

**mkfs.cramfs**

Make compressed ROM file system

```
:~# mkfs.cramfs -h

Usage:
 mkfs.cramfs [-h] [-v] [-b blksize] [-e edition] [-N endian] [-i file] [-n name] dirname outfile

Make compressed ROM file system.

Options:
 -v             be verbose
 -E             make all warnings errors (non-zero exit status)
 -b blksize     use this blocksize, must equal page size
 -e edition     set edition number (part of fsid)
 -N endian      set cramfs endianness (big|little|host), default host
 -i file        insert a file image into the filesystem
 -n name        set name of cramfs filesystem
 -p             pad by 512 bytes for boot code
 -s             sort directory entries (old option, ignored)
 -z             make explicit holes
 dirname        root of the filesystem to be compressed
 outfile        output file

 -h, --help     display this help
 -V, --version  display version

For more details see mkfs.cramfs(8).
```

***

**mkfs.minix**

Make a Minix filesystem

```
:~# mkfs.minix -h

Usage:
 mkfs.minix [options] /dev/name [blocks]

Options:
 -1                      use Minix version 1
 -2, -v                  use Minix version 2
 -3                      use Minix version 3
 -n, --namelength <num>  maximum length of filenames
 -i, --inodes <num>      number of inodes for the filesystem
 -c, --check             check the device for bad blocks
 -l, --badblocks <file>  list of bad blocks from file
     --lock[=<mode>]     use exclusive device lock (yes, no or nonblock)

 -h, --help              display this help
 -V, --version           display version

For more details see mkfs.minix(8).
```

***

**mkswap**

Set up a Linux swap area

```
:~# mkswap -h

Usage:
 mkswap [options] device [size]

Set up a Linux swap area.

Options:
 -c, --check               check bad blocks before creating the swap area
 -f, --force               allow swap size area be larger than device
 -q, --quiet               suppress output and warning messages
 -p, --pagesize SIZE       specify page size in bytes
 -L, --label LABEL         specify label
 -v, --swapversion NUM     specify swap-space version number
 -U, --uuid UUID           specify the uuid to use
     --verbose             verbose output
     --lock[=<mode>]       use exclusive device lock (yes, no or nonblock)
 -h, --help                display this help
 -V, --version             display version

For more details see mkswap(8).
```

***

**more**

File perusal filter for crt viewing

```
:~# more -h

Usage:
 more [options] <file>...

A file perusal filter for CRT viewing.

Options:
 -d, --silent          display help instead of ringing bell
 -f, --logical         count logical rather than screen lines
 -l, --no-pause        suppress pause after form feed
 -c, --print-over      do not scroll, display text and clean line ends
 -p, --clean-print     do not scroll, clean screen and display text
 -e, --exit-on-eof     exit on end-of-file
 -s, --squeeze         squeeze multiple blank lines into one
 -u, --plain           suppress underlining and bold
 -n, --lines <number>  the number of lines per screenful
 -<number>             same as --lines
 +<number>             display file beginning from line number
 +/<pattern>           display file beginning from pattern match

 -h, --help            display this help
 -V, --version         display version

For more details see more(1).
```

***

**mountpoint**

See if a directory or file is a mountpoint

```
:~# mountpoint -h

Usage:
 mountpoint [-qd] /path/to/directory
 mountpoint -x /dev/device

Check whether a directory or file is a mountpoint.

Options:
 -q, --quiet        quiet mode - don't print anything
     --nofollow     do not follow symlink
 -d, --fs-devno     print maj:min device number of the filesystem
 -x, --devno        print maj:min device number of the block device

 -h, --help         display this help
 -V, --version      display version

For more details see mountpoint(1).
```

***

**namei**

Follow a pathname until a terminal point is found

```
:~# namei -h

Usage:
 namei [options] <pathname>...

Follow a pathname until a terminal point is found.

Options:
 -x, --mountpoints   show mount point directories with a 'D'
 -m, --modes         show the mode bits of each file
 -o, --owners        show owner and group name of each file
 -l, --long          use a long listing format (-m -o -v) 
 -n, --nosymlinks    don't follow symlinks
 -v, --vertical      vertical align of modes and owners
 -h, --help          display this help
 -V, --version       display version

For more details see namei(1).
```

***

**nsenter**

Run program in different namespaces

```
:~# nsenter -h

Usage:
 nsenter [options] [<program> [<argument>...]]

Run a program with namespaces of other processes.

Options:
 -a, --all              enter all namespaces
 -t, --target <pid>     target process to get namespaces from
 -m, --mount[=<file>]   enter mount namespace
 -u, --uts[=<file>]     enter UTS namespace (hostname etc)
 -i, --ipc[=<file>]     enter System V IPC namespace
 -n, --net[=<file>]     enter network namespace
 -p, --pid[=<file>]     enter pid namespace
 -C, --cgroup[=<file>]  enter cgroup namespace
 -U, --user[=<file>]    enter user namespace
 -T, --time[=<file>]    enter time namespace
 -S, --setuid <uid>     set uid in entered namespace
 -G, --setgid <gid>     set gid in entered namespace
     --preserve-credentials do not touch uids or gids
 -r, --root[=<dir>]     set the root directory
 -w, --wd[=<dir>]       set the working directory
 -W. --wdns <dir>       set the working directory in namespace
 -F, --no-fork          do not fork before exec'ing <program>
 -Z, --follow-context   set SELinux context according to --target PID

 -h, --help             display this help
 -V, --version          display version

For more details see nsenter(1).
```

***

**partx**

Tell the kernel about the presence and numbering of on-disk partitions

```
:~# partx -h

Usage:
 partx [-a|-d|-s|-u] [--nr <n:m> | <partition>] <disk>

Tell the kernel about the presence and numbering of partitions.

Options:
 -a, --add            add specified partitions or all of them
 -d, --delete         delete specified partitions or all of them
 -u, --update         update specified partitions or all of them
 -s, --show           list partitions

 -b, --bytes          print SIZE in bytes rather than in human readable format
 -g, --noheadings     don't print headings for --show
 -n, --nr <n:m>       specify the range of partitions (e.g. --nr 2:4)
 -o, --output <list>  define which output columns to use
     --output-all     output all columns
 -P, --pairs          use key="value" output format
 -r, --raw            use raw output format
 -S, --sector-size <num>  overwrite sector size
 -t, --type <type>    specify the partition type
     --list-types     list supported partition types and exit
 -v, --verbose        verbose mode

 -h, --help           display this help
 -V, --version        display version

Available output columns:
         NR  partition number
      START  start of the partition in sectors
        END  end of the partition in sectors
    SECTORS  number of sectors
       SIZE  human readable size
       NAME  partition name
       UUID  partition UUID
       TYPE  partition type (a string, a UUID, or hex)
      FLAGS  partition flags
     SCHEME  partition table type (dos, gpt, ...)

For more details see partx(8).
```

***

**pivot\_root**

Change the root filesystem

```
:~# pivot_root -h

Usage:
 pivot_root [options] new_root put_old

Change the root filesystem.

Options:
 -h, --help     display this help
 -V, --version  display version

For more details see pivot_root(8).
```

***

**prlimit**

Get and set process resource limits

```
:~# prlimit -h

Usage:
 prlimit [options] [--<resource>=<limit>] [-p PID]
 prlimit [options] [--<resource>=<limit>] COMMAND

Show or change the resource limits of a process.

Options:
 -p, --pid <pid>        process id
 -o, --output <list>    define which output columns to use
     --noheadings       don't print headings
     --raw              use the raw output format
     --verbose          verbose output
 -h, --help             display this help
 -V, --version          display version

Resources:
 -c, --core             maximum size of core files created
 -d, --data             maximum size of a process's data segment
 -e, --nice             maximum nice priority allowed to raise
 -f, --fsize            maximum size of files written by the process
 -i, --sigpending       maximum number of pending signals
 -l, --memlock          maximum size a process may lock into memory
 -m, --rss              maximum resident set size
 -n, --nofile           maximum number of open files
 -q, --msgqueue         maximum bytes in POSIX message queues
 -r, --rtprio           maximum real-time scheduling priority
 -s, --stack            maximum stack size
 -t, --cpu              maximum amount of CPU time in seconds
 -u, --nproc            maximum number of user processes
 -v, --as               size of virtual memory
 -x, --locks            maximum number of file locks
 -y, --rttime           CPU time in microseconds a process scheduled
                        under real-time scheduling

Arguments:
 <limit> is defined as a range soft:hard, soft:, :hard or a value to
         define both limits (e.g. -e=0:10 -r=:10).

Available output columns:
 DESCRIPTION  resource description
    RESOURCE  resource name
        SOFT  soft limit
        HARD  hard limit (ceiling)
       UNITS  units

For more details see prlimit(1).
```

***

**readprofile**

Read kernel profiling information

```
:~# readprofile -h

Usage:
 readprofile [options]

Display kernel profiling information.

Options:
 -m, --mapfile <mapfile>   (defaults: "/boot/System.map" and
                                      "/boot/System.map-6.1.0-kali5-amd64")
 -p, --profile <pro-file>  (default:  "/proc/profile")
 -M, --multiplier <mult>   set the profiling multiplier to <mult>
 -i, --info                print only info about the sampling step
 -v, --verbose             print verbose data
 -a, --all                 print all symbols, even if count is 0
 -b, --histbin             print individual histogram-bin counts
 -s, --counters            print individual counters within functions
 -r, --reset               reset all the counters (root only)
 -n, --no-auto             disable byte order auto-detection

 -h, --help                display this help
 -V, --version             display version

For more details see readprofile(8).
```

***

**rename.ul**

Rename files

```
:~# rename.ul -h

Usage:
 rename.ul [options] <expression> <replacement> <file>...

Rename files.

Options:
 -v, --verbose       explain what is being done
 -s, --symlink       act on the target of symlinks
 -n, --no-act        do not make any changes
 -a, --all           replace all occurrences
 -l, --last          replace only the last occurrence
 -o, --no-overwrite  don't overwrite existing files
 -i, --interactive   prompt before overwrite

 -h, --help          display this help
 -V, --version       display version

For more details see rename(1).
```

***

**resizepart**

Tell the kernel about the new size of a partition

```
:~# resizepart -h

Usage:
 resizepart <disk device> <partition number> <length>

Tell the kernel about the new size of a partition.

Options:
 -h, --help     display this help
 -V, --version  display version

For more details see resizepart(8).
```

***

**rev**

Reverse lines characterwise

```
:~# rev -h
Usage: rev [options] [file ...]

Reverse lines characterwise.

Options:
 -h, --help     display this help
 -V, --version  display version

For more details see rev(1).
```

***

**rtcwake**

Enter a system sleep state until specified wakeup time

```
:~# rtcwake -h

Usage:
 rtcwake [options]

Enter a system sleep state until a specified wakeup time.

Options:
 -a, --auto               reads the clock mode from adjust file (default)
 -A, --adjfile <file>     specifies the path to the adjust file
                            the default is /etc/adjtime
     --date <timestamp>   date time of timestamp to wake
 -d, --device <device>    select rtc device (rtc0|rtc1|...)
 -n, --dry-run            does everything, but suspend
 -l, --local              RTC uses local timezone
     --list-modes         list available modes
 -m, --mode <mode>        standby|mem|... sleep mode
 -s, --seconds <seconds>  seconds to sleep
 -t, --time <time_t>      time to wake
 -u, --utc                RTC uses UTC
 -v, --verbose            verbose messages

 -h, --help               display this help
 -V, --version            display version

For more details see rtcwake(8).
```

***

**runuser**

Run a command with substitute user and group ID

```
:~# runuser -h

Usage:
 runuser [options] -u <user> [[--] <command>]
 runuser [options] [-] [<user> [<argument>...]]

Run <command> with the effective user ID and group ID of <user>.  If -u is
not given, fall back to su(1)-compatible semantics and execute standard shell.
The options -c, -f, -l, and -s are mutually exclusive with -u.

Options:
 -u, --user <user>               username
 -m, -p, --preserve-environment      do not reset environment variables
 -w, --whitelist-environment <list>  don't reset specified variables

 -g, --group <group>             specify the primary group
 -G, --supp-group <group>        specify a supplemental group

 -, -l, --login                  make the shell a login shell
 -c, --command <command>         pass a single command to the shell with -c
 --session-command <command>     pass a single command to the shell with -c
                                   and do not create a new session
 -f, --fast                      pass -f to the shell (for csh or tcsh)
 -s, --shell <shell>             run <shell> if /etc/shells allows it
 -P, --pty                       create a new pseudo-terminal

 -h, --help                      display this help
 -V, --version                   display version


For more details see runuser(1).
```

***

**setarch**

Change reported architecture in new program environment and/or set personality flags

```
:~# setarch -h

Usage:
 setarch [<arch>] [options] [<program> [<argument>...]]

Change the reported architecture and set personality flags.

Options:
 -B, --32bit              turns on ADDR_LIMIT_32BIT
 -F, --fdpic-funcptrs     makes function pointers point to descriptors
 -I, --short-inode        turns on SHORT_INODE
 -L, --addr-compat-layout changes the way virtual memory is allocated
 -R, --addr-no-randomize  disables randomization of the virtual address space
 -S, --whole-seconds      turns on WHOLE_SECONDS
 -T, --sticky-timeouts    turns on STICKY_TIMEOUTS
 -X, --read-implies-exec  turns on READ_IMPLIES_EXEC
 -Z, --mmap-page-zero     turns on MMAP_PAGE_ZERO
 -3, --3gb                limits the used address space to a maximum of 3 GB
     --4gb                ignored (for backward compatibility only)
     --uname-2.6          turns on UNAME26
 -v, --verbose            say what options are being switched on
     --list               list settable architectures, and exit

 -h, --help               display this help
 -V, --version            display version

For more details see setarch(8).
```

***

**setpriv**

Run a program with different Linux privilege settings

```
:~# setpriv -h

Usage:
 setpriv [options] <program> [<argument>...]

Run a program with different privilege settings.

Options:
 -d, --dump                  show current state (and do not exec)
 --nnp, --no-new-privs       disallow granting new privileges
 --ambient-caps <caps,...>   set ambient capabilities
 --inh-caps <caps,...>       set inheritable capabilities
 --bounding-set <caps>       set capability bounding set
 --ruid <uid|user>           set real uid
 --euid <uid|user>           set effective uid
 --rgid <gid|user>           set real gid
 --egid <gid|group>          set effective gid
 --reuid <uid|user>          set real and effective uid
 --regid <gid|group>         set real and effective gid
 --clear-groups              clear supplementary groups
 --keep-groups               keep supplementary groups
 --init-groups               initialize supplementary groups
 --groups <group,...>        set supplementary groups by UID or name
 --securebits <bits>         set securebits
 --pdeathsig keep|clear|<signame>
                             set or clear parent death signal
 --selinux-label <label>     set SELinux label
 --apparmor-profile <pr>     set AppArmor profile
 --reset-env                 clear all environment and initialize
                               HOME, SHELL, USER, LOGNAME and PATH

 -h, --help                  display this help
 -V, --version               display version

 This tool can be dangerous.  Read the manpage, and be careful.

For more details see setpriv(1).
```

***

**setsid**

Run a program in a new session

```
:~# setsid -h

Usage:
 setsid [options] <program> [arguments ...]

Run a program in a new session.

Options:
 -c, --ctty     set the controlling terminal to the current one
 -f, --fork     always fork
 -w, --wait     wait program to exit, and use the same return
 -h, --help     display this help
 -V, --version  display version

For more details see setsid(1).
```

***

**setterm**

Set terminal attributes

```
:~# setterm --help

Usage:
 setterm [options]

Set the attributes of a terminal.

Options:
 --term <terminal_name>        override TERM environment variable
 --reset                       reset terminal to power-on state
 --resize                      reset terminal rows and columns
 --initialize                  display init string, and use default settings
 --default                     use default terminal settings
 --store                       save current terminal settings as default

 --cursor on|off               display cursor
 --repeat on|off               keyboard repeat
 --appcursorkeys on|off        cursor key application mode
 --linewrap on|off             continue on a new line when a line is full
 --inversescreen on|off        swap colors for the whole screen

 --msg on|off                  send kernel messages to console
 --msglevel <0-8>              kernel console log level

 --foreground default|<color>  set foreground color
 --background default|<color>  set background color
 --ulcolor [bright] <color>    set underlined text color
 --hbcolor [bright] <color>    set half-bright text color
        <color>: black blue cyan green grey magenta red white yellow

 --bold on|off                 bold
 --half-bright on|off          dim
 --blink on|off                blink
 --underline on|off            underline
 --reverse  on|off             swap foreground and background colors

 --clear[=<all|rest>]          clear screen and set cursor position
 --tabs[=<number>...]          set these tab stop positions, or show them
 --clrtabs[=<number>...]       clear these tab stop positions, or all
 --regtabs[=1-160]             set a regular tab stop interval
 --blank[=0-60|force|poke]     set time of inactivity before screen blanks

 --dump[=<number>]             write vcsa<number> console dump to file
 --append <number>             append vcsa<number> console dump to file
 --file <filename>             name of the dump file

 --powersave on|vsync|hsync|powerdown|off
                               set vesa powersaving features
 --powerdown[=<0-60>]          set vesa powerdown interval in minutes

 --blength[=<0-2000>]          duration of the bell in milliseconds
 --bfreq[=<number>]            bell frequency in Hertz

 --help                        display this help
 --version                     display version

For more details see setterm(1).
```

***

**su**

Run a command with substitute user and group ID

```
:~# su -h

Usage:
 su [options] [-] [<user> [<argument>...]]

Change the effective user ID and group ID to that of <user>.
A mere - implies -l.  If <user> is not given, root is assumed.

Options:
 -m, -p, --preserve-environment      do not reset environment variables
 -w, --whitelist-environment <list>  don't reset specified variables

 -g, --group <group>             specify the primary group
 -G, --supp-group <group>        specify a supplemental group

 -, -l, --login                  make the shell a login shell
 -c, --command <command>         pass a single command to the shell with -c
 --session-command <command>     pass a single command to the shell with -c
                                   and do not create a new session
 -f, --fast                      pass -f to the shell (for csh or tcsh)
 -s, --shell <shell>             run <shell> if /etc/shells allows it
 -P, --pty                       create a new pseudo-terminal

 -h, --help                      display this help
 -V, --version                   display version

For more details see su(1).
```

***

**sulogin**

Single-user login

```
:~# sulogin -h

Usage:
 sulogin [options] [tty device]

Single-user login.

Options:
 -p, --login-shell        start a login shell
 -t, --timeout <seconds>  max time to wait for a password (default: no limit)
 -e, --force              examine password files directly if getpwnam(3) fails

 -h, --help               display this help
 -V, --version            display version

For more details see sulogin(8).
```

***

**swaplabel**

Print or change the label or UUID of a swap area

```
:~# swaplabel -h

Usage:
 swaplabel [options] <device>

Display or change the label or UUID of a swap area.

Options:
 -L, --label <label> specify a new label
 -U, --uuid <uuid>   specify a new uuid

 -h, --help          display this help
 -V, --version       display version

For more details see swaplabel(8).
```

***

**switch\_root**

Switch to another filesystem as the root of the mount tree

```
:~# switch_root -h

Usage:
 switch_root [options] <newrootdir> <init> <args to init>

Switch to another filesystem as the root of the mount tree.

Options:
 -h, --help     display this help
 -V, --version  display version

For more details see switch_root(8).
```

***

**taskset**

Set or retrieve a process’s CPU affinity

```
:~# taskset -h
Usage: taskset [options] [mask | cpu-list] [pid|cmd [args...]]


Show or change the CPU affinity of a process.

Options:
 -a, --all-tasks         operate on all the tasks (threads) for a given pid
 -p, --pid               operate on existing given pid
 -c, --cpu-list          display and specify cpus in list format
 -h, --help              display this help
 -V, --version           display version

The default behavior is to run a new command:
    taskset 03 sshd -b 1024
You can retrieve the mask of an existing task:
    taskset -p 700
Or set it:
    taskset -p 03 700
List format uses a comma-separated list instead of a mask:
    taskset -pc 0,3,7-11 700
Ranges in list format can take a stride argument:
    e.g. 0-31:2 is equivalent to mask 0x55555555

For more details see taskset(1).
```

***

**uclampset**

Manipulate the utilization clamping attributes of the system or a process

```
:~# uclampset -h

Usage:
 uclampset [options]
 uclampset [options] --pid <pid> | --system | <command> <arg>...

Show or change the utilization clamping attributes.

Options:
 -m <value>           util_min value to set
 -M <value>           util_max value to set
 -a, --all-tasks      operate on all the tasks (threads) for a given pid
 -p, --pid <pid>      operate on existing given pid
 -s, --system         operate on system
 -R, --reset-on-fork  set reset-on-fork flag
 -v, --verbose        display status information
 -h, --help           display this help
 -V, --version        display version

Utilization value range is [0:1024]. Use special -1 value to reset to system's default.

For more details see uclampset(1).
```

***

**unshare**

Run program in new namespaces

```
:~# unshare -h

Usage:
 unshare [options] [<program> [<argument>...]]

Run a program with some namespaces unshared from the parent.

Options:
 -m, --mount[=<file>]      unshare mounts namespace
 -u, --uts[=<file>]        unshare UTS namespace (hostname etc)
 -i, --ipc[=<file>]        unshare System V IPC namespace
 -n, --net[=<file>]        unshare network namespace
 -p, --pid[=<file>]        unshare pid namespace
 -U, --user[=<file>]       unshare user namespace
 -C, --cgroup[=<file>]     unshare cgroup namespace
 -T, --time[=<file>]       unshare time namespace

 -f, --fork                fork before launching <program>
 --map-user=<uid>|<name>   map current user to uid (implies --user)
 --map-group=<gid>|<name>  map current group to gid (implies --user)
 -r, --map-root-user       map current user to root (implies --user)
 -c, --map-current-user    map current user to itself (implies --user)
 --map-auto                map users and groups automatically (implies --user)
 --map-users=<outeruid>,<inneruid>,<count>
                           map count users from outeruid to inneruid (implies --user)
 --map-groups=<outergid>,<innergid>,<count>
                           map count groups from outergid to innergid (implies --user)

 --kill-child[=<signame>]  when dying, kill the forked child (implies --fork)
                             defaults to SIGKILL
 --mount-proc[=<dir>]      mount proc filesystem first (implies --mount)
 --propagation slave|shared|private|unchanged
                           modify mount propagation in mount namespace
 --setgroups allow|deny    control the setgroups syscall in user namespaces
 --keep-caps               retain capabilities granted in user namespaces

 -R, --root=<dir>          run the command with root directory set to <dir>
 -w, --wd=<dir>            change working directory to <dir>
 -S, --setuid <uid>        set uid in entered namespace
 -G, --setgid <gid>        set gid in entered namespace
 --monotonic <offset>      set clock monotonic offset (seconds) in time namespaces
 --boottime <offset>       set clock boottime offset (seconds) in time namespaces

 -h, --help                display this help
 -V, --version             display version

For more details see unshare(1).
```

***

**utmpdump**

Dump UTMP and WTMP files in raw format

```
:~# utmpdump -h

Usage:
 utmpdump [options] [filename]

Dump UTMP and WTMP files in raw format.

Options:
 -f, --follow         output appended data as the file grows
 -r, --reverse        write back dumped data into utmp file
 -o, --output <file>  write to file instead of standard output
 -h, --help           display this help
 -V, --version        display version

For more details see utmpdump(1).
```

***

**wdctl**

Show hardware watchdog status

```
:~# wdctl -h

Usage:
 wdctl [options] [<device> ...]

Show the status of the hardware watchdog.

Options:
 -f, --flags <list>     print selected flags only
 -F, --noflags          don't print information about flags
 -I, --noident          don't print watchdog identity information
 -n, --noheadings       don't print headings for flags table
 -O, --oneline          print all information on one line
 -o, --output <list>    output columns of the flags
 -p, --setpretimeout <sec> set watchdog pre-timeout
 -g, --setpregovernor <name> set pre-timeout governor
 -r, --raw              use raw output format for flags table
 -T, --notimeouts       don't print watchdog timeouts
 -s, --settimeout <sec> set watchdog timeout
 -x, --flags-only       print only flags table (same as -I -T)

 -h, --help             display this help
 -V, --version          display version

No default device is available.

Available output columns:
          FLAG  flag name
   DESCRIPTION  flag description
        STATUS  flag status
   BOOT-STATUS  flag boot status
        DEVICE  watchdog device name

For more details see wdctl(8).
```

***

**whereis**

Locate the binary, source, and manual page files for a command

```
:~# whereis -h

Usage:
 whereis [options] [-BMS <dir>... -f] <name>

Locate the binary, source, and manual-page files for a command.

Options:
 -b         search only for binaries
 -B <dirs>  define binaries lookup path
 -m         search only for manuals and infos
 -M <dirs>  define man and info lookup path
 -s         search only for sources
 -S <dirs>  define sources lookup path
 -f         terminate <dirs> argument list
 -u         search for unusual entries
 -l         output effective lookup paths

 -h, --help     display this help
 -V, --version  display version

For more details see whereis(1).
```

***

**wipefs**

Wipe a signature from a device

```
:~# wipefs -h

Usage:
 wipefs [options] <device>

Wipe signatures from a device.

Options:
 -a, --all           wipe all magic strings (BE CAREFUL!)
 -b, --backup        create a signature backup in $HOME
 -f, --force         force erasure
 -i, --noheadings    don't print headings
 -J, --json          use JSON output format
 -n, --no-act        do everything except the actual write() call
 -o, --offset <num>  offset to erase, in bytes
 -O, --output <list> COLUMNS to display (see below)
 -p, --parsable      print out in parsable instead of printable format
 -q, --quiet         suppress output messages
 -t, --types <list>  limit the set of filesystem, RAIDs or partition tables
     --lock[=<mode>] use exclusive device lock (yes, no or nonblock)
 -h, --help          display this help
 -V, --version       display version

Arguments:
 <num> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)

Available output columns:
     UUID  partition/filesystem UUID
    LABEL  filesystem LABEL
   LENGTH  magic string length
     TYPE  superblok type
   OFFSET  magic string offset
    USAGE  type description
   DEVICE  block device name

For more details see wipefs(8).
```

***

**x86\_64**

Change reported architecture in new program environment and/or set personality flags

```
:~# x86_64 -h

Usage:
 x86_64 [options] [<program> [<argument>...]]

Change the reported architecture and set personality flags.

Options:
 -B, --32bit              turns on ADDR_LIMIT_32BIT
 -F, --fdpic-funcptrs     makes function pointers point to descriptors
 -I, --short-inode        turns on SHORT_INODE
 -L, --addr-compat-layout changes the way virtual memory is allocated
 -R, --addr-no-randomize  disables randomization of the virtual address space
 -S, --whole-seconds      turns on WHOLE_SECONDS
 -T, --sticky-timeouts    turns on STICKY_TIMEOUTS
 -X, --read-implies-exec  turns on READ_IMPLIES_EXEC
 -Z, --mmap-page-zero     turns on MMAP_PAGE_ZERO
 -3, --3gb                limits the used address space to a maximum of 3 GB
     --4gb                ignored (for backward compatibility only)
     --uname-2.6          turns on UNAME26
 -v, --verbose            say what options are being switched on

 -h, --help               display this help
 -V, --version            display version

For more details see setarch(8).
```

***

**zramctl**

Set up and control zram devices

```
:~# zramctl -h

Usage:
 zramctl [options] <device>
 zramctl -r <device> [...]
 zramctl [options] -f | <device> -s <size>

Set up and control zram devices.

Options:
 -a, --algorithm <alg>     compression algorithm to use
 -b, --bytes               print sizes in bytes rather than in human readable format
 -f, --find                find a free device
 -n, --noheadings          don't print headings
 -o, --output <list>       columns to use for status output
     --output-all          output all columns
     --raw                 use raw status output format
 -r, --reset               reset all specified devices
 -s, --size <size>         device size
 -t, --streams <number>    number of compression streams

 -h, --help                display this help
 -V, --version             display version

Arguments:
 <size> arguments may be followed by the suffixes for
   GiB, TiB, PiB, EiB, ZiB, and YiB (the "iB" is optional)
 <alg> specify algorithm, supported are:
   lzo, lz4, lz4hc, deflate, 842 and zstd

Available output columns:
        NAME  zram device name
    DISKSIZE  limit on the uncompressed amount of data
        DATA  uncompressed size of stored data
       COMPR  compressed size of stored data
   ALGORITHM  the selected compression algorithm
     STREAMS  number of concurrent compress operations
  ZERO-PAGES  empty pages with no allocated memory
       TOTAL  all memory including allocator fragmentation and metadata overhead
   MEM-LIMIT  memory limit used to store compressed data
    MEM-USED  memory zram have been consumed to store compressed data
    MIGRATED  number of objects migrated by compaction
  MOUNTPOINT  where the device is mounted

For more details see zramctl(8).
```

***

Tools commonly found on systems where humans login interactively, or are needed with non-standard system configurations.

**Installed size:** `366 KB`\
**How to install:** `sudo apt install util-linux-extra`

<details>

<summary>Dependencies:</summary>

* libaudit1
* libc6
* libsmartcols1

</details>

**fincore**

Count pages of file contents in core

```
:~# fincore -h

Usage:
 fincore [options] file...

Options:
 -J, --json            use JSON output format
 -b, --bytes           print sizes in bytes rather than in human readable format
 -n, --noheadings      don't print headings
 -o, --output <list>   output columns
 -r, --raw             use raw output format

 -h, --help            display this help
 -V, --version         display version

Available output columns:
       PAGES  file data resident in memory in pages
        SIZE  size of the file
        FILE  file name
         RES  file data resident in memory in bytes

For more details see fincore(1).
```

***

**hwclock**

Settings that affect the behaviour of the hwclock init script Time clocks utility

```
:~# hwclock -h

Usage:
 hwclock [function] [option...]

Time clocks utility.

Functions:
 -r, --show                      display the RTC time
     --get                       display drift corrected RTC time
     --set                       set the RTC according to --date
 -s, --hctosys                   set the system time from the RTC
 -w, --systohc                   set the RTC from the system time
     --systz                     send timescale configurations to the kernel
 -a, --adjust                    adjust the RTC to account for systematic drift
     --param-get <param>         display the RTC parameter
     --param-set <param>=<value> set the RTC parameter
     --predict                   predict the drifted RTC time according to --date

Options:
 -u, --utc                       the RTC timescale is UTC
 -l, --localtime                 the RTC timescale is Local
 -f, --rtc <file>                use an alternate file to /dev/rtc0
     --directisa                 use the ISA bus instead of /dev/rtc0 access
     --date <time>               date/time input for --set and --predict
     --delay <sec>               delay used when set new RTC time
     --update-drift              update the RTC drift factor
     --noadjfile                 do not use /etc/adjtime
     --adjfile <file>            use an alternate file to /etc/adjtime
     --test                      dry run; implies --verbose
 -v, --verbose                   display more details

 -h, --help                      display this help
 -V, --version                   display version

Arguments:
 <param> is either a numeric RTC parameter value or one of these aliases:
   - features: supported features (0x0)
   - correction: time correction (0x1)
   - bsm: backup switch mode (0x2)
   See Kernel's include/uapi/linux/rtc.h for parameters and values.

 <param> and <value> accept hexadecimal values if prefixed with 0x, otherwise decimal.

For more details see hwclock(8).
```

***

**lsfd**

List file descriptors

```
:~# lsfd -h

Usage:
 lsfd [options]

Options:
 -l, --threads         list in threads level
 -J, --json            use JSON output format
 -n, --noheadings      don't print headings
 -o, --output <list>   output columns
 -r, --raw             use raw output format
 -u, --notruncate      don't truncate text in columns
 -p, --pid  <pid(s)>   collect information only specified processes
 -Q, --filter <expr>   apply display filter
     --debug-filter    dump the internal data structure of filter and exit
 -C, --counter <name>:<expr>
                       define custom counter for --summary output
     --dump-counters   dump counter definitions
     --summary[=when]  print summary information (only, append, or never)

 -h, --help            display this help
 -V, --version         display version

Available output columns:
       ASSOC  <string>  association between file and process
      BLKDRV  <string>  block device driver name resolved by /proc/devices
      CHRDRV  <string>  character device driver name resolved by /proc/devices
     COMMAND  <string>  command of the process opening the file
     DELETED  <boolean> reachability from the file system
         DEV  <string>  ID of device containing file
     DEVTYPE  <string>  device type (blk, char, or nodev)
          FD  <number>  file descriptor for the file
       FLAGS  <string>  flags specified when opening the file
       INODE  <number>  inode number
     KTHREAD  <boolean> opened by a kernel thread
     MAJ:MIN  <string>  device ID for special, or ID of device containing file
      MAPLEN  <number>  length of file mapping (in page)
     MISCDEV  <string>  misc character device name resolved by /proc/misc
       MNTID  <number>  mount id
        MODE  <string>  access mode (rwx)
        NAME  <string>  name of the file
       NLINK  <number>  link count
   PARTITION  <string>  block device name resolved by /proc/partition
         PID  <number>  PID of the process opening the file
         POS  <number>  file position
   PROTONAME  <string>  protocol name
        RDEV  <string>  device ID (if special file)
        SIZE  <number>  file size
      SOURCE  <string>  file system, partition, or device containing file
         TID  <number>  thread ID of the process opening the file
        TYPE  <string>  file type
         UID  <number>  user ID number of the process
        USER  <string>  user of the process
        FUID  <number>  user ID number of the file's owner
       OWNER  <string>  owner of the file

For more details see lsfd(1).
```

***

**lsirq**

Utility to display kernel interrupt information

```
:~# lsirq -h

Usage:
 lsirq [options]

Utility to display kernel interrupt information.

Options:
 -J, --json           use JSON output format
 -P, --pairs          use key="value" output format
 -n, --noheadings     don't print headings
 -o, --output <list>  define which output columns to use
 -s, --sort <column>  specify sort column
 -S, --softirq        show softirqs instead of interrupts

 -h, --help           display this help
 -V, --version        display version

Available output columns:
  IRQ    interrupts
  TOTAL  total count
  NAME   name

For more details see lsirq(1).
```

***

#### util-linux-locales <a href="#util-linux-locales" id="util-linux-locales"></a>

This package contains the internationalization files for the util-linux package.

They are needed when you want the programs in util-linux to print their messages in other languages than English.

**Installed size:** `7.78 MB`\
**How to install:** `sudo apt install util-linux-locales`

<details>

<summary>Dependencies:</summary>

* util-linux

</details>

***

#### uuid-dev <a href="#uuid-dev" id="uuid-dev"></a>

The libuuid library generates and parses 128-bit Universally Unique IDs (UUIDs). See RFC 4122 for more information.

This package contains the development environment for the uuid library.

**Installed size:** `113 KB`\
**How to install:** `sudo apt install uuid-dev`

<details>

<summary>Dependencies:</summary>

* libc6-dev | libc-dev
* libuuid1

</details>

***

#### uuid-runtime <a href="#uuid-runtime" id="uuid-runtime"></a>

The libuuid library generates and parses 128-bit Universally Unique IDs (UUIDs). A UUID is an identifier that is unique within the space of all such identifiers across both space and time. It can be used for multiple purposes, from tagging objects with an extremely short lifetime to reliably identifying very persistent objects across a network.

See RFC 4122 for more information.

This package contains the uuidgen program and the uuidd daemon.

The uuidd daemon is used to generate UUIDs, especially time-based UUIDs, in a secure and guaranteed-unique fashion, even in the face of large numbers of threads trying to grab UUIDs running on different CPUs. It is used by libuuid as well as the uuidgen program.

**Installed size:** `174 KB`\
**How to install:** `sudo apt install uuid-runtime`

<details>

<summary>Dependencies:</summary>

* adduser
* init-system-helpers
* libc6
* libsmartcols1
* libsystemd0
* libuuid1
* libuuid1

</details>

**uuidd**

UUID generation daemon

```
:~# uuidd -h

Usage:
 uuidd [options]

A daemon for generating UUIDs.

Options:
 -p, --pid <path>        path to pid file
 -s, --socket <path>     path to socket
 -T, --timeout <sec>     specify inactivity timeout
 -k, --kill              kill running daemon
 -r, --random            test random-based generation
 -t, --time              test time-based generation
 -n, --uuids <num>       request number of uuids
 -P, --no-pid            do not create pid file
 -F, --no-fork           do not daemonize using double-fork
 -S, --socket-activation do not create listening socket
 -C, --cont-clock[=<NUM>[hd]]
                         activate continuous clock handling
 -d, --debug             run in debugging mode
 -q, --quiet             turn on quiet mode

 -h, --help              display this help
 -V, --version           display version

For more details see uuidd(8).
```

***

**uuidgen**

Create a new UUID value

```
:~# uuidgen -h

Usage:
 uuidgen [options]

Create a new UUID value.

Options:
 -r, --random        generate random-based uuid
 -t, --time          generate time-based uuid
 -n, --namespace ns  generate hash-based uuid in this namespace
                       available namespaces: @dns @url @oid @x500
 -N, --name name     generate hash-based uuid from this name
 -m, --md5           generate md5 hash
 -s, --sha1          generate sha1 hash
 -x, --hex           interpret name as hex string

 -h, --help          display this help
 -V, --version       display version

For more details see uuidgen(1).
```

***

**uuidparse**

A utility to parse unique identifiers

```
:~# uuidparse -h

Usage:
 uuidparse [options] <uuid ...>

Options:
 -J, --json             use JSON output format
 -n, --noheadings       don't print headings
 -o, --output <list>    COLUMNS to display (see below)
 -r, --raw              use the raw output format
 -h, --help             display this help
 -V, --version          display version

Available output columns:
     UUID  unique identifier
  VARIANT  variant name
     TYPE  type name
     TIME  timestamp

For more details see uuidparse(1).
```

***

Updated on: 2023-Mar-08\


***
