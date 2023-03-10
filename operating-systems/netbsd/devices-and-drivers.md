# Devices and Drivers

```
INTRO(4)                NetBSD Kernel Interfaces Manual               INTRO(4)




     intro -- introduction to devices and device drivers




     This section contains information related to devices, device drivers and
     miscellaneous hardware.

   The device abstraction
     Device is a term used mostly for hardware-related stuff that belongs to
     the system, like disks, printers, or a graphics display with its key-
     board.  There are also so-called pseudo-devices where a device driver
     emulates the behaviour of a device in software without any particular
     underlying hardware.  A typical example for the latter class is /dev/mem,
     a loophole where the physical memory can be accessed using the regular
     file access semantics.

     The device abstraction generally provides a common set of system calls
     layered on top of them, which are dispatched to the corresponding device
     driver by the upper layers of the kernel.  The set of system calls avail-
     able for devices is chosen from open(2), close(2), read(2), write(2),
     ioctl(2), select(2), and mmap(2).  Not all drivers implement all system
     calls, for example, calling mmap(2) on terminal devices is likely to be
     not useful at all.

   Accessing Devices
     Most of the devices in a UNIX-like operating system are accessed through
     so-called device nodes, sometimes also called special files.  They are
     usually located under the directory /dev in the file system hierarchy
     (see also hier(7)).

     Note that this could lead to an inconsistent state, where either there
     are device nodes that do not have a configured driver associated with
     them, or there may be drivers that have successfully probed for their
     devices, but cannot be accessed since the corresponding device node is
     still missing.  In the first case, any attempt to reference the device
     through the device node will result in an error, returned by the upper
     layers of the kernel, usually ENXIO.  In the second case, the device node
     needs to be created before the driver and its device will be usable.

     Some devices come in two flavors: block and character devices, or to use
     better terms, buffered and unbuffered (raw) devices.  The traditional
     names are reflected by the letters `b' and `c' as the file type identifi-
     cation in the output of `ls -l'.  Buffered devices are being accessed
     through the buffer cache of the operating system, and they are solely
     intended to layer a file system on top of them.  They are normally imple-
     mented for disks and disk-like devices only and, for historical reasons,
     for tape devices.

     Raw devices are available for all drivers, including those that also
     implement a buffered device.  For the latter group of devices, the dif-
     ferentiation is conventionally done by prepending the letter `r' to the
     path name of the device node, for example /dev/rsd0[cd] denotes the raw
     device for the first SCSI disk, while /dev/sd0[cd] is the corresponding
     device node for the buffered device.

     Unbuffered devices should be used for all actions that are not related to
     file system operations, even if the device in question is a disk device.
     This includes making backups of entire disk partitions, or to raw floppy
     disks (i.e., those used like tapes).

     Access restrictions to device nodes are usually subject to the regular
     file permissions of the device node entry, instead of being enforced
     directly by the drivers in the kernel.

   Drivers without device nodes
     Drivers for network devices do not use device nodes in order to be
     accessed.  Their selection is based on other decisions inside the kernel,
     and instead of calling open(2), use of a network device is generally
     introduced by using the system call socket(2).

   Configuring a driver into the kernel
     For each kernel, there is a configuration file that is used as a base to
     select the facilities and drivers for that kernel, and to tune several
     options.  See config(1) for a detailed description of the files involved.
     The individual manual pages in this section provide a sample line for the
     configuration file in their synopsis portion.  See also the sample config
     file /usr/src/sys/arch/i386/conf/GENERIC (for the i386 architecture).




     config(1), close(2), ioctl(2), mmap(2), open(2), read(2), select(2),
     socket(2), write(2), hier(7)




     This manual page first appeared in FreeBSD 2.1 and NetBSD 9.




     This man page has been written by J�rg Wunsch with initial input by David
     E. O'Brien.

NetBSD 10.99                   December 18, 2017                  NetBSD 10.99
```
