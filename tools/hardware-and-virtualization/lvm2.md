---
description: >-
  LVM2 is a Linux-based logical volume manager that allows for the creation of
  logical volumes on one or more physical hard drives.
---

# 💾 lvm2

LVM2 (Logical Volume Manager 2) is a tool used in Linux-based operating systems to manage and organize storage devices, including hard disks, SSDs, and other storage media, into logical volumes. LVM2 provides a layer of abstraction between physical storage devices and the file systems that use them, allowing for more flexibility and scalability in managing storage resources. With LVM2, multiple physical disks can be combined into a single logical volume, which can then be divided into smaller volumes or resized as needed. LVM2 also allows for snapshots and mirroring of volumes for backup and redundancy purposes.

#### dmeventd <a href="#dmeventd" id="dmeventd"></a>

The Linux Kernel Device Mapper is the LVM (Linux Logical Volume Management) Team’s implementation of a minimalistic kernel-space driver that handles volume management, while keeping knowledge of the underlying device layout in user-space. This makes it useful for not only LVM, but software raid, and other drivers that create “virtual” block devices.

This package contains a daemon to monitor events of devmapper devices.

**Installed size:** `224 KB`\
**How to install:** `sudo apt install dmeventd`

<details>

<summary>Dependencies:</summary>

* libc6
* libdevmapper-event1.02.1
* libdevmapper1.02.1
* liblvm2cmd2.03

</details>

**dmeventd**

Device-mapper event daemon

```
:~# dmeventd -h
Usage:
dmeventd [-d [-d [-d]]] [-f] [-h] [-l] [-R] [-V] [-?]

   -d       Log debug messages to syslog (-d, -dd, -ddd)
   -f       Don't fork, run in the foreground
   -h       Show this help information
   -l       Log to stdout,stderr instead of syslog
   -?       Show this help information on stderr
   -R       Restart dmeventd
   -V       Show version of dmeventd

```

***

#### dmsetup <a href="#dmsetup" id="dmsetup"></a>

The Linux Kernel Device Mapper is the LVM (Linux Logical Volume Management) Team’s implementation of a minimalistic kernel-space driver that handles volume management, while keeping knowledge of the underlying device layout in user-space. This makes it useful for not only LVM, but software raid, and other drivers that create “virtual” block devices.

This package contains a utility for modifying device mappings.

**Installed size:** `246 KB`\
**How to install:** `sudo apt install dmsetup`

<details>

<summary>Dependencies:</summary>

* libc6
* libdevmapper1.02.1

</details>

**blkdeactivate**

Utility to deactivate block devices

```
:~# blkdeactivate -h
blkdeactivate: Utility to deactivate block devices

  blkdeactivate [options] [device...]
    - Deactivate block device tree.
      If devices are specified, deactivate only supplied devices and their holders.

  Options:
    -e | --errors                       Show errors reported from tools
    -h | --help                         Show this help message
    -d | --dmoptions     DM_OPTIONS     Comma separated DM specific options
    -l | --lvmoptions    LVM_OPTIONS    Comma separated LVM specific options
    -m | --mpathoptions  MPATH_OPTIONS  Comma separated DM-multipath specific options
    -r | --mdraidoptions MDRAID_OPTIONS Comma separated MD RAID specific options
    -o | --vdooptions    VDO_OPTIONS    Comma separated VDO specific options
    -u | --umount                       Unmount the device if mounted
    -v | --verbose                      Verbose mode (also implies -e)

  Device specific options:
    DM_OPTIONS:
      retry           retry removal several times in case of failure
      force           force device removal
    LVM_OPTIONS:
      retry           retry removal several times in case of failure
      wholevg         deactivate the whole VG when processing an LV
    MDRAID_OPTIONS:
      wait            wait for resync, recovery or reshape to complete first
    MPATH_OPTIONS:
      disablequeueing disable queueing on all DM-multipath devices first
    VDO_OPTIONS:
      configfile=file use specified VDO configuration file
```

***

**dmsetup**

Low level logical volume management

```
:~# dmsetup -h
Usage:

dmsetup
        [--version] [-h|--help [-c|-C|--columns]]
        [-v|--verbose [-v|--verbose ...]] [-f|--force]
        [--checks] [--manglename {none|hex|auto}]
        [-r|--readonly] [--noopencount] [--noflush] [--nolockfs] [--inactive]
        [--udevcookie <cookie>] [--noudevrules] [--noudevsync] [--verifyudev]
        [-y|--yes] [--readahead {[+]<sectors>|auto|none}] [--retry]
        [-c|-C|--columns] [-o <fields>] [-O|--sort <sort_fields>]
        [-S|--select <selection>] [--nameprefixes] [--noheadings]
        [--separator <separator>]

	help [-c|-C|--columns]
	create <dev_name>
	    [-j|--major <major> -m|--minor <minor>]
	    [-U|--uid <uid>] [-G|--gid <gid>] [-M|--mode <octal_mode>]
	    [-u|--uuid <uuid>] [--addnodeonresume|--addnodeoncreate]
	    [--readahead {[+]<sectors>|auto|none}]
	    [-n|--notable|--table {<table>|<table_file>}]
	create --concise [<concise_device_spec_list>]
	remove [--deferred] [-f|--force] [--retry] <device>...
	remove_all [-f|--force]
	suspend [--noflush] [--nolockfs] <device>...
	resume [--noflush] [--nolockfs] <device>...
	       [--addnodeonresume|--addnodeoncreate]
	       [--readahead {[+]<sectors>|auto|none}]
	load <device> [<table>|<table_file>]
	clear <device>
	reload <device> [<table>|<table_file>]
	wipe_table [-f|--force] [--noflush] [--nolockfs] <device>...
	rename <device> [--setuuid] <new_name_or_uuid>
	measure [<device>...]
	message <device> <sector> <message>
	ls [--target <target_type>] [--exec <command>] [-o <options>] [--tree]
	info [<device>...]
	deps [-o <options>] [<device>...]
	stats <command> [<options>] [<device>...]
	status [<device>...] [--noflush] [--target <target_type>]
	table [<device>...] [--concise] [--target <target_type>] [--showkeys]
	wait <device> [<event_nr>] [--noflush]
	mknodes [<device>...]
	mangle [<device>...]
	udevcreatecookie 
	udevreleasecookie [<cookie>]
	udevflags <cookie>
	udevcomplete <cookie>
	udevcomplete_all [<age_in_minutes>]
	udevcookies 
	target-version [<target>...]
	targets 
	version 
	setgeometry <device> <cyl> <head> <sect> <start>
	splitname <device> [<subsystem>]

<device> may be device name or (if only one) -u <uuid> or -j <major> -m <minor>
<mangling_mode> is one of 'none', 'auto' and 'hex'.
<fields> are comma-separated.  Use 'help -c' for list.
<concise_device_specification> has single-device entries separated by semi-colons:
    <name>,<uuid>,<minor>,<flags>,<table>
        where <flags> is 'ro' or 'rw' (the default) and any of <uuid>, <minor>
        and <flags> may be empty. Separate extra table lines with commas.
    E.g.: dev1,,,,0 100 linear 253:1 0,100 100 error;dev2,,,ro,0 1 error
Table_file contents may be supplied on stdin.
Options are: devno, devname, blkdevname.
Tree specific options are: ascii, utf, vt100; compact, inverted, notrunc;
                           blkdevname, [no]device, active, open, rw and uuid.

```

***

**dmstats**

Device-mapper statistics management

```
:~# dmstats -h
Usage:

dmstats
        [-h|--help]
        [-v|--verbose [-v|--verbose ...]]
        [--areas <nr_areas>] [--areasize <size>]
        [--userdata <data>] [--clear]
        [--count <count>] [--interval <seconds>]
        [-o <fields>] [-O|--sort <sort_fields>]
	      [--programid <id>]
        [--start <start>] [--length <length>]
        [--segments] [--units <units>]

	help 
	clear [--allregions|--regionid id] [--alldevices|<device>...] 
	create [--start <start> [--length <len>]
	    [--areas <nr_areas>] [--areasize <size>] 
	    [--programid <id>] [--userdata <data> ] 
	    [--bounds histogram_boundaries] [--precise] 
	    [--segments] [--alldevices|<device>...] 
	create --filemap [--nogroup] [--nomonitor] [--follow mode]
	    [--programid <id>] [--userdata <data> ] 
	    [--bounds histogram_boundaries] [--precise] <file_path>
	delete [--allprograms|--programid id] 
	    [--allregions|--regionid id] 
	    [--alldevices|<device>...] 
	group [--alias NAME] --regions <regions>
	    [--allprograms|--programid id] [--alldevices|<device>...] 
	list [--allprograms|--programid id] [--allregions|--regionid id] 
	print [--clear] [--allprograms|--programid id] 
	    [--allregions|--regionid id] 
	    [--alldevices|<device>...] 
	report [--interval <seconds>] [--count <cnt>]
	    [--units <u>] [--programid <id>] [--regionid <id>] 
	    [-o <fields>] [-O|--sort <sort_fields>]
	    [-S|--select <selection>] [--nameprefixes]
	    [--noheadings] [--separator <separator>]
	    [--allprograms|--programid id] [<device>...]
	ungroup --groupid <id> [--allprograms|--programid id] 
	    [--alldevices|<device>...] 
	update_filemap --groupid <id> 
	    [--nomonitor] [--follow mode] <file_path>
	version 

<device> may be device name or (if only one) -u <uuid> or -j <major> -m <minor>
<fields> are comma-separated.  Use 'help -c' for list.

```

***

#### libdevmapper-dev <a href="#libdevmapper-dev" id="libdevmapper-dev"></a>

The Linux Kernel Device Mapper is the LVM (Linux Logical Volume Management) Team’s implementation of a minimalistic kernel-space driver that handles volume management, while keeping knowledge of the underlying device layout in user-space. This makes it useful for not only LVM, but software raid, and other drivers that create “virtual” block devices.

This package contains the (user-space) header files for accessing the device-mapper; it allow usage of the device-mapper through a clean, consistent interface (as opposed to through kernel ioctls).

**Installed size:** `164 KB`\
**How to install:** `sudo apt install libdevmapper-dev`

<details>

<summary>Dependencies:</summary>

* libdevmapper-event1.02.1
* libdevmapper1.02.1
* libselinux1-dev
* libudev-dev

</details>

***

#### libdevmapper-event1.02.1 <a href="#libdevmapper-event1021" id="libdevmapper-event1021"></a>

The Linux Kernel Device Mapper is the LVM (Linux Logical Volume Management) Team’s implementation of a minimalistic kernel-space driver that handles volume management, while keeping knowledge of the underlying device layout in user-space. This makes it useful for not only LVM, but software raid, and other drivers that create “virtual” block devices.

This package contains the userspace library to help with event monitoring for devmapper devices, in conjunction with the dmevent daemon.

**Installed size:** `53 KB`\
**How to install:** `sudo apt install libdevmapper-event1.02.1`

<details>

<summary>Dependencies:</summary>

* libc6
* libdevmapper1.02.1

</details>

***

#### libdevmapper1.02.1 <a href="#libdevmapper1021" id="libdevmapper1021"></a>

The Linux Kernel Device Mapper is the LVM (Linux Logical Volume Management) Team’s implementation of a minimalistic kernel-space driver that handles volume management, while keeping knowledge of the underlying device layout in user-space. This makes it useful for not only LVM, but software raid, and other drivers that create “virtual” block devices.

This package contains the (user-space) shared library for accessing the device-mapper; it allows usage of the device-mapper through a clean, consistent interface (as opposed to through kernel ioctls).

**Installed size:** `474 KB`\
**How to install:** `sudo apt install libdevmapper1.02.1`

<details>

<summary>Dependencies:</summary>

* dmsetup
* libc6
* libselinux1
* libudev1

</details>

***

#### liblvm2-dev <a href="#liblvm2-dev" id="liblvm2-dev"></a>

This package contains files needed to develop applications that use the lvm2app library.

**Installed size:** `20 KB`\
**How to install:** `sudo apt install liblvm2-dev`

<details>

<summary>Dependencies:</summary>

* libdevmapper-dev
* liblvm2cmd2.03

</details>

***

#### liblvm2cmd2.03 <a href="#liblvm2cmd203" id="liblvm2cmd203"></a>

This package contains the lvm2cmd shared library.

**Installed size:** `2.98 MB`\
**How to install:** `sudo apt install liblvm2cmd2.03`

<details>

<summary>Dependencies:</summary>

* dmeventd
* libaio1
* libblkid1
* libc6
* libdevmapper-event1.02.1
* libselinux1
* libsystemd0
* libudev1

</details>

***

#### lvm2 <a href="#lvm2" id="lvm2"></a>

This is LVM2, the rewrite of The Linux Logical Volume Manager. LVM supports enterprise level volume management of disk and disk subsystems by grouping arbitrary disks into volume groups. The total capacity of volume groups can be allocated to logical volumes, which are accessed as regular block devices.

**Installed size:** `3.91 MB`\
**How to install:** `sudo apt install lvm2`

<details>

<summary>Dependencies:</summary>

* dmeventd
* dmsetup
* libaio1
* libblkid1
* libc6
* libdevmapper-event1.02.1
* libedit2
* libselinux1
* libsystemd0
* libudev1
* lsb-base

</details>

**fsadm**

Utility to resize or check filesystem on a device

```
:~# fsadm -h
fsadm: Utility to resize or check the filesystem on a device

  fsadm [options] check <device>
    - Check the filesystem on device using fsck

  fsadm [options] resize <device> [<new_size>[BKMGTPE]]
    - Change the size of the filesystem on device to new_size

  Options:
    -h | --help         Show this help message
    -v | --verbose      Be verbose
    -e | --ext-offline  unmount filesystem before ext2/ext3/ext4 resize
    -f | --force        Bypass sanity checks
    -n | --dry-run      Print commands without running them
    -l | --lvresize     Resize given device (if it is LVM device)
    -c | --cryptresize  Resize given crypt device
    -y | --yes          Answer "yes" at any prompts

  new_size - Absolute number of filesystem blocks to be in the filesystem,
             or an absolute size using a suffix (in powers of 1024).
             If new_size is not supplied, the whole device is used.
```

***

**lvchange**

Change the attributes of logical volume(s)

```
:~# lvchange -h
  lvchange - Change the attributes of logical volume(s)

  Change a general LV attribute. 
  For options listed in parentheses, any one is 
  required, after which the others are optional.
  lvchange
	( -C|--contiguous y|n,
	  -p|--permission rw|r,
	  -r|--readahead auto|none|Number,
	  -k|--setactivationskip y|n,
	  -Z|--zero y|n,
	  -M|--persistent n,
	     --addtag Tag,
	     --deltag Tag,
	     --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit,
	     --compression y|n,
	     --deduplication y|n,
	     --detachprofile,
	     --metadataprofile String,
	     --profile String,
	     --setautoactivation y|n,
	     --errorwhenfull y|n,
	     --discards passdown|nopassdown|ignore,
	     --cachemode writethrough|writeback|passthrough,
	     --cachepolicy String,
	     --cachesettings String,
	     --minrecoveryrate Size[k|UNIT],
	     --maxrecoveryrate Size[k|UNIT],
	     --vdosettings String,
	     --writebehind Number,
	     --writemostly PV[:t|n|y] )
	 VG|LV|Tag|Select ...
	[ -a|--activate y|n|ay ]
	[    --poll y|n ]
	[    --monitor y|n ]
	[ COMMON_OPTIONS ]

  Resyncronize a mirror or raid LV. 
  Use to reset 'R' attribute on a not initially synchronized LV.
  lvchange --resync VG|LV|Tag|Select ...
	[ -a|--activate y|n|ay ]
	[ COMMON_OPTIONS ]

  Resynchronize or check a raid LV.
  lvchange --syncaction check|repair VG|LV|Tag|Select ...
	[ COMMON_OPTIONS ]

  Reconstruct data on specific PVs of a raid LV.
  lvchange --rebuild PV VG|LV|Tag|Select ...
	[ COMMON_OPTIONS ]

  Activate or deactivate an LV.
  lvchange -a|--activate y|n|ay VG|LV|Tag|Select ...
	[ -P|--partial ]
	[ -K|--ignoreactivationskip ]
	[    --activationmode partial|degraded|complete ]
	[    --poll y|n ]
	[    --monitor y|n ]
	[    --ignorelockingfailure ]
	[    --sysinit ]
	[    --readonly ]
	[ COMMON_OPTIONS ]

  Reactivate an LV using the latest metadata.
  lvchange --refresh VG|LV|Tag|Select ...
	[ -P|--partial ]
	[    --activationmode partial|degraded|complete ]
	[    --poll y|n ]
	[    --monitor y|n ]
	[ COMMON_OPTIONS ]

  Start or stop monitoring an LV from dmeventd.
  lvchange --monitor y|n VG|LV|Tag|Select ...
	[ COMMON_OPTIONS ]

  Start or stop processing an LV conversion.
  lvchange --poll y|n VG|LV|Tag|Select ...
	[    --monitor y|n ]
	[ COMMON_OPTIONS ]

  Make the minor device number persistent for an LV.
  lvchange -M|--persistent y --minor Number LV
	[ -j|--major Number ]
	[ -a|--activate y|n|ay ]
	[    --poll y|n ]
	[    --monitor y|n ]
	[ COMMON_OPTIONS ]

  Common options for command:
	[ -A|--autobackup y|n ]
	[ -f|--force ]
	[ -S|--select String ]
	[    --ignoremonitoring ]
	[    --noudevsync ]
	[    --reportformat basic|json ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvconvert**

Change logical volume layout

```
:~# lvconvert -h
  lvconvert - Change logical volume layout

  Convert LV to linear.
  lvconvert --type linear LV
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Convert LV to striped.
  lvconvert --type striped LV
	[ -I|--stripesize Size[k|UNIT] ]
	[ -R|--regionsize Size[m|UNIT] ]
	[ -i|--interval Number ]
	[    --stripes Number ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Convert LV to type mirror (also see type raid1),
  lvconvert --type mirror LV
	[ -m|--mirrors [+|-]Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -R|--regionsize Size[m|UNIT] ]
	[ -i|--interval Number ]
	[    --stripes Number ]
	[    --mirrorlog core|disk ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Convert LV to raid or change raid layout 
  (a specific raid level must be used, e.g. raid1).
  lvconvert --type raid LV
	[ -m|--mirrors [+|-]Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -R|--regionsize Size[m|UNIT] ]
	[ -i|--interval Number ]
	[    --stripes Number ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Convert LV to raid1 or mirror, or change number of mirror images.
  lvconvert -m|--mirrors [+|-]Number LV
	[ -R|--regionsize Size[m|UNIT] ]
	[ -i|--interval Number ]
	[    --mirrorlog core|disk ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Convert raid LV to change number of stripe images.
  lvconvert --stripes Number LV
	[ -i|--interval Number ]
	[ -R|--regionsize Size[m|UNIT] ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Convert raid LV to change the stripe size.
  lvconvert -I|--stripesize Size[k|UNIT] LV
	[ -i|--interval Number ]
	[ -R|--regionsize Size[m|UNIT] ]
	[ COMMON_OPTIONS ]

  Split images from a raid1 or mirror LV and use them to create a new LV.
  lvconvert --splitmirrors Number -n|--name LV_new LV
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Split images from a raid1 LV and track changes to origin for later merge.
  lvconvert --splitmirrors Number --trackchanges LV
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Merge LV images that were split from a raid1 LV.
  lvconvert --mergemirrors VG|LV|Tag ...
	[ COMMON_OPTIONS ]

  Convert LV to a thin LV, using the original LV as an external origin.
  lvconvert --type thin --thinpool LV LV
	[ -T|--thin ]
	[ -r|--readahead auto|none|Number ]
	[ -c|--chunksize Size[k|UNIT] ]
	[ -Z|--zero y|n ]
	[    --originname LV_new ]
	[    --poolmetadata LV ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[    --metadataprofile String ]
	[ COMMON_OPTIONS ]

  Attach a cache pool to an LV, converts the LV to type cache.
  lvconvert --type cache --cachepool LV LV
	[ -H|--cache ]
	[ -Z|--zero y|n ]
	[ -r|--readahead auto|none|Number ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachemetadataformat auto|1|2 ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --poolmetadata LV ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[    --metadataprofile String ]
	[ COMMON_OPTIONS ]

  Attach a writecache to an LV, converts the LV to type writecache.
  lvconvert --type writecache --cachevol LV LV
	[    --cachesettings String ]
	[ COMMON_OPTIONS ]

  Attach a cache to an LV, converts the LV to type cache.
  lvconvert --type cache --cachevol LV LV
	[ -H|--cache ]
	[ -Z|--zero y|n ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachemetadataformat auto|1|2 ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[ COMMON_OPTIONS ]

  Add a writecache to an LV, using a specified cache device.
  lvconvert --type writecache --cachedevice PV LV
	[    --cachesize Size[m|UNIT] ]
	[    --cachesettings String ]
	[ COMMON_OPTIONS ]

  Add a cache to an LV, using a specified cache device.
  lvconvert --type cache --cachedevice PV LV
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachesize Size[m|UNIT] ]
	[    --cachesettings String ]
	[ COMMON_OPTIONS ]

  Convert LV to type thin-pool.
  lvconvert --type thin-pool LV
	[ -I|--stripesize Size[k|UNIT] ]
	[ -r|--readahead auto|none|Number ]
	[ -c|--chunksize Size[k|UNIT] ]
	[ -Z|--zero y|n ]
	[    --stripes Number ]
	[    --discards passdown|nopassdown|ignore ]
	[    --errorwhenfull y|n ]
	[    --poolmetadata LV ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[    --metadataprofile String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Convert LV to type cache-pool.
  lvconvert --type cache-pool LV
	[ -Z|--zero y|n ]
	[ -r|--readahead auto|none|Number ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachemetadataformat auto|1|2 ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --poolmetadata LV ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[    --metadataprofile String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Convert LV to type vdopool.
  lvconvert --type vdo-pool LV
	[ -n|--name LV_new ]
	[ -V|--virtualsize Size[m|UNIT] ]
	[ -r|--readahead auto|none|Number ]
	[ -Z|--zero y|n ]
	[    --metadataprofile String ]
	[    --compression y|n ]
	[    --deduplication y|n ]
	[    --vdosettings String ]
	[ COMMON_OPTIONS ]

  Detach a cache from an LV.
  lvconvert --splitcache LV
	[    --cachesettings String ]
	[ COMMON_OPTIONS ]

  Merge thin LV into its origin LV.
  lvconvert --mergethin LV ...
	[ COMMON_OPTIONS ]

  Merge COW snapshot LV into its origin.
  lvconvert --mergesnapshot LV ...
	[ -i|--interval Number ]
	[ COMMON_OPTIONS ]

  Combine a former COW snapshot (second arg) with a former 
  origin LV (first arg) to reverse a splitsnapshot command.
  lvconvert --type snapshot LV LV
	[ -s|--snapshot ]
	[ -c|--chunksize Size[k|UNIT] ]
	[ -Z|--zero y|n ]
	[ COMMON_OPTIONS ]

  Replace failed PVs in a raid or mirror LV. 
  Repair a thin pool. 
  Repair a cache pool.
  lvconvert --repair LV
	[ -i|--interval Number ]
	[    --usepolicies ]
	[    --poolmetadataspare y|n ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Replace specific PV(s) in a raid LV with another PV.
  lvconvert --replace PV LV
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Poll LV to continue conversion.
  lvconvert --startpoll LV
	[ COMMON_OPTIONS ]

  Add or remove data integrity checksums to raid images.
  lvconvert --raidintegrity y|n LV
	[    --raidintegritymode String ]
	[    --raidintegrityblocksize Number ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Common options for command:
	[ -b|--background ]
	[ -f|--force ]
	[    --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit ]
	[    --noudevsync ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvcreate**

Create a logical volume

```
:~# lvcreate -h
  lvcreate - Create a logical volume

  Create a linear LV.
  lvcreate -L|--size Size[m|UNIT] VG
	[ --type linear ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a striped LV.
  lvcreate -i|--stripes Number -L|--size Size[m|UNIT] VG
	[ --type striped ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a raid1 or mirror LV.
  lvcreate -m|--mirrors Number -L|--size Size[m|UNIT] VG
	[ --type raid1|mirror ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -R|--regionsize Size[m|UNIT] ]
	[    --mirrorlog core|disk ]
	[    --minrecoveryrate Size[k|UNIT] ]
	[    --maxrecoveryrate Size[k|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a raid LV (a specific raid level must be used, e.g. raid1).
  lvcreate --type raid -L|--size Size[m|UNIT] VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -m|--mirrors Number ]
	[ -R|--regionsize Size[m|UNIT] ]
	[    --minrecoveryrate Size[k|UNIT] ]
	[    --maxrecoveryrate Size[k|UNIT] ]
	[    --raidintegrity y|n ]
	[    --raidintegritymode String ]
	[    --raidintegrityblocksize Number ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a raid10 LV.
  lvcreate -m|--mirrors Number -i|--stripes Number -L|--size Size[m|UNIT] VG
	[ --type raid10 ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -R|--regionsize Size[m|UNIT] ]
	[    --minrecoveryrate Size[k|UNIT] ]
	[    --maxrecoveryrate Size[k|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a COW snapshot LV of an origin LV.
  lvcreate -s|--snapshot -L|--size Size[m|UNIT] LV
	[ --type snapshot ] (implied)
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -c|--chunksize Size[k|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a thin pool.
  lvcreate --type thin-pool -L|--size Size[m|UNIT] VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -T|--thin ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --thinpool LV_new ]
	[    --discards passdown|nopassdown|ignore ]
	[    --errorwhenfull y|n ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a cache pool.
  lvcreate --type cache-pool -L|--size Size[m|UNIT] VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -H|--cache ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --cachemetadataformat auto|1|2 ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a thin LV in a thin pool.
  lvcreate -V|--virtualsize Size[m|UNIT] --thinpool LV VG
	[ --type thin ] (implied)
	[ -T|--thin ]
	[ COMMON_OPTIONS ]

  Create a thin LV that is a snapshot of an existing thin LV.
  lvcreate -s|--snapshot LV
	[ --type thin ] (implied)
	[ COMMON_OPTIONS ]

  Create a thin LV that is a snapshot of an external origin LV.
  lvcreate --type thin --thinpool LV LV
	[ -T|--thin ]
	[ COMMON_OPTIONS ]

  Create a LV that returns VDO when used.
  lvcreate --type vdo -L|--size Size[m|UNIT] VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -V|--virtualsize Size[m|UNIT] ]
	[    --vdo ]
	[    --vdopool LV_new ]
	[    --compression y|n ]
	[    --deduplication y|n ]
	[    --vdosettings String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach the specified cachepool 
  which converts the new LV to type cache.
  lvcreate --type cache -L|--size Size[m|UNIT] --cachepool LV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -H|--cache ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --cachemetadataformat auto|1|2 ]
	[    --poolmetadatasize Size[m|UNIT] ]
	[    --poolmetadataspare y|n ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach the specified cachevol 
  which converts the new LV to type cache.
  lvcreate --type cache -L|--size Size[m|UNIT] --cachevol LV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --cachemetadataformat auto|1|2 ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach a cachevol created from 
  the specified cache device, which converts the 
  new LV to type cache.
  lvcreate --type cache -L|--size Size[m|UNIT] --cachedevice PV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -c|--chunksize Size[k|UNIT] ]
	[    --cachesize Size[m|UNIT] ]
	[    --cachemode writethrough|writeback|passthrough ]
	[    --cachepolicy String ]
	[    --cachesettings String ]
	[    --cachemetadataformat auto|1|2 ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach the specified cachevol 
  which converts the new LV to type writecache.
  lvcreate --type writecache -L|--size Size[m|UNIT] --cachevol LV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[    --cachesettings String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Create a new LV, then attach a cachevol created from 
  the specified cache device, which converts the 
  new LV to type writecache.
  lvcreate --type writecache -L|--size Size[m|UNIT] --cachedevice PV VG
	[ -l|--extents Number[PERCENT] ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[    --cachesize Size[m|UNIT] ]
	[    --cachesettings String ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Common options for command:
	[ -a|--activate y|n|ay ]
	[ -A|--autobackup y|n ]
	[ -C|--contiguous y|n ]
	[ -M|--persistent y|n ]
	[ -j|--major Number ]
	[ -k|--setactivationskip y|n ]
	[ -K|--ignoreactivationskip ]
	[ -n|--name String ]
	[ -p|--permission rw|r ]
	[ -r|--readahead auto|none|Number ]
	[ -W|--wipesignatures y|n ]
	[ -Z|--zero y|n ]
	[    --addtag Tag ]
	[    --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit ]
	[    --setautoactivation y|n ]
	[    --ignoremonitoring ]
	[    --metadataprofile String ]
	[    --minor Number ]
	[    --monitor y|n ]
	[    --nosync ]
	[    --noudevsync ]
	[    --reportformat basic|json ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvdisplay**

Display information about a logical volume

```
:~# lvdisplay -h
  lvdisplay - Display information about a logical volume

  lvdisplay
	[ -a|--all ]
	[ -c|--colon ]
	[ -C|--columns ]
	[ -H|--history ]
	[ -m|--maps ]
	[ -o|--options String ]
	[ -O|--sort String ]
	[ -S|--select String ]
	[    --aligned ]
	[    --binary ]
	[    --configreport log|vg|lv|pv|pvseg|seg ]
	[    --foreign ]
	[    --ignorelockingfailure ]
	[    --logonly ]
	[    --noheadings ]
	[    --nosuffix ]
	[    --readonly ]
	[    --segments ]
	[    --separator String ]
	[    --shared ]
	[    --unbuffered ]
	[    --units [Number]r|R|h|H|b|B|s|S|k|K|m|M|g|G|t|T|p|P|e|E ]
	[ COMMON_OPTIONS ]
	[ VG|LV|Tag ... ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvextend**

Add space to a logical volume

```
:~# lvextend -h
  lvextend - Add space to a logical volume

  Extend an LV by a specified size.
  lvextend -L|--size [+]Size[m|UNIT] LV
	[ -l|--extents [+]Number[PERCENT] ]
	[ -r|--resizefs ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[    --poolmetadatasize [+]Size[m|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Extend an LV by specified PV extents.
  lvextend LV PV ...
	[ -r|--resizefs ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ COMMON_OPTIONS ]

  Extend a pool metadata SubLV by a specified size.
  lvextend --poolmetadatasize [+]Size[m|UNIT] LV
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Extend an LV according to a predefined policy.
  lvextend --usepolicies LV
	[ -r|--resizefs ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Common options for command:
	[ -A|--autobackup y|n ]
	[ -f|--force ]
	[ -m|--mirrors Number ]
	[ -n|--nofsck ]
	[    --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit ]
	[    --nosync ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[    --type linear|striped|snapshot|raid|mirror|thin|thin-pool|vdo|vdo-pool|cache|cache-pool|writecache ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvm**

LVM2 tools

```
:~# lvm -h
  Available lvm commands:
  Use 'lvm help <command>' for more information
   
  config          Display and manipulate configuration information
  devtypes        Display recognised built-in block device types
  dumpconfig      Display and manipulate configuration information
  formats         List available metadata formats
  fullreport      Display full report
  help            Display help for commands
  lastlog         Display last command's log report
  lvchange        Change the attributes of logical volume(s)
  lvconvert       Change logical volume layout
  lvcreate        Create a logical volume
  lvdisplay       Display information about a logical volume
  lvextend        Add space to a logical volume
  lvmchange       With the device mapper, this is obsolete and does nothing.
  lvmconfig       Display and manipulate configuration information
  lvmdevices      Manage the devices file
  lvmdiskscan     List devices that may be used as physical volumes
  lvmsadc         Collect activity data
  lvmsar          Create activity report
  lvpoll          Continue already initiated poll operation on a logical volume
  lvreduce        Reduce the size of a logical volume
  lvremove        Remove logical volume(s) from the system
  lvrename        Rename a logical volume
  lvresize        Resize a logical volume
  lvs             Display information about logical volumes
  lvscan          List all logical volumes in all volume groups
  pvchange        Change attributes of physical volume(s)
  pvck            Check metadata on physical volumes
  pvcreate        Initialize physical volume(s) for use by LVM
  pvdata          Display the on-disk metadata for physical volume(s)
  pvdisplay       Display various attributes of physical volume(s)
  pvmove          Move extents from one physical volume to another
  pvremove        Remove LVM label(s) from physical volume(s)
  pvresize        Resize physical volume(s)
  pvs             Display information about physical volumes
  pvscan          List all physical volumes
  segtypes        List available segment types
  systemid        Display the system ID, if any, currently set on this host
  tags            List tags defined on this host
  version         Display software and driver version information
  vgcfgbackup     Backup volume group configuration(s)
  vgcfgrestore    Restore volume group configuration
  vgchange        Change volume group attributes
  vgck            Check the consistency of volume group(s)
  vgconvert       Change volume group metadata format
  vgcreate        Create a volume group
  vgdisplay       Display volume group information
  vgexport        Unregister volume group(s) from the system
  vgextend        Add physical volumes to a volume group
  vgimport        Register exported volume group with system
  vgimportclone   Import a VG from cloned PVs
  vgimportdevices Add devices for a VG to the devices file.
  vgmerge         Merge volume groups
  vgmknodes       Create the special files for volume group devices in /dev
  vgreduce        Remove physical volume(s) from a volume group
  vgremove        Remove volume group(s)
  vgrename        Rename a volume group
  vgs             Display information about volume groups
  vgscan          Search for all volume groups
  vgsplit         Move physical volumes into a new or existing volume group
```

***

**lvmconfig**

Display and manipulate configuration information

```
:~# lvmconfig -h
  lvmconfig - Display and manipulate configuration information

  lvmconfig
	[ -f|--file String ]
	[ -l|--list ]
	[    --atversion String ]
	[    --typeconfig current|default|diff|full|list|missing|new|profilable|profilable-command|profilable-metadata ]
	[    --ignoreadvanced ]
	[    --ignoreunsupported ]
	[    --ignorelocal ]
	[    --mergedconfig ]
	[    --metadataprofile String ]
	[    --sinceversion String ]
	[    --showdeprecated ]
	[    --showunsupported ]
	[    --validate ]
	[    --withsummary ]
	[    --withcomments ]
	[    --withgeneralpreamble ]
	[    --withlocalpreamble ]
	[    --withspaces ]
	[    --unconfigured ]
	[    --withversions ]
	[ COMMON_OPTIONS ]
	[ String ... ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvmdiskscan**

List devices that may be used as physical volumes

```
:~# lvmdiskscan -h
  lvmdiskscan - List devices that may be used as physical volumes

  lvmdiskscan
	[ -l|--lvmpartition ]
	[    --readonly ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvmdump**

Create lvm2 information dumps for diagnostic purposes

```
:~# lvmdump --help
/usr/sbin/lvmdump: unknown option -
/usr/sbin/lvmdump [options]
    -h print this message
    -a advanced collection - warning: if lvm is already hung,
       then this script may hang as well if -a is used
    -c if running clvmd, gather cluster data as well
    -d <directory> dump into a directory instead of tarball
    -l gather lvmetad state if running
    -p gather lvmpolld state if running
    -m gather LVM metadata from the PVs
    -s gather system info and context
    -u gather udev info and context

```

***

**lvmpolld**

LVM poll daemon

```
:~# lvmpolld -h
Usage:
lvmpolld [-V] [-h] [-f] [-l {all|wire|debug}] [-s path] [-B path] [-p path] [-t secs]
lvmpolld --dump [-s path]
   -V|--version     Show version info
   -h|--help        Show this help information
   -f|--foreground  Don't fork, run in the foreground
   --dump           Dump full lvmpolld state
   -l|--log         Logging message level (-l {all|wire|debug})
   -p|--pidfile     Set path to the pidfile
   -s|--socket      Set path to the communication socket
   -B|--binary      Path to lvm2 binary
   -t|--timeout     Time to wait in seconds before shutdown on idle (missing or 0 = inifinite)

```

***

**lvmsadc**

LVM system activity data collector

```
:~# lvmsadc -h
  lvmsadc - Collect activity data

  lvmsadc
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvmsar**

LVM system activity reporter

```
:~# lvmsar -h
  lvmsar - Create activity report

  lvmsar
	[ -f|--full ]
	[ -s|--stdin ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvreduce**

Reduce the size of a logical volume

```
:~# lvreduce -h
  lvreduce - Reduce the size of a logical volume

  lvreduce -L|--size [-]Size[m|UNIT] LV
	[ -l|--extents [-]Number[PERCENT] ]
	[ -A|--autobackup y|n ]
	[ -f|--force ]
	[ -n|--nofsck ]
	[ -r|--resizefs ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvremove**

Remove logical volume(s) from the system

```
:~# lvremove -h
  lvremove - Remove logical volume(s) from the system

  lvremove VG|LV|Tag|Select ...
	[ -A|--autobackup y|n ]
	[ -f|--force ]
	[ -S|--select String ]
	[    --nohistory ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvrename**

Rename a logical volume

```
:~# lvrename -h
  lvrename - Rename a logical volume

  lvrename VG LV LV_new
	[ COMMON_OPTIONS ]

  lvrename LV LV_new
	[ COMMON_OPTIONS ]

  Common options for command:
	[ -A|--autobackup y|n ]
	[    --noudevsync ]
	[    --reportformat basic|json ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvresize**

Resize a logical volume

```
:~# lvresize -h
  lvresize - Resize a logical volume

  Resize an LV by a specified size.
  lvresize -L|--size [+|-]Size[m|UNIT] LV
	[ -l|--extents [+|-]Number[PERCENT] ]
	[ -r|--resizefs ]
	[    --poolmetadatasize [+]Size[m|UNIT] ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Resize an LV by specified PV extents.
  lvresize LV PV ...
	[ -r|--resizefs ]
	[ COMMON_OPTIONS ]

  Resize a pool metadata SubLV by a specified size.
  lvresize --poolmetadatasize [+]Size[m|UNIT] LV
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Common options for command:
	[ -A|--autobackup y|n ]
	[ -f|--force ]
	[ -i|--stripes Number ]
	[ -I|--stripesize Size[k|UNIT] ]
	[ -n|--nofsck ]
	[    --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit ]
	[    --nosync ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[    --type linear|striped|snapshot|raid|mirror|thin|thin-pool|vdo|vdo-pool|cache|cache-pool|writecache ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvs**

Display information about logical volumes

```
:~# lvs -h
  lvs - Display information about logical volumes

  lvs
	[ -H|--history ]
	[ -a|--all ]
	[ -o|--options String ]
	[ -S|--select String ]
	[ -O|--sort String ]
	[    --segments ]
	[    --aligned ]
	[    --binary ]
	[    --configreport log|vg|lv|pv|pvseg|seg ]
	[    --foreign ]
	[    --ignorelockingfailure ]
	[    --logonly ]
	[    --nameprefixes ]
	[    --noheadings ]
	[    --nosuffix ]
	[    --readonly ]
	[    --reportformat basic|json ]
	[    --rows ]
	[    --separator String ]
	[    --shared ]
	[    --unbuffered ]
	[    --units [Number]r|R|h|H|b|B|s|S|k|K|m|M|g|G|t|T|p|P|e|E ]
	[    --unquoted ]
	[ COMMON_OPTIONS ]
	[ VG|LV|Tag ... ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**lvscan**

List all logical volumes in all volume groups

```
ali:~# lvscan -h
  lvscan - List all logical volumes in all volume groups

  lvscan
	[ -a|--all ]
	[ -b|--blockdevice ]
	[    --ignorelockingfailure ]
	[    --readonly ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**pvchange**

Change attributes of physical volume(s)

```
:~# pvchange -h
  pvchange - Change attributes of physical volume(s)

  Change properties of all PVs.
  pvchange -a|--all
	( -x|--allocatable y|n,
	  -u|--uuid,
	     --addtag Tag,
	     --deltag Tag,
	     --metadataignore y|n )

	[ COMMON_OPTIONS ]

  Change properties of specified PVs.
  pvchange
	( -x|--allocatable y|n,
	  -u|--uuid,
	     --addtag Tag,
	     --deltag Tag,
	     --metadataignore y|n )
	 PV|Select ...
	[ -S|--select String ]
	[ COMMON_OPTIONS ]

  Common options for command:
	[ -A|--autobackup y|n ]
	[ -f|--force ]
	[ -u|--uuid ]
	[    --reportformat basic|json ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**pvck**

Check metadata on physical volumes

```
:~# pvck -h
  pvck - Check metadata on physical volumes

  Check for metadata on a device
  pvck PV ...
	[ COMMON_OPTIONS ]

  Check and print LVM headers and metadata on a device
  pvck --dump headers|metadata|metadata_all|metadata_search PV
	[ -f|--file String ]
	[    --settings String ]
	[    --pvmetadatacopies 0|1|2 ]
	[ COMMON_OPTIONS ]

  Repair LVM headers or metadata on a device
  pvck --repairtype pv_header|metadata|label_header PV
	[ -f|--file String ]
	[    --settings String ]
	[ COMMON_OPTIONS ]

  Repair LVM headers and metadata on a device
  pvck --repair -f|--file String PV
	[    --settings String ]
	[ COMMON_OPTIONS ]

  Common options for command:
	[    --labelsector Number ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**pvcreate**

Initialize physical volume(s) for use by LVM

```
:~# pvcreate -h
  pvcreate - Initialize physical volume(s) for use by LVM

  pvcreate PV ...
	[ -f|--force ]
	[ -M|--metadatatype lvm2 ]
	[ -u|--uuid String ]
	[ -Z|--zero y|n ]
	[    --dataalignment Size[k|UNIT] ]
	[    --dataalignmentoffset Size[k|UNIT] ]
	[    --bootloaderareasize Size[m|UNIT] ]
	[    --labelsector Number ]
	[    --pvmetadatacopies 0|1|2 ]
	[    --metadatasize Size[m|UNIT] ]
	[    --metadataignore y|n ]
	[    --norestorefile ]
	[    --setphysicalvolumesize Size[m|UNIT] ]
	[    --reportformat basic|json ]
	[    --restorefile String ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**pvdisplay**

Display various attributes of physical volume(s)

```
:~# pvdisplay -h
  pvdisplay - Display various attributes of physical volume(s)

  pvdisplay
	[ -a|--all ]
	[ -c|--colon ]
	[ -C|--columns ]
	[ -m|--maps ]
	[ -o|--options String ]
	[ -S|--select String ]
	[ -s|--short ]
	[ -O|--sort String ]
	[    --aligned ]
	[    --binary ]
	[    --configreport log|vg|lv|pv|pvseg|seg ]
	[    --foreign ]
	[    --ignorelockingfailure ]
	[    --logonly ]
	[    --noheadings ]
	[    --nosuffix ]
	[    --readonly ]
	[    --separator String ]
	[    --shared ]
	[    --unbuffered ]
	[    --units [Number]r|R|h|H|b|B|s|S|k|K|m|M|g|G|t|T|p|P|e|E ]
	[ COMMON_OPTIONS ]
	[ PV|Tag ... ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**pvmove**

Move extents from one physical volume to another

```
:~# pvmove -h
  pvmove - Move extents from one physical volume to another

  Move PV extents.
  pvmove PV
	[ -A|--autobackup y|n ]
	[ -n|--name LV ]
	[    --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit ]
	[    --atomic ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]
	[ PV ... ]

  Continue or abort existing pvmove operations.
  pvmove
	[ COMMON_OPTIONS ]

  Common options for command:
	[ -b|--background ]
	[ -i|--interval Number ]
	[    --abort ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**pvremove**

Remove LVM label(s) from physical volume(s)

```
:~# pvremove -h
  pvremove - Remove LVM label(s) from physical volume(s)

  pvremove PV ...
	[ -f|--force ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**pvresize**

Resize physical volume(s)

```
:~# pvresize -h
  pvresize - Resize physical volume(s)

  pvresize PV ...
	[    --setphysicalvolumesize Size[m|UNIT] ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**pvs**

Display information about physical volumes

```
:~# pvs -h
  pvs - Display information about physical volumes

  pvs
	[ -a|--all ]
	[ -o|--options String ]
	[ -S|--select String ]
	[ -O|--sort String ]
	[    --segments ]
	[    --aligned ]
	[    --binary ]
	[    --configreport log|vg|lv|pv|pvseg|seg ]
	[    --foreign ]
	[    --ignorelockingfailure ]
	[    --logonly ]
	[    --nameprefixes ]
	[    --noheadings ]
	[    --nosuffix ]
	[    --readonly ]
	[    --reportformat basic|json ]
	[    --rows ]
	[    --separator String ]
	[    --shared ]
	[    --unbuffered ]
	[    --units [Number]r|R|h|H|b|B|s|S|k|K|m|M|g|G|t|T|p|P|e|E ]
	[    --unquoted ]
	[ COMMON_OPTIONS ]
	[ PV|Tag ... ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**pvscan**

List all physical volumes

```
:~# pvscan -h
  pvscan - List all physical volumes

  Display PV information.
  pvscan
	[ -e|--exported ]
	[ -n|--novolumegroup ]
	[ -s|--short ]
	[ -u|--uuid ]
	[    --ignorelockingfailure ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]

  Record that a PV is online or offline.
  pvscan --cache
	[ -j|--major Number ]
	[    --ignorelockingfailure ]
	[    --reportformat basic|json ]
	[    --minor Number ]
	[    --noudevsync ]
	[ COMMON_OPTIONS ]
	[ String|PV ... ]

  Record that a PV is online and autoactivate the VG if complete.
  pvscan --cache -a|--activate ay
	[ -j|--major Number ]
	[    --ignorelockingfailure ]
	[    --reportformat basic|json ]
	[    --minor Number ]
	[    --noudevsync ]
	[    --autoactivation String ]
	[ COMMON_OPTIONS ]
	[ String|PV ... ]

  Record that a PV is online and list the VG using the PV.
  pvscan --cache --listvg PV
	[    --ignorelockingfailure ]
	[    --checkcomplete ]
	[    --vgonline ]
	[    --udevoutput ]
	[    --autoactivation String ]
	[ COMMON_OPTIONS ]

  Record that a PV is online and list LVs using the PV.
  pvscan --cache --listlvs PV
	[    --ignorelockingfailure ]
	[    --checkcomplete ]
	[    --vgonline ]
	[ COMMON_OPTIONS ]

  List LVs using the PV.
  pvscan --listlvs PV
	[ COMMON_OPTIONS ]

  List the VG using the PV.
  pvscan --listvg PV
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgcfgbackup**

Backup volume group configuration(s)

```
:~# vgcfgbackup -h
  vgcfgbackup - Backup volume group configuration(s)

  vgcfgbackup
	[ -f|--file String ]
	[    --foreign ]
	[    --ignorelockingfailure ]
	[    --readonly ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]
	[ VG ... ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgcfgrestore**

Restore volume group configuration

```
:~# vgcfgrestore -h
  vgcfgrestore - Restore volume group configuration

  Restore VG metadata from last backup.
  vgcfgrestore VG
	[ COMMON_OPTIONS ]

  Restore VG metadata from specified file.
  vgcfgrestore -f|--file String VG
	[ COMMON_OPTIONS ]

  List all VG metadata backups.
  vgcfgrestore -l|--list VG
	[ COMMON_OPTIONS ]

  List one VG metadata backup file.
  vgcfgrestore -l|--list -f|--file String
	[ COMMON_OPTIONS ]
	[ VG ]

  Common options for command:
	[ -M|--metadatatype lvm2 ]
	[    --force ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgchange**

Change volume group attributes

```
:~# vgchange -h
  vgchange - Change volume group attributes

  Change a general VG attribute. 
  For options listed in parentheses, any one is 
  required, after which the others are optional.
  vgchange
	( -l|--logicalvolume Number,
	  -p|--maxphysicalvolumes Number,
	  -u|--uuid,
	  -s|--physicalextentsize Size[m|UNIT],
	  -x|--resizeable y|n,
	     --addtag Tag,
	     --deltag Tag,
	     --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit,
	     --pvmetadatacopies 0|1|2,
	     --vgmetadatacopies all|unmanaged|Number,
	     --profile String,
	     --detachprofile,
	     --metadataprofile String,
	     --setautoactivation y|n )

	[ -A|--autobackup y|n ]
	[ -S|--select String ]
	[ -f|--force ]
	[    --poll y|n ]
	[    --ignoremonitoring ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]
	[ VG|Tag|Select ... ]

  Start or stop monitoring LVs from dmeventd.
  vgchange --monitor y|n
	[ -A|--autobackup y|n ]
	[ -S|--select String ]
	[ -f|--force ]
	[    --sysinit ]
	[    --ignorelockingfailure ]
	[    --poll y|n ]
	[    --ignoremonitoring ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]
	[ VG|Tag|Select ... ]

  Start or stop processing LV conversions.
  vgchange --poll y|n
	[ -A|--autobackup y|n ]
	[ -S|--select String ]
	[ -f|--force ]
	[    --ignorelockingfailure ]
	[    --ignoremonitoring ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]
	[ VG|Tag|Select ... ]

  Activate or deactivate LVs.
  vgchange -a|--activate y|n|ay
	[ -K|--ignoreactivationskip ]
	[ -P|--partial ]
	[ -A|--autobackup y|n ]
	[ -S|--select String ]
	[ -f|--force ]
	[    --activationmode partial|degraded|complete ]
	[    --sysinit ]
	[    --readonly ]
	[    --ignorelockingfailure ]
	[    --monitor y|n ]
	[    --poll y|n ]
	[    --autoactivation String ]
	[    --ignoremonitoring ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]
	[ VG|Tag|Select ... ]

  Reactivate LVs using the latest metadata.
  vgchange --refresh
	[ -A|--autobackup y|n ]
	[ -S|--select String ]
	[ -f|--force ]
	[    --sysinit ]
	[    --ignorelockingfailure ]
	[    --poll y|n ]
	[    --ignoremonitoring ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]
	[ VG|Tag|Select ... ]

  Change the system ID of a VG.
  vgchange --systemid String VG
	[ COMMON_OPTIONS ]

  Start the lockspace of a shared VG in lvmlockd.
  vgchange --lockstart
	[ -S|--select String ]
	[ COMMON_OPTIONS ]
	[ VG|Tag|Select ... ]

  Stop the lockspace of a shared VG in lvmlockd.
  vgchange --lockstop
	[ -S|--select String ]
	[ COMMON_OPTIONS ]
	[ VG|Tag|Select ... ]

  Change the lock type for a shared VG.
  vgchange --locktype sanlock|dlm|none VG
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgck**

Check the consistency of volume group(s)

```
:~# vgck -h
  vgck - Check the consistency of volume group(s)

  Read and display information about a VG.
  vgck
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]
	[ VG|Tag ... ]

  Rewrite VG metadata to correct problems.
  vgck --updatemetadata VG
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgconvert**

Change volume group metadata format

```
:~# vgconvert -h
  vgconvert - Change volume group metadata format

  vgconvert VG ...
	[ -f|--force ]
	[ -M|--metadatatype lvm2 ]
	[    --labelsector Number ]
	[    --bootloaderareasize Size[m|UNIT] ]
	[    --pvmetadatacopies 0|1|2 ]
	[    --metadatasize Size[m|UNIT] ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgcreate**

Create a volume group

```
:~# vgcreate -h
  vgcreate - Create a volume group

  vgcreate VG_new PV ...
	[ -A|--autobackup y|n ]
	[ -c|--clustered y|n ]
	[ -l|--maxlogicalvolumes Number ]
	[ -p|--maxphysicalvolumes Number ]
	[ -M|--metadatatype lvm2 ]
	[ -s|--physicalextentsize Size[m|UNIT] ]
	[ -f|--force ]
	[ -Z|--zero y|n ]
	[    --addtag Tag ]
	[    --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit ]
	[    --metadataprofile String ]
	[    --labelsector Number ]
	[    --metadatasize Size[m|UNIT] ]
	[    --pvmetadatacopies 0|1|2 ]
	[    --vgmetadatacopies all|unmanaged|Number ]
	[    --reportformat basic|json ]
	[    --dataalignment Size[k|UNIT] ]
	[    --dataalignmentoffset Size[k|UNIT] ]
	[    --shared ]
	[    --systemid String ]
	[    --locktype sanlock|dlm|none ]
	[    --setautoactivation y|n ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgdisplay**

Display volume group information

```
:~# vgdisplay -h
  vgdisplay - Display volume group information

  vgdisplay
	[ -A|--activevolumegroups ]
	[ -c|--colon ]
	[ -C|--columns ]
	[ -o|--options String ]
	[ -S|--select String ]
	[ -s|--short ]
	[ -O|--sort String ]
	[    --aligned ]
	[    --binary ]
	[    --configreport log|vg|lv|pv|pvseg|seg ]
	[    --foreign ]
	[    --ignorelockingfailure ]
	[    --logonly ]
	[    --noheadings ]
	[    --nosuffix ]
	[    --readonly ]
	[    --shared ]
	[    --separator String ]
	[    --unbuffered ]
	[    --units [Number]r|R|h|H|b|B|s|S|k|K|m|M|g|G|t|T|p|P|e|E ]
	[ COMMON_OPTIONS ]
	[ VG|Tag ... ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgexport**

Unregister volume group(s) from the system

```
:~# vgexport -h
  vgexport - Unregister volume group(s) from the system

  Export specified VGs.
  vgexport VG|Tag|Select ...
	[ -S|--select String ]
	[ COMMON_OPTIONS ]

  Export all VGs.
  vgexport -a|--all
	[ COMMON_OPTIONS ]

  Common options for command:
	[    --reportformat basic|json ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgextend**

Add physical volumes to a volume group

```
:~# vgextend -h
  vgextend - Add physical volumes to a volume group

  vgextend VG PV ...
	[ -A|--autobackup y|n ]
	[ -f|--force ]
	[ -Z|--zero y|n ]
	[ -M|--metadatatype lvm2 ]
	[    --labelsector Number ]
	[    --metadatasize Size[m|UNIT] ]
	[    --pvmetadatacopies 0|1|2 ]
	[    --metadataignore y|n ]
	[    --dataalignment Size[k|UNIT] ]
	[    --dataalignmentoffset Size[k|UNIT] ]
	[    --reportformat basic|json ]
	[    --restoremissing ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgimport**

Register exported volume group with system

```
:~# vgimport -h
  vgimport - Register exported volume group with system

  Import specified VGs.
  vgimport VG|Tag|Select ...
	[ -S|--select String ]
	[ COMMON_OPTIONS ]

  Import all VGs.
  vgimport -a|--all
	[ COMMON_OPTIONS ]

  Common options for command:
	[ -f|--force ]
	[    --reportformat basic|json ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgimportclone**

Import a VG from cloned PVs

```
:~# vgimportclone -h
  vgimportclone - Import a VG from cloned PVs

  vgimportclone PV ...
	[ -n|--basevgname VG ]
	[ -i|--import ]
	[    --importdevices ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgmerge**

Merge volume groups

```
:~# vgmerge -h
  vgmerge - Merge volume groups

  vgmerge VG VG
	[ -A|--autobackup y|n ]
	[ -l|--list ]
	[    --poolmetadataspare y|n ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgmknodes**

Create the special files for volume group devices in /dev

```
:~# vgmknodes -h
  vgmknodes - Create the special files for volume group devices in /dev

  vgmknodes
	[    --ignorelockingfailure ]
	[    --refresh ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]
	[ VG|LV|Tag ... ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgreduce**

Remove physical volume(s) from a volume group

```
:~# vgreduce -h
  vgreduce - Remove physical volume(s) from a volume group

  Remove a PV from a VG.
  vgreduce VG PV ...
	[ COMMON_OPTIONS ]

  Remove all unused PVs from a VG.
  vgreduce -a|--all VG
	[ COMMON_OPTIONS ]

  Remove all missing PVs from a VG.
  vgreduce --removemissing VG
	[    --mirrorsonly ]
	[ COMMON_OPTIONS ]

  Common options for command:
	[ -A|--autobackup y|n ]
	[ -f|--force ]
	[    --reportformat basic|json ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgremove**

Remove volume group(s)

```
:~# vgremove -h
  vgremove - Remove volume group(s)

  vgremove VG|Tag|Select ...
	[ -f|--force ]
	[ -S|--select String ]
	[    --noudevsync ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgrename**

Rename a volume group

```
:~# vgrename -h
  vgrename - Rename a volume group

  Rename a VG.
  vgrename VG VG_new
	[ COMMON_OPTIONS ]

  Rename a VG by specifying the VG UUID.
  vgrename String VG_new
	[ COMMON_OPTIONS ]

  Common options for command:
	[ -A|--autobackup y|n ]
	[ -f|--force ]
	[    --reportformat basic|json ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgs**

Display information about volume groups

```
:~# vgs -h
  vgs - Display information about volume groups

  vgs
	[ -a|--all ]
	[ -o|--options String ]
	[ -S|--select String ]
	[ -O|--sort String ]
	[    --aligned ]
	[    --binary ]
	[    --configreport log|vg|lv|pv|pvseg|seg ]
	[    --foreign ]
	[    --ignorelockingfailure ]
	[    --logonly ]
	[    --nameprefixes ]
	[    --noheadings ]
	[    --nosuffix ]
	[    --readonly ]
	[    --reportformat basic|json ]
	[    --rows ]
	[    --separator String ]
	[    --shared ]
	[    --unbuffered ]
	[    --units [Number]r|R|h|H|b|B|s|S|k|K|m|M|g|G|t|T|p|P|e|E ]
	[    --unquoted ]
	[ COMMON_OPTIONS ]
	[ VG|Tag ... ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgscan**

Search for all volume groups

```
:~# vgscan -h
  vgscan - Search for all volume groups

  vgscan
	[    --ignorelockingfailure ]
	[    --mknodes ]
	[    --notifydbus ]
	[    --reportformat basic|json ]
	[ COMMON_OPTIONS ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

**vgsplit**

Move physical volumes into a new or existing volume group

```
:~# vgsplit -h
  vgsplit - Move physical volumes into a new or existing volume group

  Split a VG by specified PVs.
  vgsplit VG VG PV ...
	[ COMMON_OPTIONS ]

  Split a VG by PVs in a specified LV.
  vgsplit -n|--name LV VG VG
	[ COMMON_OPTIONS ]

  Common options for command:
	[ -A|--autobackup y|n ]
	[ -l|--maxlogicalvolumes Number ]
	[ -M|--metadatatype lvm2 ]
	[ -p|--maxphysicalvolumes Number ]
	[    --alloc contiguous|cling|cling_by_tags|normal|anywhere|inherit ]
	[    --poolmetadataspare y|n ]
	[    --vgmetadatacopies all|unmanaged|Number ]

  Common options for lvm:
	[ -d|--debug ]
	[ -h|--help ]
	[ -q|--quiet ]
	[ -v|--verbose ]
	[ -y|--yes ]
	[ -t|--test ]
	[    --commandprofile String ]
	[    --config String ]
	[    --driverloaded y|n ]
	[    --nolocking ]
	[    --lockopt String ]
	[    --longhelp ]
	[    --profile String ]
	[    --version ]
	[    --devicesfile String ]
	[    --devices PV ]
	[    --nohints ]
	[    --journal String ]

  Use --longhelp to show all options and advanced commands.
```

***

#### lvm2-dbusd <a href="#lvm2-dbusd" id="lvm2-dbusd"></a>

This is LVM2, the rewrite of The Linux Logical Volume Manager. LVM supports enterprise level volume management of disk and disk subsystems by grouping arbitrary disks into volume groups. The total capacity of volume groups can be allocated to logical volumes, which are accessed as regular block devices.

This package includes the D-Bus daemon.

**Installed size:** `233 KB`\
**How to install:** `sudo apt install lvm2-dbusd`

<details>

<summary>Dependencies:</summary>

* dbus
* lvm2
* python3
* python3-dbus
* python3-gi
* python3-pyudev

</details>

**lvmdbusd**

LVM D-Bus daemon

```
:~# lvmdbusd -h
usage: lvmdbusd [-h] [--udev] [--debug] [--nojson] [--lvmshell]
                [--blackboxsize BB_SIZE]

options:
  -h, --help            show this help message and exit
  --udev                Use udev for updating state
  --debug               Dump debug messages
  --nojson              Do not use LVM JSON output (disables lvmshell)
  --lvmshell            Use the lvm shell, not fork & exec lvm
  --blackboxsize BB_SIZE
                        Size of the black box flight recorder, 0 to disable
```

***

#### lvm2-lockd <a href="#lvm2-lockd" id="lvm2-lockd"></a>

This is LVM2, the rewrite of The Linux Logical Volume Manager. LVM supports enterprise level volume management of disk and disk subsystems by grouping arbitrary disks into volume groups. The total capacity of volume groups can be allocated to logical volumes, which are accessed as regular block devices.

LVM commands use lvmlockd to coordinate access to shared storage.

**Installed size:** `563 KB`\
**How to install:** `sudo apt install lvm2-lockd`

<details>

<summary>Dependencies:</summary>

* libc6
* libdlm3
* libsanlock-client1
* libselinux1
* libsystemd0
* libudev1
* lvm2

</details>

**lvmlockctl**

Control for lvmlockd

```
:~# lvmlockctl -h
lvmlockctl options
Options:
--help | -h
      Show this help information.
--quit | -q
      Tell lvmlockd to quit.
--info | -i
      Print lock state information from lvmlockd.
--dump | -d
      Print log buffer from lvmlockd.
--wait | -w 0|1
      Wait option for other commands.
--force | -f 0|1>
      Force option for other commands.
--kill | -k <vgname>
      Kill access to the VG locks are lost (see lvmlockctl_kill_command).
--drop | -r <vgname>
      Clear locks for the VG when it is unused after kill (-k).
--gl-enable | -E <vgname>
      Tell lvmlockd to enable the global lock in a sanlock VG.
--gl-disable | -D <vgname>
      Tell lvmlockd to disable the global lock in a sanlock VG.
--stop-lockspaces | -S
      Stop all lockspaces.
--stderr | -e
      Send kill and drop messages to stderr instead of syslog
```

***

**lvmlockd**

LVM locking daemon

```
:~# lvmlockd -h
Usage:
lvmlockd [options]

  --help | -h
        Show this help information.
  --version | -V
        Show version of lvmlockd.
  --test | -T
        Test mode, do not call lock manager.
  --foreground | -f
        Don't fork.
  --daemon-debug | -D
        Don't fork and print debugging to stdout.
  --pid-file | -p <path>
        Set path to the pid file. [/run/lvmlockd.pid]
  --socket-path | -s <path>
        Set path to the socket to listen on. [/run/lvm/lvmlockd.socket]
  --adopt-file <path>
        Set path to the adopt file. [/run/lvm/lvmlockd.adopt]
  --syslog-priority | -S err|warning|debug
        Write log messages from this level up to syslog. [warning]
  --gl-type | -g <str>
        Set global lock type to be dlm|sanlock.
  --host-id | -i <num>
        Set the local sanlock host id.
  --host-id-file | -F <path>
        A file containing the local sanlock host_id.
  --sanlock-timeout | -o <seconds>
        Set the sanlock lockspace I/O timeout.
  --adopt | -A 0|1
        Adopt locks from a previous instance of lvmlockd.
```

***
