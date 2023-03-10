# Libraries

```
INTRO(3)                NetBSD Library Functions Manual               INTRO(3)




     intro -- introduction to the system libraries




     This section provides an overview of the system libraries, their func-
     tions, error returns and other common definitions and concepts.  Most of
     these functions are available from the standard C library, libc.  Other
     libraries, such as the math library, libm, must be indicated at compile
     time with the -l option of the compiler.

     The various system libraries supplied in NetBSD (followed by the linker
     flags) are:

     libasn1 (-lasn1)
                 The abstract syntax notation (ASN) library provides routines
                 for the specification of abstract data types.

     libbz2 (-lbz2)
                 Block-sorting compressor library providing routines for fast
                 and efficient compression.

     libc (-lc)  The standard C library.  When using the C compiler cc(1), it
                 is not necessary to supply the linker flag -lc for these
                 functions.  There are several subsystems included inside
                 libc:

                 standard I/O routines
                         see stdio(3)

                 database routines
                         see db(3)

                 bit operators
                         see bitstring(3)

                 string operators
                         see string(3)

                 character tests and character operators

                 encryption and hash routines
                         see md4(3) and md5(3).

                 storage allocation
                         see mpool(3) and malloc(3)

                 time functions
                         see time(3)

                 signal handling
                         see signal(3)

     libcom_err (-lcom_err)
                 The common error description library.  See com_err(3).

     libcompat (-lcompat)
                 Functions which are obsolete but are available for compati-
                 bility with 4.3BSD.  In particular, a number of system call
                 interfaces provided in previous releases of BSD have been
                 included for source code compatibility.  Use of these rou-
                 tines should, for the most part, be avoided.  The manual page
                 entry for each compatibility routine indicates the proper
                 interface to use.

     libcrypt (-lcrypt)
                 The crypt library.  See crypt(3).

     libcrypto (-lcrypto)
                 The OpenSSL cryptographic library.  See crypto(7).

     libcurses (-lcurses -lterminfo)
                 Terminal independent screen management routines for two
                 dimensional non-bitmap display terminals.  See curses(3).

     libdes (-ldes)
                 The OpenSSL cryptographic library for the DES algorithms.
                 See des(3).

     libdm (-ldm)
                 The device-mapper driver access library used for communica-
                 tion with kernel driver dm(4) and for lvm(8) subsystem.

     libedit (-ledit)
                 The command-line editor or editline library.  The editline
                 library provides generic editing and history functions.  See
                 editline(3).

     libform (-lform)
                 The curses form library provides a terminal-independent form
                 system using the curses library.  The form library provides
                 facilities for defining forms on terminals.  See forms(3).

     libgssapi (-lgssapi)
                 The Generic Security Services (GSS) API library.  This
                 library provides verification services to applications and
                 usually sits above the cryptographic libraries.

     libhesiod (-lhesiod)
                 The Hesiod library.  This library provides routines for per-
                 forming lookups of Hesiod information, which is stored as
                 text records in the Domain Name Service.  See hesiod(3).

     libhdb (-lhdb)
                 The Heimdal Kerberos 5 authentication/authorisation database
                 access library.

     libintl (-lintl)
                 The internationalized message handling library.  See
                 gettext(3).

     libipsec (-lipsec)
                 The IPsec policy control library.  See ipsec_set_policy(3)
                 and ipsec_strerror(3).

     libkadm5clnt (-lkadm5clnt)
                 The Kerberos 5 administration client library.

     libkadm5srv (-lkadm5srv)
                 The Kerberos 5 administration server library.  See
                 kadm5_pwcheck(3).

     libkafs (-lkafs)
                 The Kerberos IV AFS library.  See kafs(3).

     libkdb (-lkdb)
                 The Kerberos IV authentication/authorisation database access
                 library.

     libkrb (-lkrb)
                 The Kerberos IV library.

     libkrb5 (-lkrb5)
                 The Kerberos 5 library.  See krb5(3).

     libkstream (-lkstream)
                 Kerberos IV encrypted stream library.

     libkvm (-lkvm)
                 Kernel data access library.  See kvm(3).

     libl (-ll)  The library for lex(1).

     libm (-lm)  The math library.  See math(3).

     libmenu (-lmenu)
                 The curses menu library.  See menus(3).

     libnvmm (-lnvmm)
                 NetBSD Virtualization API.  See libnvmm(3).

     libossaudio (-lossaudio)
                 Open Sound System compatibility library.  See ossaudio(3).

     libpanel (-lpanel)
                 The curses panel library.  See panel(3).

     libpcap (-lpcap)
                 The packet capture library.  See pcap(3).

     libpci (-lpci)
                 The PCI bus access library.  See pci(3).

     libposix (-lposix)
                 The POSIX compatibility library provides a compatibility
                 interface for POSIX functions which differ from the standard
                 BSD interfaces.  See chown(2) and rename(2).

     libresolv (-lresolv)
                 The DNS resolver library.

     librmt (-lrmt)
                 Remote magnetic tape library.  See rmtops(3).

     libroken (-lroken)
                 A library containing compatibility functions used by Ker-
                 beros.  It implements functionality required by the Kerberos
                 implementation not implemented in the standard NetBSD
                 libraries.

     librpcsvc (-lrpcsvc)
                 The Remote Procedure Call (RPC) services library.  See
                 rpc(3).

     libskey (-lskey)
                 The S/Key one-time password library.  See skey(3).

     libsl (-lsl)

     libss (-lss)

     libssl (-lssl)
                 The secure sockets layer (SSL) library.  See ssl(7).

     libtelnet (-ltelnet)
                 The telnet library.

     libterminfo (-lterminfo)
                 The terminal-independent operation library.  See terminfo(3).

     libusbhid (-lusbhid)
                 The Universal Serial Bus (USB) Human Interface Devices access
                 library.  See libusbhid(3).

     libutil (-lutil)
                 The system utilities library.  See util(3).

     libwrap (-lwrap)
                 The TCP wrappers library.  See hosts_access(3).

     liby (-ly)  The library for yacc(1).

     libz (-lz)  General-purpose compression library.  See zlib(3).




     cc(1), ld(1), nm(1), rtld(1), intro(2)




     An intro manual appeared in Version 7 AT&T UNIX.

NetBSD 10.99                    April 14, 2021                    NetBSD 10.99
```
