---
description: >-
  Samba is an open-source software suite that provides file and print services
  for Windows clients. It's easy to use, secure, and highly customizable.
---

# 🌐 samba

Samba is an open-source software suite that provides file and print services for Windows clients using the SMB/CIFS protocol. It allows Unix-based systems to share files and printers with Windows-based systems, and vice versa. Samba is a popular tool for network administrators and IT professionals, and is widely used in enterprise environments.

Samba provides a range of features and capabilities that make it a powerful tool for file and print sharing. It supports file sharing across multiple platforms, including Unix, Linux, macOS, and Windows. It also supports a wide range of protocols, including SMB, CIFS, and FTP, and provides support for both IPv4 and IPv6 networks.

One of the key benefits of Samba is its ease of use. It is designed to be simple and intuitive to configure and manage, with a range of tools and utilities that make it easy to set up and maintain file and print services. Additionally, Samba provides a range of security features, including support for encryption and authentication protocols, that help to ensure the privacy and security of shared data.

Samba is also highly customizable, and can be extended with a range of plugins and scripts to provide additional functionality. For example, there are plugins available for integrating Samba with LDAP directories, for providing print services, and for integrating with other network services.

Despite its many strengths, Samba is not without its limitations. It can be challenging to configure in complex network environments, and may require advanced knowledge of networking and security concepts. Additionally, it may not be suitable for all file and print sharing scenarios, particularly those involving high-performance or high-throughput workloads.

In summary, Samba is a powerful and flexible tool for providing file and print services in a mixed-platform environment. Its ease of use, security features, and extensibility make it an essential tool for network administrators and IT professionals. While it may not be suitable for all file and print sharing scenarios, it is a valuable addition to any enterprise or organizational network.

### Packages and Binaries:

#### ctdb <a href="#ctdb" id="ctdb"></a>

CTDB is a cluster implementation of the TDB database used by Samba and other projects to store temporary data. If an application is already using TDB for temporary data it is very easy to convert that application to be cluster aware and use CTDB instead.

CTDB provides the same types of functions as TDB but in a clustered fashion, providing a TDB-style database that spans multiple physical hosts in a cluster.

Features include:

* CTDB provides a TDB that has consistent data and consistent locking across all nodes in a cluster.
* CTDB is very fast.
* In case of node failures, CTDB will automatically recover and repair all TDB databases that it manages.
* CTDB is the core component that provides pCIFS (“parallel CIFS”) with Samba3/4.
* CTDB provides HA features such as node monitoring, node failover, and IP takeover.
* CTDB provides a reliable messaging transport to allow applications linked with CTDB to communicate to other instances of the application running on different nodes in the cluster.
* CTDB has pluggable transport backends. Currently implemented backends are TCP and Infiniband.
* CTDB supports a system of application specific management scripts, allowing applications that depend on network or filesystem resources to be managed in a highly available manner on a cluster.

**Installed size:** `3.67 MB`\
**How to install:** `sudo apt install ctdb`

<details>

<summary>Dependencies:</summary>

* iproute2
* libbsd0
* libc6
* libpopt0
* libtalloc2
* libtdb1
* libtevent0
* libtirpc3
* psmisc
* samba-libs
* sudo
* tdb-tools
* time

</details>

**ctdb**

CTDB management utility Clustered TDB

```
:~# ctdb --help
Usage: [OPTION...]
  -d, --debug=STRING       debug level
  -t, --timelimit=INT      timelimit (in seconds)
  -n, --node=INT           node specification - integer
  -Y                       enable machine readable output
  -x, --separator=CHAR     specify separator for machine readable output
  -X                       enable machine parsable output with separator |
  -v, --verbose            enable verbose output
  -T, --maxruntime=INT     die if runtime exceeds this limit (in seconds)

Help options:
  -?, --help               Show this help message
      --usage              Display brief usage message
```

***

**ctdb\_diagnostics**

Dump diagnostic information about CTDB/Samba installation

```
:~# ctdb_diagnostics -h
Failed to read nodes file "/etc/ctdb/nodes"
Usage: ctdb_diagnostics [OPTION] ...
  options:
    -n <nodes>  Comma separated list of nodes to operate on
    -c          Ignore comment lines (starting with '#') in file comparisons
    -w          Ignore whitespace in file comparisons
    --no-ads    Do not use commands that assume an Active Directory Server
```

***

**ctdbd**

The CTDB cluster daemon

```
:~# ctdbd --help
Usage: [OPTION...]
  -i, --interactive     don't fork, log to stderr

Help options:
  -?, --help            Show this help message
      --usage           Display brief usage message
```

***

**ltdbtool**

Manipulate CTDB’s local TDB files

```
:~# ltdbtool -h
Usage: ltdbtool [options] <command>

Options:
   -s {0|32|64}    specify how to determine the ctdb record header size
                   for the input database:
                   0: no ctdb header
                   32: ctdb header size of a 32 bit system (20 bytes)
                   64: ctdb header size of a 64 bit system (24 bytes)
                   default: 32 or 64 depending on the system architecture

   -S <num>        the number of bytes to interpret as ctdb record header
                   for the input database (beware!)

   -o {0|32|64}    specify how to determine the ctdb record header size
                   for the output database
                   0: no ctdb header
                   32: ctdb header size of a 32 bit system (20 bytes)
                   64: ctdb header size of a 64 bit system (24 bytes)
                   default: 32 or 64 depending on the system architecture

   -O <num>        the number of bytes to interpret as ctdb record header
                   for the output database (beware!)

   -e              Include empty records, defaults to off

   -p              print header (for the dump command), defaults to off

   -h              print this help

Commands:
  help                         print this help
  dump <db>                    dump the db to stdout
  convert <in_db> <out_db>     convert the db

```

***

**onnode**

Run commands on CTDB cluster nodes

```
:~# onnode --help
/usr/bin/onnode: illegal option -- -
Usage: onnode [OPTION] ... <NODES> <COMMAND> ...
  options:
    -c          Run in current working directory on specified nodes.
    -f          Specify nodes file, overriding default.
    -i          Keep standard input open - the default is to close it.
    -n          Allow nodes to be specified by name.
    -p          Run command in parallel on specified nodes.
    -P          Push given files to nodes instead of running commands.
    -q          Do not print node addresses (overrides -v).
    -v          Print node address even for a single node.
  <NODES>       "all", "any", "ok" (or "healthy"), "con" (or "connected") ; or
                a node number (0 base); or
                a hostname (if -n is specified); or
                list (comma separated) of <NODES>; or
                range (hyphen separated) of node numbers.
```

***

**ping\_pong**

Measures the ping-pong byte range lock latency

```
:~# man ping_pong
PING_PONG(1)             CTDB - clustered TDB database            PING_PONG(1)

NAME
       ping_pong - measures the ping-pong byte range lock latency

SYNOPSIS
       ping_pong {-r | -w | -rw} [-m] [-c] {FILENAME} {NUM-LOCKS}

DESCRIPTION
       ping_pong measures the byte range lock latency. It is especially useful
       on a cluster of nodes sharing a common lock manager as it will give
       some indication of the lock manager's performance under stress.

       FILENAME is a file on shared storage to use for byte range locking
       tests.

       NUM-LOCKS is the number of byte range locks, so needs to be (strictly)
       greater than the number of nodes in the cluster.

OPTIONS
       -r
           test read performance

       -w
           test write performance

       -m
           use mmap

       -c
           validate the locks

EXAMPLES
       Testing lock coherence

                 ping_pong test.dat N

       Testing lock coherence with lock validation

                 ping_pong -c test.dat N

       Testing IO coherence

                 ping_pong -rw test.dat N

SEE ALSO
       ctdb(7), https://wiki.samba.org/index.php/Ping_pong

AUTHOR
       This documentation was written by Mathieu Parent

COPYRIGHT
       Copyright (C) 2002 Andrew Tridgell

       This program is free software; you can redistribute it and/or modify it
       under the terms of the GNU General Public License as published by the
       Free Software Foundation; either version 3 of the License, or (at your
       option) any later version.

       This program is distributed in the hope that it will be useful, but
       WITHOUT ANY WARRANTY; without even the implied warranty of
       MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
       General Public License for more details.

       You should have received a copy of the GNU General Public License along
       with this program; if not, see http://www.gnu.org/licenses.

ctdb                              02/04/2023                      PING_PONG(1)
```

***

#### ldb-tools <a href="#ldb-tools" id="ldb-tools"></a>

ldb is a LDAP-like embedded database built on top of TDB.

What ldb does is provide a fast database with an LDAP-like API designed to be used within an application. In some ways it can be seen as a intermediate solution between key-value pair databases and a real LDAP database.

This package contains bundled test and utility binaries

**Installed size:** `195 KB`\
**How to install:** `sudo apt install ldb-tools`

<details>

<summary>Dependencies:</summary>

* libc6
* libldb2
* libpopt0
* libtalloc2

</details>

**ldbadd**

Command-line utility for adding records to an LDB

```
:~# ldbadd --help
Usage: [OPTION...]
  -H, --url=URL                   database URL
  -b, --basedn=DN                 base DN
  -e, --editor=PROGRAM            external editor
  -s, --scope=SCOPE               search scope
  -v, --verbose                   increase verbosity
      --trace                     enable tracing
  -i, --interactive               input from stdin
  -r, --recursive                 recursive delete
      --modules-path=PATH         modules path
      --num-searches=INT          number of test searches
      --num-records=INT           number of test records
  -a, --all                       (|(objectClass=*)(distinguishedName=*))
      --nosync                    non-synchronous transactions
  -S, --sorted                    sort attributes
  -o OPTION                       ldb_connect option
      --controls=STRING           controls
      --show-binary               display binary LDIF
      --paged                     use a paged search
      --show-deleted              show deleted objects
      --show-recycled             show recycled objects
      --show-deactivated-link     show deactivated links
      --reveal                    reveal ldb internals
      --relax                     pass relax control
      --cross-ncs                 search across NC boundaries
      --extended-dn               show extended DNs

Help options:
  -?, --help                      Show this help message
      --usage                     Display brief usage message
```

***

**ldbdel**

Command-line program for deleting LDB records

```
:~# ldbdel --help
Usage: [OPTION...]
  -H, --url=URL                   database URL
  -b, --basedn=DN                 base DN
  -e, --editor=PROGRAM            external editor
  -s, --scope=SCOPE               search scope
  -v, --verbose                   increase verbosity
      --trace                     enable tracing
  -i, --interactive               input from stdin
  -r, --recursive                 recursive delete
      --modules-path=PATH         modules path
      --num-searches=INT          number of test searches
      --num-records=INT           number of test records
  -a, --all                       (|(objectClass=*)(distinguishedName=*))
      --nosync                    non-synchronous transactions
  -S, --sorted                    sort attributes
  -o OPTION                       ldb_connect option
      --controls=STRING           controls
      --show-binary               display binary LDIF
      --paged                     use a paged search
      --show-deleted              show deleted objects
      --show-recycled             show recycled objects
      --show-deactivated-link     show deactivated links
      --reveal                    reveal ldb internals
      --relax                     pass relax control
      --cross-ncs                 search across NC boundaries
      --extended-dn               show extended DNs

Help options:
  -?, --help                      Show this help message
      --usage                     Display brief usage message
```

***

**ldbedit**

Edit LDB databases using your preferred editor

```
:~# ldbedit --help
Usage: [OPTION...]
  -H, --url=URL                   database URL
  -b, --basedn=DN                 base DN
  -e, --editor=PROGRAM            external editor
  -s, --scope=SCOPE               search scope
  -v, --verbose                   increase verbosity
      --trace                     enable tracing
  -i, --interactive               input from stdin
  -r, --recursive                 recursive delete
      --modules-path=PATH         modules path
      --num-searches=INT          number of test searches
      --num-records=INT           number of test records
  -a, --all                       (|(objectClass=*)(distinguishedName=*))
      --nosync                    non-synchronous transactions
  -S, --sorted                    sort attributes
  -o OPTION                       ldb_connect option
      --controls=STRING           controls
      --show-binary               display binary LDIF
      --paged                     use a paged search
      --show-deleted              show deleted objects
      --show-recycled             show recycled objects
      --show-deactivated-link     show deactivated links
      --reveal                    reveal ldb internals
      --relax                     pass relax control
      --cross-ncs                 search across NC boundaries
      --extended-dn               show extended DNs

Help options:
  -?, --help                      Show this help message
      --usage                     Display brief usage message
```

***

**ldbmodify**

Modify records in a LDB database

```
:~# ldbmodify --help
Usage: [OPTION...]
  -H, --url=URL                   database URL
  -b, --basedn=DN                 base DN
  -e, --editor=PROGRAM            external editor
  -s, --scope=SCOPE               search scope
  -v, --verbose                   increase verbosity
      --trace                     enable tracing
  -i, --interactive               input from stdin
  -r, --recursive                 recursive delete
      --modules-path=PATH         modules path
      --num-searches=INT          number of test searches
      --num-records=INT           number of test records
  -a, --all                       (|(objectClass=*)(distinguishedName=*))
      --nosync                    non-synchronous transactions
  -S, --sorted                    sort attributes
  -o OPTION                       ldb_connect option
      --controls=STRING           controls
      --show-binary               display binary LDIF
      --paged                     use a paged search
      --show-deleted              show deleted objects
      --show-recycled             show recycled objects
      --show-deactivated-link     show deactivated links
      --reveal                    reveal ldb internals
      --relax                     pass relax control
      --cross-ncs                 search across NC boundaries
      --extended-dn               show extended DNs

Help options:
  -?, --help                      Show this help message
      --usage                     Display brief usage message
```

***

**ldbrename**

Edit LDB databases using your favorite editor

```
:~# ldbrename --help
Usage: [OPTION...]
  -H, --url=URL                   database URL
  -b, --basedn=DN                 base DN
  -e, --editor=PROGRAM            external editor
  -s, --scope=SCOPE               search scope
  -v, --verbose                   increase verbosity
      --trace                     enable tracing
  -i, --interactive               input from stdin
  -r, --recursive                 recursive delete
      --modules-path=PATH         modules path
      --num-searches=INT          number of test searches
      --num-records=INT           number of test records
  -a, --all                       (|(objectClass=*)(distinguishedName=*))
      --nosync                    non-synchronous transactions
  -S, --sorted                    sort attributes
  -o OPTION                       ldb_connect option
      --controls=STRING           controls
      --show-binary               display binary LDIF
      --paged                     use a paged search
      --show-deleted              show deleted objects
      --show-recycled             show recycled objects
      --show-deactivated-link     show deactivated links
      --reveal                    reveal ldb internals
      --relax                     pass relax control
      --cross-ncs                 search across NC boundaries
      --extended-dn               show extended DNs

Help options:
  -?, --help                      Show this help message
      --usage                     Display brief usage message
```

***

**ldbsearch**

Search for records in a LDB database

```
:~# ldbsearch --help
Usage: [OPTION...]
  -H, --url=URL                   database URL
  -b, --basedn=DN                 base DN
  -e, --editor=PROGRAM            external editor
  -s, --scope=SCOPE               search scope
  -v, --verbose                   increase verbosity
      --trace                     enable tracing
  -i, --interactive               input from stdin
  -r, --recursive                 recursive delete
      --modules-path=PATH         modules path
      --num-searches=INT          number of test searches
      --num-records=INT           number of test records
  -a, --all                       (|(objectClass=*)(distinguishedName=*))
      --nosync                    non-synchronous transactions
  -S, --sorted                    sort attributes
  -o OPTION                       ldb_connect option
      --controls=STRING           controls
      --show-binary               display binary LDIF
      --paged                     use a paged search
      --show-deleted              show deleted objects
      --show-recycled             show recycled objects
      --show-deactivated-link     show deactivated links
      --reveal                    reveal ldb internals
      --relax                     pass relax control
      --cross-ncs                 search across NC boundaries
      --extended-dn               show extended DNs

Help options:
  -?, --help                      Show this help message
      --usage                     Display brief usage message
```

***

#### libldb-dev <a href="#libldb-dev" id="libldb-dev"></a>

ldb is a LDAP-like embedded database built on top of TDB.

What ldb does is provide a fast database with an LDAP-like API designed to be used within an application. In some ways it can be seen as a intermediate solution between key-value pair databases and a real LDAP database.

This package contains the development files.

**Installed size:** `171 KB`\
**How to install:** `sudo apt install libldb-dev`

<details>

<summary>Dependencies:</summary>

* libc6-dev
* libldb2
* libtalloc-dev
* libtdb-dev
* libtevent-dev
* pkg-config

</details>

***

#### libldb2 <a href="#libldb2" id="libldb2"></a>

ldb is a LDAP-like embedded database built on top of TDB.

It provides a fast database with an LDAP-like API designed to be used within an application. In some ways it can be seen as a intermediate solution between key-value pair databases and a real LDAP database.

This package contains the shared library file.

**Installed size:** `614 KB`\
**How to install:** `sudo apt install libldb2`

<details>

<summary>Dependencies:</summary>

* libc6
* libldap-2.5-0
* liblmdb0
* libtalloc2
* libtdb1
* libtevent0

</details>

***

#### libnss-winbind <a href="#libnss-winbind" id="libnss-winbind"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file and printer sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as an NT4-style domain controller, and can integrate with both NT4 domains and Active Directory realms as a member server.

This package provides nss\_winbind, a plugin that integrates with a local winbindd server to provide user/group name lookups to the system; and nss\_wins, which provides hostname lookups via both the NBNS and NetBIOS broadcast protocols.

**Installed size:** `185 KB`\
**How to install:** `sudo apt install libnss-winbind`

<details>

<summary>Dependencies:</summary>

* libbsd0
* libc6
* winbind

</details>

***

#### libpam-winbind <a href="#libpam-winbind" id="libpam-winbind"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file and printer sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as an NT4-style domain controller, and can integrate with both NT4 domains and Active Directory realms as a member server.

This package provides pam\_winbind, a plugin that integrates with a local winbindd server to provide Windows domain authentication to the system.

**Installed size:** `168 KB`\
**How to install:** `sudo apt install libpam-winbind`

<details>

<summary>Dependencies:</summary>

* libbsd0
* libc6
* libpam-runtime
* libpam0g
* libtalloc2
* winbind

</details>

***

#### libsmbclient <a href="#libsmbclient" id="libsmbclient"></a>

This package provides a shared library that enables client applications to talk to Microsoft Windows and Samba servers using the SMB/CIFS protocol.

**Installed size:** `232 KB`\
**How to install:** `sudo apt install libsmbclient`

<details>

<summary>Dependencies:</summary>

* libbsd0
* libc6
* libtalloc2
* libtevent0
* samba-libs

</details>

***

#### libsmbclient-dev <a href="#libsmbclient-dev" id="libsmbclient-dev"></a>

This package provides the development files (static library and headers) required for building applications against libsmbclient, a library that enables client applications to talk to Microsoft Windows and Samba servers using the SMB/CIFS protocol.

**Installed size:** `268 KB`\
**How to install:** `sudo apt install libsmbclient-dev`

<details>

<summary>Dependencies:</summary>

* libsmbclient

</details>

***

#### libwbclient-dev <a href="#libwbclient-dev" id="libwbclient-dev"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file and printer sharing with Microsoft Windows, OS X, and other Unix systems.

This package provides the development files (static library and headers) required for building applications against libwbclient, a library for client applications that interact via the winbind pipe protocol with a Samba winbind server.

**Installed size:** `110 KB`\
**How to install:** `sudo apt install libwbclient-dev`

<details>

<summary>Dependencies:</summary>

* libwbclient0

</details>

***

#### libwbclient0 <a href="#libwbclient0" id="libwbclient0"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file and printer sharing with Microsoft Windows, OS X, and other Unix systems.

This package provides a library for client applications that interact via the winbind pipe protocol with a Samba winbind server.

**Installed size:** `128 KB`\
**How to install:** `sudo apt install libwbclient0`

<details>

<summary>Dependencies:</summary>

* libbsd0
* libc6

</details>

***

#### python3-ldb <a href="#python3-ldb" id="python3-ldb"></a>

ldb is a LDAP-like embedded database built on top of TDB.

This package contains the Python 3 bindings.

**Installed size:** `182 KB`\
**How to install:** `sudo apt install python3-ldb`

<details>

<summary>Dependencies:</summary>

* libc6
* libldb2
* libpython3.11
* libtalloc2
* python3
* python3

</details>

***

#### python3-ldb-dev <a href="#python3-ldb-dev" id="python3-ldb-dev"></a>

ldb is a LDAP-like embedded database built on top of TDB.

It is a fast database with an LDAP-like API designed to be used within an application. In some ways it can be seen as a intermediate solution between key-value pair databases and a real LDAP database.

This package contains the development files for the Python 3 bindings.

**Installed size:** `60 KB`\
**How to install:** `sudo apt install python3-ldb-dev`

<details>

<summary>Dependencies:</summary>

* libc6-dev
* libldb-dev
* pkg-config
* python3-ldb

</details>

***

#### python3-samba <a href="#python3-samba" id="python3-samba"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as a domain controller or member server in both NT4-style and Active Directory domains.

This package contains Python 3 bindings for most Samba libraries.

**Installed size:** `21.40 MB`\
**How to install:** `sudo apt install python3-samba`

<details>

<summary>Dependencies:</summary>

* libbsd0
* libc6
* libgnutls30
* libldb2
* libpython3.11
* libtalloc2
* libtevent0
* python3
* python3
* python3-ldb
* python3-talloc
* python3-tdb
* samba-libs

</details>

***

#### registry-tools <a href="#registry-tools" id="registry-tools"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as a domain controller or member server in both NT4-style and Active Directory domains.

This package contains tools for viewing and manipulating the binary “registry” found on Windows machines, both locally and remote.

**Installed size:** `153 KB`\
**How to install:** `sudo apt install registry-tools`

<details>

<summary>Dependencies:</summary>

* libc6
* libpopt0
* libreadline8
* libtalloc2
* samba-libs

</details>

**regdiff**

Diff program for Windows registry files

```
:~# regdiff --help
Usage: regdiff [OPTION...]
  -o, --output=STRING                          output file to use
  -n, --null                                   Diff from NULL
  -R, --remote=STRING                          Connect to remote server
  -L, --local                                  Open local registry

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Version options:
  -V, --version                                Print version
```

***

**regpatch**

Applies registry patches to registry files

```
:~# regpatch --help
Usage: regpatch [OPTION...]
  -R, --remote=STRING                          connect to specified remote
                                               server
  -F, --file=STRING                            file path

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Version options:
  -V, --version                                Print version
```

***

**regshell**

Windows registry file browser using readline

```
:~# regshell --help
Usage: regshell [OPTION...]
  -F, --file=STRING                            open hive file
  -R, --remote=STRING                          connect to specified remote
                                               server

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Deprecated legacy options:
  -k, --kerberos=STRING                        DEPRECATED: Migrate to
                                               --use-kerberos

Version options:
  -V, --version                                Print version
```

***

**regtree**

Text-mode registry viewer

```
:~# regtree --help
Usage: regtree [OPTION...]
  -F, --file=STRING                            file path
  -R, --remote=STRING                          connect to specified remote
                                               server
  -f, --fullpath                               show full paths
  -V, --no-values                              don't show values

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Version options:
  -V, --version                                Print version
```

***

#### samba <a href="#samba" id="samba"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file and printer sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as an NT4-style domain controller, and can integrate with both NT4 domains and Active Directory realms as a member server.

This package provides the components necessary to use Samba as a stand-alone file and print server or as an NT4 or Active Directory domain controller. For use in an NT4 domain or Active Directory realm, you will also need the winbind package.

This package is not required for connecting to existing SMB/CIFS servers (see smbclient) or for mounting remote filesystems (see cifs-utils).

**Installed size:** `3.84 MB`\
**How to install:** `sudo apt install samba`

<details>

<summary>Dependencies:</summary>

* init-system-helpers
* libbsd0
* libc6
* libcups2
* libgnutls30
* libldap-2.5-0
* libldb2
* libpam-modules
* libpam-runtime
* libpopt0
* libtalloc2
* libtasn1-6
* libtdb1
* libtevent0
* passwd
* procps
* python3
* python3-dnspython
* python3-samba
* samba-common
* samba-common-bin
* samba-libs
* tdb-tools

</details>

**dumpmscat**

***

**eventlogadm**

Push records into the Samba event log store

```
:~# eventlogadm -h

Usage: eventlogadm [OPTION]

 -o write <Eventlog Name> 					Writes records to eventlog from STDIN
 -o addsource <EventlogName> <sourcename> <msgfileDLLname> 	Adds the specified source & DLL eventlog registry entry
 -o dump <Eventlog Name> <starting_record>					Dump stored eventlog entries on STDOUT

Miscellaneous options:
 -s <filename>							Use configuration file <filename>.
 -d								turn debug on
 -h								display help

Active eventlog names:
--------------------------------------
	<None specified>
```

***

**mvxattr**

Recursively rename extended attributes

```
:~# mvxattr --help
Usage: mvxattr -s STRING -d STRING PATH [PATH ...]
  -s, --from=STRING         xattr source name
  -d, --to=STRING           xattr destination name
  -l, --follow-symlinks     follow symlinks, the default is to ignore them
  -p, --print               print files where the xattr got renamed
  -v, --verbose             print files as they are checked
  -f, --force               force overwriting of destination xattr

Help options:
  -?, --help                Show this help message
      --usage               Display brief usage message
```

***

**nmbd**

NetBIOS name server to provide NetBIOS over IP naming services to clients

```
:~# nmbd --help
Usage: nmbd [OPTION...]
  -H, --hosts=STRING                 Load a netbios hosts file
  -p, --port=INT                     Listen on the specified port

Help options:
  -?, --help                         Show this help message
      --usage                        Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL        Set debug level
      --debug-stdout                 Send debug output to standard output
  -s, --configfile=CONFIGFILE        Use alternative configuration file
      --option=name=value            Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE     Basename for log/debug files
      --leak-report                  enable talloc leak reporting on exit
      --leak-report-full             enable full talloc leak reporting on exit

Daemon options:
  -D, --daemon                       Become a daemon (default)
  -i, --interactive                  Run interactive (not a daemon) and log to
                                     stdout
  -F, --foreground                   Run daemon in foreground (for
                                     daemontools, etc.)
      --no-process-group             Don't create a new process group

Version options:
  -V, --version                      Print version
```

***

**oLschema2ldif**

Converts LDAP schema’s to LDB-compatible LDIF

```
:~# oLschema2ldif --help
Usage: [OPTION...]
  -b, --basedn=DN             base DN
  -I, --input=inputfile       inputfile of OpenLDAP style schema otherwise
                              STDIN
  -O, --output=outputfile     outputfile otherwise STDOUT

Help options:
  -?, --help                  Show this help message
      --usage                 Display brief usage message

Version options:
  -V, --version               Print version
```

***

**pdbedit**

Manage the SAM database (Database of Samba Users)

```
:~# pdbedit --help
Usage: [OPTION...]
  -L, --list                            list all users
  -v, --verbose                         be verbose
  -w, --smbpasswd-style                 give output in smbpasswd style
  -u, --user=USER                       use username
  -N, --account-desc=STRING             set account description
  -f, --fullname=STRING                 set full name
  -h, --homedir=STRING                  set home directory
  -D, --drive=STRING                    set home drive
  -S, --script=STRING                   set logon script
  -p, --profile=STRING                  set profile path
  -I, --domain=STRING                   set a users' domain
  -U, --user SID=STRING                 set user SID or RID
  -M, --machine SID=STRING              set machine SID or RID
  -a, --create                          create user
  -r, --modify                          modify user
  -m, --machine                         account is a machine account
  -x, --delete                          delete user
  -b, --backend=STRING                  use different passdb backend as
                                        default backend
  -i, --import=STRING                   import user accounts from this backend
  -e, --export=STRING                   export user accounts to this backend
  -g, --group                           use -i and -e for groups
  -y, --policies                        use -i and -e to move account policies
                                        between backends
      --policies-reset                  restore default policies
  -P, --account-policy=STRING           value of an account policy (like
                                        maximum password age)
  -C, --value=LONG                      set the account policy to this value
  -c, --account-control=STRING          Values of account control
      --force-initialized-passwords     Force initialization of corrupt
                                        password strings in a passdb backend
  -z, --bad-password-count-reset        reset bad password count
  -Z, --logon-hours-reset               reset logon hours
      --time-format=STRING              The time format for time parameters
  -t, --password-from-stdin             get password from standard in
  -K, --kickoff-time=STRING             set the kickoff time
      --set-nt-hash=STRING              set password from nt-hash

Help options:
  -?, --help                            Show this help message
      --usage                           Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL           Set debug level
      --debug-stdout                    Send debug output to standard output
  -s, --configfile=CONFIGFILE           Use alternative configuration file
      --option=name=value               Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE        Basename for log/debug files
      --leak-report                     enable talloc leak reporting on exit
      --leak-report-full                enable full talloc leak reporting on
                                        exit

Version options:
  -V, --version                         Print version
```

***

**profiles**

A utility to report and change SIDs in registry files

```
:~# profiles --help
Usage: <profilefile>
  -c, --change-sid=STRING            Provides SID to change
  -n, --new-sid=STRING               Provides SID to change to
  -v, --verbose                      Verbose output

Help options:
  -?, --help                         Show this help message
      --usage                        Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL        Set debug level
      --debug-stdout                 Send debug output to standard output
  -s, --configfile=CONFIGFILE        Use alternative configuration file
      --option=name=value            Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE     Basename for log/debug files
      --leak-report                  enable talloc leak reporting on exit
      --leak-report-full             enable full talloc leak reporting on exit

Version options:
  -V, --version                      Print version
```

***

**samba**

A Windows AD and SMB/CIFS fileserver for UNIX Server to provide AD and SMB/CIFS services to clients

```
:~# samba --help
Usage: samba: root process [OPTION...]
  -M, --model=MODEL                  Select process model
      --maximum-runtime=seconds      set maximum runtime of the server
                                     process, till autotermination
  -b, --show-build                   show build info

Help options:
  -?, --help                         Show this help message
      --usage                        Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL        Set debug level
      --debug-stdout                 Send debug output to standard output
  -s, --configfile=CONFIGFILE        Use alternative configuration file
      --option=name=value            Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE     Basename for log/debug files
      --leak-report                  enable talloc leak reporting on exit
      --leak-report-full             enable full talloc leak reporting on exit

Daemon options:
  -D, --daemon                       Become a daemon (default)
  -i, --interactive                  Run interactive (not a daemon) and log to
                                     stdout
  -F, --foreground                   Run daemon in foreground (for
                                     daemontools, etc.)
      --no-process-group             Don't create a new process group

Version options:
  -V, --version                      Print version
```

***

**samba-gpupdate**

Apply group policy

```
:~# samba-gpupdate -h
Usage: samba-gpupdate [options]

Options:
  -h, --help            show this help message and exit
  -X, --unapply         Unapply Group Policy
  --target=TARGET       {Computer | User}
  --force               Reapplies all policy settings
  --rsop                Print the Resultant Set of Policy

  Samba Common Options:
    -s FILE, --configfile=FILE
                        Configuration file
    -d DEBUGLEVEL, --debuglevel=DEBUGLEVEL
                        debug level
    --option=OPTION     set smb.conf option from command line
    --realm=REALM       set the realm name

  Version Options:
    -V, --version       Display version number

  Credentials Options:
    --simple-bind-dn=DN
                        DN to use for a simple bind
    --password=PASSWORD
                        Password
    -U USERNAME, --username=USERNAME
                        Username
    -W WORKGROUP, --workgroup=WORKGROUP
                        Workgroup
    -N, --no-pass       Don't ask for a password
    --ipaddress=IPADDRESS
                        IP address of server
    -P, --machine-pass  Use stored machine account password
    --use-kerberos=desired|required|off
                        Use Kerberos authentication
    --use-krb5-ccache=KRB5CCNAME
                        Kerberos Credentials cache
    -k KERBEROS, --kerberos=KERBEROS
                        DEPRECATED: Migrate to --use-kerberos
```

***

**samba\_dnsupdate**

```
:~# samba_dnsupdate -h
Usage: samba_dnsupdate [options]

Options:
  -h, --help            show this help message and exit
  --verbose             
  --use-samba-tool      Use samba-tool to make updates over RPC, rather than
                        over DNS
  --use-nsupdate        Use nsupdate command to make updates over DNS
                        (default, if kinit successful)
  --all-names           
  --all-interfaces      
  --current-ip=CURRENT_IP
                        IP address to update DNS to match (helpful if behind
                        NAT, valid multiple times, defaults to values from
                        interfaces=)
  --rpc-server-ip=RPC_SERVER_IP
                        IP address of server to use with samba-tool (defaults
                        to first --current-ip)
  --use-file=USE_FILE   Use a file, rather than real DNS calls
  --update-list=UPDATE_LIST
                        Add DNS names from the given file
  --update-cache=UPDATE_CACHE
                        Cache database of already registered records
  --fail-immediately    Exit on first failure
  --no-credentials      don't try and get credentials
  --no-substitutions    don't try and expands variables in file specified by
                        --update-list

  Samba Common Options:
    -s FILE, --configfile=FILE
                        Configuration file
    -d DEBUGLEVEL, --debuglevel=DEBUGLEVEL
                        debug level
    --option=OPTION     set smb.conf option from command line
    --realm=REALM       set the realm name

  Version Options:
    -V, --version       Display version number
```

***

**samba\_downgrade\_db**

Samba tool for downgrading AD databases

```
:~# samba_downgrade_db -h
Usage: samba_downgrade_db

Options:
  -h, --help         show this help message and exit
  -H URL, --URL=URL  LDB URL for database

  Version Options:
    -V, --version    Display version number
```

***

**samba\_spnupdate**

```
:~# samba_spnupdate -h
Usage: samba_spnupdate

Options:
  -h, --help            show this help message and exit
  --verbose             

  Samba Common Options:
    -s FILE, --configfile=FILE
                        Configuration file
    -d DEBUGLEVEL, --debuglevel=DEBUGLEVEL
                        debug level
    --option=OPTION     set smb.conf option from command line
    --realm=REALM       set the realm name

  Version Options:
    -V, --version       Display version number

  Credentials Options:
    --simple-bind-dn=DN
                        DN to use for a simple bind
    --password=PASSWORD
                        Password
    -U USERNAME, --username=USERNAME
                        Username
    -W WORKGROUP, --workgroup=WORKGROUP
                        Workgroup
    -N, --no-pass       Don't ask for a password
    --ipaddress=IPADDRESS
                        IP address of server
    -P, --machine-pass  Use stored machine account password
    --use-kerberos=desired|required|off
                        Use Kerberos authentication
    --use-krb5-ccache=KRB5CCNAME
                        Kerberos Credentials cache
    -k KERBEROS, --kerberos=KERBEROS
                        DEPRECATED: Migrate to --use-kerberos
```

***

**samba\_upgradedns**

```
:~# samba_upgradedns -h
Usage: samba_upgradedns [options]

Options:
  -h, --help            show this help message and exit
  --dns-backend=<BIND9_DLZ|SAMBA_INTERNAL>
                        The DNS server backend, default SAMBA_INTERNAL
  --migrate=<yes|no>    Migrate existing zone data, default yes
  --verbose             Be verbose

  Version Options:
    -V, --version       Display version number

  Samba Common Options:
    -s FILE, --configfile=FILE
                        Configuration file
    -d DEBUGLEVEL, --debuglevel=DEBUGLEVEL
                        debug level
    --option=OPTION     set smb.conf option from command line
    --realm=REALM       set the realm name

  Credentials Options:
    --simple-bind-dn=DN
                        DN to use for a simple bind
    --password=PASSWORD
                        Password
    -U USERNAME, --username=USERNAME
                        Username
    -W WORKGROUP, --workgroup=WORKGROUP
                        Workgroup
    -N, --no-pass       Don't ask for a password
    --ipaddress=IPADDRESS
                        IP address of server
    -P, --machine-pass  Use stored machine account password
    --use-kerberos=desired|required|off
                        Use Kerberos authentication
    --use-krb5-ccache=KRB5CCNAME
                        Kerberos Credentials cache
    -k KERBEROS, --kerberos=KERBEROS
                        DEPRECATED: Migrate to --use-kerberos
```

***

**sharesec**

Set or get share ACLs

```
:~# sharesec --help
Usage: sharesec sharename

  -r, --remove=ACL                   Remove ACEs
  -m, --modify=ACL                   Modify existing ACEs
  -a, --add=ACL                      Add ACEs
  -R, --replace=ACLS                 Overwrite share permission ACL
  -D, --delete                       Delete the entire security descriptor
  -S, --setsddl=STRING               Set the SD in sddl format
      --viewsddl                     View the SD in sddl format
  -v, --view                         View current share permissions
      --view-all                     View all current share permissions
  -M, --machine-sid                  Initialize the machine SID
  -F, --force                        Force storing the ACL

Help options:
  -?, --help                         Show this help message
      --usage                        Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL        Set debug level
      --debug-stdout                 Send debug output to standard output
  -s, --configfile=CONFIGFILE        Use alternative configuration file
      --option=name=value            Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE     Basename for log/debug files
      --leak-report                  enable talloc leak reporting on exit
      --leak-report-full             enable full talloc leak reporting on exit

Version options:
  -V, --version                      Print version
```

***

**smbcontrol**

Send messages to smbd, nmbd or winbindd processes

```
:~# smbcontrol -h
Invalid option
Usage: smbcontrol [OPTION...] <destination> <message-type> <parameters>
  -t, --timeout=TIMEOUT              Set timeout value in seconds

Help options:
  -?, --help                         Show this help message
      --usage                        Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL        Set debug level
      --debug-stdout                 Send debug output to standard output
  -s, --configfile=CONFIGFILE        Use alternative configuration file
      --option=name=value            Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE     Basename for log/debug files
      --leak-report                  enable talloc leak reporting on exit
      --leak-report-full             enable full talloc leak reporting on exit

Version options:
  -V, --version                      Print version
Usage: smbcontrol [OPTION...] <destination> <message-type> <parameters>
  -t, --timeout=TIMEOUT              Set timeout value in seconds

Help options:
  -?, --help                         Show this help message
      --usage                        Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL        Set debug level
      --debug-stdout                 Send debug output to standard output
  -s, --configfile=CONFIGFILE        Use alternative configuration file
      --option=name=value            Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE     Basename for log/debug files
      --leak-report                  enable talloc leak reporting on exit
      --leak-report-full             enable full talloc leak reporting on exit

Version options:
  -V, --version                      Print version

<destination> is one of "nmbd", "smbd", "winbindd" or a process ID

<message-type> is one of:
	debug                         Set debuglevel
	idmap                         Manipulate idmap cache
	force-election                Force a browse election
	ping                          Elicit a response
	profile                       
	inject                        Inject a fatal signal into a running smbd
	stacktrace                    Display a stack trace of a daemon
	profilelevel                  
	debuglevel                    Display current debuglevels
	printnotify                   Send a print notify message
	close-share                   Forcibly disconnect a share
	close-denied-share            Forcibly disconnect users from shares disallowed now
	kill-client-ip                Forcibly disconnect a client with a specific IP address
	ip-dropped                    Tell winbind that an IP got dropped
	pool-usage                    Display talloc memory usage
	rpc-dump-status               Display rpc status
	ringbuf-log                   Display ringbuf log
	dmalloc-mark                  
	dmalloc-log-changed           
	shutdown                      Shut down daemon
	drvupgrade                    Notify a printer driver has changed
	reload-config                 Force smbd or winbindd to reload config file
	reload-printers               Force smbd to reload printers
	nodestatus                    Ask nmbd to do a node status request
	online                        Ask winbind to go into online state
	offline                       Ask winbind to go into offline state
	onlinestatus                  Request winbind online status
	validate-cache                Validate winbind's credential cache
	dump-domain-list              Dump winbind domain list
	disconnect-dc                 
	notify-cleanup                
	num-children                  Print number of smbd child processes
	msg-cleanup                   
	noop                          Do nothing
	sleep                         Cause the target process to sleep

```

***

**smbd**

Server to provide SMB/CIFS services to clients

```
:~# smbd --help
Usage: smbd [OPTION...]
  -b, --build-options                     Print build options
  -p, --port=STRING                       Listen on the specified ports
  -P, --profiling-level=PROFILE_LEVEL     Set profiling level

Help options:
  -?, --help                              Show this help message
      --usage                             Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL             Set debug level
      --debug-stdout                      Send debug output to standard output
  -s, --configfile=CONFIGFILE             Use alternative configuration file
      --option=name=value                 Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE          Basename for log/debug files
      --leak-report                       enable talloc leak reporting on exit
      --leak-report-full                  enable full talloc leak reporting on
                                          exit

Daemon options:
  -D, --daemon                            Become a daemon (default)
  -i, --interactive                       Run interactive (not a daemon) and
                                          log to stdout
  -F, --foreground                        Run daemon in foreground (for
                                          daemontools, etc.)
      --no-process-group                  Don't create a new process group

Version options:
  -V, --version                           Print version
```

***

**smbstatus**

Report on current Samba connections

```
:~# smbstatus --help
Usage: [OPTION...]
  -p, --processes                    Show processes only
  -v, --verbose                      Be verbose
  -L, --locks                        Show locks only
  -S, --shares                       Show shares only
  -N, --notify                       Show notifies
  -u, --user=STRING                  Switch to user
  -b, --brief                        Be brief
  -P, --profile                      Do profiling
  -R, --profile-rates                Show call rates
  -B, --byterange                    Include byte range locks
  -n, --numeric                      Numeric uid/gid
  -j, --json                         JSON output
  -f, --fast                         Skip checks if processes still exist
      --resolve-uids                 Try to resolve UIDs to usernames

Help options:
  -?, --help                         Show this help message
      --usage                        Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL        Set debug level
      --debug-stdout                 Send debug output to standard output
  -s, --configfile=CONFIGFILE        Use alternative configuration file
      --option=name=value            Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE     Basename for log/debug files
      --leak-report                  enable talloc leak reporting on exit
      --leak-report-full             enable full talloc leak reporting on exit

Version options:
  -V, --version                      Print version
```

***

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file and printer sharing with Microsoft Windows, OS X, and other Unix systems.

This package contains control files to run an Active Directory Domain Controller (AD DC). For now, this is just a metapackage pulling in all the required dependencies.

**Installed size:** `46 KB`\
**How to install:** `sudo apt install samba-ad-dc`

<details>

<summary>Dependencies:</summary>

* samba
* samba-dsdb-modules
* samba-vfs-modules
* winbind

</details>

***

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file and printer sharing with Microsoft Windows, OS X, and other Unix systems.

This package contains files to setup an Active Directory Domain Controller (AD DC).

**Installed size:** `13.39 MB`\
**How to install:** `sudo apt install samba-ad-provision`

***

#### samba-common <a href="#samba-common" id="samba-common"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file and printer sharing with Microsoft Windows, OS X, and other Unix systems.

This package contains common files used by all parts of Samba.

**Installed size:** `209 KB`\
**How to install:** `sudo apt install samba-common`

<details>

<summary>Dependencies:</summary>

* debconf | debconf-2.0
* ucf

</details>

***

#### samba-common-bin <a href="#samba-common-bin" id="samba-common-bin"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as a domain controller or member server in both NT4-style and Active Directory domains.

This package contains the common files that are used by both the server (provided in the samba package) and the client (provided in the samba-clients package).

**Installed size:** `4.34 MB`\
**How to install:** `sudo apt install samba-common-bin`

<details>

<summary>Dependencies:</summary>

* libbsd0
* libc6
* libcups2
* libgnutls30
* libjansson4
* libldap-2.5-0
* libncurses6
* libpopt0
* libreadline8
* libtalloc2
* libtdb1
* libtevent0
* libtinfo6
* libwbclient0
* python3
* python3-samba
* samba-common
* samba-libs

</details>

**dbwrap\_tool**

Low level TDB/CTDB manipulation tool using the dbwrap interface

```
:~# dbwrap_tool --help
Usage: [OPTION...]
      --non-persistent               treat the database as non-persistent
                                     (CAVEAT: This mode might wipe your
                                     database!)
      --persistent                   treat the database as persistent

Help options:
  -?, --help                         Show this help message
      --usage                        Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL        Set debug level
      --debug-stdout                 Send debug output to standard output
  -s, --configfile=CONFIGFILE        Use alternative configuration file
      --option=name=value            Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE     Basename for log/debug files
      --leak-report                  enable talloc leak reporting on exit
      --leak-report-full             enable full talloc leak reporting on exit

Version options:
  -V, --version                      Print version
```

***

**net**

Tool for administration of Samba and remote CIFS servers.

```
:~# net -h
Usage:
  Use 'net help rpc' to get more extensive information about 'net rpc' commands.
  Use 'net help rap' to get more extensive information about 'net rap' commands.
  Use 'net help ads' to get more extensive information about 'net ads' commands.
  Use 'net help file' to get more information about 'net file' commands.
  Use 'net help share' to get more information about 'net share' commands.
  Use 'net help session' to get more information about 'net session' commands.
  Use 'net help server' to get more information about 'net server' commands.
  Use 'net help domain' to get more information about 'net domain' commands.
  Use 'net help printq' to get more information about 'net printq' commands.
  Use 'net help user' to get more information about 'net user' commands.
  Use 'net help group' to get more information about 'net group' commands.
  Use 'net help groupmap' to get more information about 'net groupmap' commands.
  Use 'net help sam' to get more information about 'net sam' commands.
  Use 'net help validate' to get more information about 'net validate' commands.
  Use 'net help groupmember' to get more information about 'net groupmember' commands.
  Use 'net help admin' to get more information about 'net admin' commands.
  Use 'net help service' to get more information about 'net service' commands.
  Use 'net help password' to get more information about 'net password' commands.
  Use 'net help primarytrust' to get more extensive information about 'net primarytrust' commands.
  Use 'net help changetrustpw' to get more information about 'net changetrustpw'.
  net [options] changesecretpw
    Change the ADS domain member machine account password in secrets.tdb.
    Do NOT use this function unless you know what it does.
    Requires the -f flag to work.
  net -U user[%%password] [-W domain] setauthuser
    Set the auth user, password (and optionally domain
    Will prompt for password if not given.
  net setauthuser delete
    Delete the existing auth user settings.
  net getauthuser
    Get the current winbind auth user settings.
  Use 'net help time' to get more information about 'net time' commands.
  Use 'net help lookup' to get more information about 'net lookup' commands.
  Use 'net help g_lock' to get more information about 'net g_lock' commands.
  Use 'net help join' to get more information about 'net join'.
  Use 'net help offlinejoin' to get more information about 'net offlinejoin'.
  Use 'net help dom' to get more information about 'net dom' commands.
  Use 'net help cache' to get more information about 'net cache' commands.
  net getlocalsid
  net setlocalsid S-1-5-21-x-y-z
  net setdomainsid S-1-5-21-x-y-z
  net getdomainsid
  net maxrid
  Use 'net help idmap to get more information about 'net idmap' commands.
  Use 'net help status' to get more information about 'net status' commands.
  Use 'net help usershare to get more information about 'net usershare' commands.
  Use 'net help usersidlist' to get more information about 'net usersidlist'.
  Use 'net help conf' to get more information about 'net conf' commands.
  Use 'net help registry' to get more information about 'net registry' commands.
  Use 'net help eventlog' to get more information about 'net eventlog' commands.
  Use 'net help printing' to get more information about 'net printing' commands.
  Use 'net help serverid' to get more information about 'net serverid' commands.
  Use 'net help notify' to get more information about 'net notify' commands.
  Use 'net help tdb' to get more information about 'net tdb' commands.
  Use 'net help vfs' to get more information about 'net vfs' commands.
  Use 'net help help' to list usage information for 'net' commands.
```

***

**nmblookup**

NetBIOS over TCP/IP client used to lookup NetBIOS names

```
:~# nmblookup --help
Usage: <NODE> ...
  -B, --broadcast=BROADCAST-ADDRESS         Specify address to use for
                                            broadcasts
  -f, --flags                               List the NMB flags returned
  -U, --unicast=STRING                      Specify address to use for unicast
  -M, --master-browser                      Search for a master browser
      --recursion                           Set recursion desired in package
  -S, --status                              Lookup node status as well
  -T, --translate                           Translate IP addresses into names
  -r, --root-port                           Use root port 137 (Win95 only
                                            replies to this)
  -A, --lookup-by-ip                        Do a node status on <name> as an
                                            IP Address

Help options:
  -?, --help                                Show this help message
      --usage                               Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL               Set debug level
      --debug-stdout                        Send debug output to standard
                                            output
  -s, --configfile=CONFIGFILE               Use alternative configuration file
      --option=name=value                   Set smb.conf option from command
                                            line
  -l, --log-basename=LOGFILEBASE            Basename for log/debug files
      --leak-report                         enable talloc leak reporting on
                                            exit
      --leak-report-full                    enable full talloc leak reporting
                                            on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER     Use these name resolution services
                                            only
  -O, --socket-options=SOCKETOPTIONS        socket options to use
  -m, --max-protocol=MAXPROTOCOL            Set max protocol level
  -n, --netbiosname=NETBIOSNAME             Primary netbios name
      --netbios-scope=SCOPE                 Use this Netbios scope
  -W, --workgroup=WORKGROUP                 Set the workgroup name
      --realm=REALM                         Set the realm name

Version options:
  -V, --version                             Print version
```

***

**samba-regedit**

Ncurses based tool to manage the Samba registry

```
:~# samba-regedit --help
Usage: samba-regedit [OPTION...]

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER        Use these name resolution
                                               services only
  -O, --socket-options=SOCKETOPTIONS           socket options to use
  -m, --max-protocol=MAXPROTOCOL               Set max protocol level
  -n, --netbiosname=NETBIOSNAME                Primary netbios name
      --netbios-scope=SCOPE                    Use this Netbios scope
  -W, --workgroup=WORKGROUP                    Set the workgroup name
      --realm=REALM                            Set the realm name

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Version options:
  -V, --version                                Print version
```

***

**samba-tool**

Main Samba administration tool.

```
:~# samba-tool -h
Usage: samba-tool <subcommand>

Main samba administration tool.


Options:
  -h, --help       show this help message and exit

  Version Options:
    -V, --version  Display version number


Available subcommands:
  computer    - Computer management.
  contact     - Contact management.
  dbcheck     - Check local AD database for errors.
  delegation  - Delegation management.
  dns         - Domain Name Service (DNS) management.
  domain      - Domain management.
  drs         - Directory Replication Services (DRS) management.
  dsacl       - DS ACLs manipulation.
  forest      - Forest management.
  fsmo        - Flexible Single Master Operations (FSMO) roles management.
  gpo         - Group Policy Object (GPO) management.
  group       - Group management.
  ldapcmp     - Compare two ldap databases.
  ntacl       - NT ACLs manipulation.
  ou          - Organizational Units (OU) management.
  processes   - List processes (to aid debugging on systems without setproctitle).
  rodc        - Read-Only Domain Controller (RODC) management.
  schema      - Schema querying and management.
  sites       - Sites management.
  spn         - Service Principal Name (SPN) management.
  testparm    - Syntax check the configuration file.
  time        - Retrieve the time on a server.
  user        - User management.
  visualize   - Produces graphical representations of Samba network state.
For more help on a specific subcommand, please type: samba-tool <subcommand> (-h|--help)

```

***

**samba\_kcc**

```
:~# samba_kcc -h
Usage: samba_kcc [options]

Options:
  -h, --help            show this help message and exit
  --readonly            compute topology but do not update database
  --debug               debug output
  --verify              verify that assorted invariants are kept
  --list-verify-tests   list what verification actions are available and do
                        nothing else
  --dot-file-dir=DOT_FILE_DIR
                        Write Graphviz .dot files to this directory
  --seed=SEED           random number seed
  --importldif=<file>   import topology ldif file
  --exportldif=<file>   export topology ldif file
  -H <URL>, --URL=<URL>
                        LDB URL for database or target server
  --tmpdb=<file>        schemaless database file to create for ldif import
  --now=<date>          assume current time is this ('YYYYmmddHHMMSS[tz]',
                        default: system time)
  --forced-local-dsa=<DSA>
                        run calculations assuming the DSA is this DN
  --attempt-live-connections
                        Attempt to connect to other DSAs to test links
  --list-valid-dsas     Print a list of DSA dnstrs that could be used in
                        --forced-local-dsa
  --test-all-reps-from  Create and verify a graph of reps-from for every DSA
  --forget-local-links  pretend not to know the existing local topology
  --forget-intersite-links
                        pretend not to know the existing intersite topology

  Samba Common Options:
    -s FILE, --configfile=FILE
                        Configuration file
    -d DEBUGLEVEL, --debuglevel=DEBUGLEVEL
                        debug level
    --option=OPTION     set smb.conf option from command line
    --realm=REALM       set the realm name

  Credentials Options:
    --simple-bind-dn=DN
                        DN to use for a simple bind
    --password=PASSWORD
                        Password
    -U USERNAME, --username=USERNAME
                        Username
    -W WORKGROUP, --workgroup=WORKGROUP
                        Workgroup
    -N, --no-pass       Don't ask for a password
    --ipaddress=IPADDRESS
                        IP address of server
    -P, --machine-pass  Use stored machine account password
    --use-kerberos=desired|required|off
                        Use Kerberos authentication
    --use-krb5-ccache=KRB5CCNAME
                        Kerberos Credentials cache
    -k KERBEROS, --kerberos=KERBEROS
                        DEPRECATED: Migrate to --use-kerberos

  Version Options:
    -V, --version       Display version number
```

***

**smbpasswd**

The Samba encrypted password file Change a user’s SMB password

```
:~# smbpasswd -h
When run by root:
    smbpasswd [options] [username]
otherwise:
    smbpasswd [options]

options:
  -L                   local mode (must be first option)
  -h                   print this usage message
  -s                   use stdin for password prompt
  -c smb.conf file     Use the given path to the smb.conf file
  -D LEVEL             debug level
  -r MACHINE           remote machine
  -U USER              remote username (e.g. SAM/user)
extra options when run by root or in local mode:
  -a                   add user
  -d                   disable user
  -e                   enable user
  -i                   interdomain trust account
  -m                   machine trust account
  -n                   set no password
  -W                   use stdin ldap admin password
  -w PASSWORD          ldap admin password
  -x                   delete user
  -R ORDER             name resolve order
```

***

**testparm**

Check an smb.conf configuration file for internal correctness

```
:~# testparm --help
Usage: testparm [OPTION...] <config-file> [host-name] [host-ip]
  -s, --suppress-prompt           Suppress prompt for enter
  -v, --verbose                   Show default options too
  -l, --skip-logic-checks         Skip the global checks
      --show-all-parameters       Show the parameters, type, possible values
      --parameter-name=STRING     Limit testparm to a named parameter
      --section-name=STRING       Limit testparm to a named section

Help options:
  -?, --help                      Show this help message
      --usage                     Display brief usage message

Common debug options:
  -d, --debuglevel=DEBUGLEVEL     Set debug level
      --debug-stdout              Send debug output to standard output

Options:
      --option=name=value         Set smb.conf option from command line

Version options:
  -V, --version                   Print version
```

***

#### samba-dev <a href="#samba-dev" id="samba-dev"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as a domain controller or member server in both NT4-style and Active Directory domains.

This package contains include files shared by the various Samba-based libraries.

**Installed size:** `1.75 MB`\
**How to install:** `sudo apt install samba-dev`

<details>

<summary>Dependencies:</summary>

* libc6-dev
* libldb-dev
* libpopt-dev
* libtalloc-dev
* libtdb-dev
* libtevent-dev
* libwbclient-dev
* samba-libs

</details>

***

#### samba-dsdb-modules <a href="#samba-dsdb-modules" id="samba-dsdb-modules"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as a domain controller or member server in both NT4-style and Active Directory domains.

This package contains LDB plugins which add support for various Active Directory features to the LDB library.

**Installed size:** `1.51 MB`\
**How to install:** `sudo apt install samba-dsdb-modules`

<details>

<summary>Dependencies:</summary>

* libbsd0
* libc6
* libcrypt1
* libgnutls30
* libgpgme11
* libldb2
* libtalloc2
* libtdb1
* libtevent0
* samba-libs

</details>

***

#### samba-libs <a href="#samba-libs" id="samba-libs"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as a domain controller or member server in both NT4-style and Active Directory domains.

This package contains the shared libraries.

**Installed size:** `24.01 MB`\
**How to install:** `sudo apt install samba-libs`

<details>

<summary>Dependencies:</summary>

* libacl1
* libavahi-client3
* libavahi-common3
* libbsd0
* libc6
* libcap2
* libgnutls30
* libicu72
* libjansson4
* libldap-2.5-0
* libldb2
* libpam0g
* libpopt0
* libsystemd0
* libtalloc2
* libtdb1
* libtevent0
* libtirpc3
* libwbclient0
* zlib1g

</details>

***

#### samba-testsuite <a href="#samba-testsuite" id="samba-testsuite"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as a domain controller or member server in both NT4-style and Active Directory domains.

This package contains programs for testing the reliability and speed of SMB servers, Samba in particular.

**Installed size:** `9.68 MB`\
**How to install:** `sudo apt install samba-testsuite`

<details>

<summary>Dependencies:</summary>

* libbsd0
* libc6
* libgnutls30
* libldb2
* libpopt0
* libreadline8
* libsmbclient
* libtalloc2
* libtdb1
* libtevent0
* libwbclient0
* python3-samba
* samba-common-bin
* samba-libs
* winbind

</details>

**gentest**

Run random generic SMB operations against two SMB servers and show the differences in behavior

```
:~# gentest --help
Usage: <unc1> <unc2>
      --smb2                                   use SMB2 protocol
      --seed=INT                               Seed to use for randomizer
      --num-ops=INT                            num ops
      --oplocks                                use oplocks
      --showall                                display all operations
      --analyse                                do backtrack analysis
      --analysealways                          analysis always
      --analysecontinuous                      analysis continuous
      --ignore=STRING                          ignore from file
      --preset                                 use preset seeds
      --fast                                   use fast reconnect
      --unclist=STRING                         unclist
      --seedsfile=STRING                       seed file
      --user1=[DOMAIN/]USERNAME[%PASSWORD]     Set first network username
      --user2=[DOMAIN/]USERNAME[%PASSWORD]     Set second network username
      --maskindexing                           mask out the indexed file attrib
      --noeas                                  don't use extended attributes
      --noacls                                 don't use ACLs
      --skip-cleanup                           don't delete files at start
      --valid                                  generate only valid fields

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER        Use these name resolution
                                               services only
  -O, --socket-options=SOCKETOPTIONS           socket options to use
  -m, --max-protocol=MAXPROTOCOL               Set max protocol level
  -n, --netbiosname=NETBIOSNAME                Primary netbios name
      --netbios-scope=SCOPE                    Use this Netbios scope
  -W, --workgroup=WORKGROUP                    Set the workgroup name
      --realm=REALM                            Set the realm name

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Version options:
  -V, --version                                Print version

Deprecated legacy options:
  -k, --kerberos=STRING                        DEPRECATED: Migrate to
                                               --use-kerberos
```

***

**locktest**

Find differences in locking between two SMB servers

```
:~# locktest --help
Usage: <unc1> <unc2>
      --seed=INT                               Seed to use for randomizer
      --num-ops=INT                            num ops
      --lockrange=INT                          locking range
      --lockbase=INT                           locking base
      --minlength=INT                          min lock length
      --hidefails                              hide unlock fails
      --oplocks                                use oplocks
      --showall                                display all operations
      --analyse                                do backtrack analysis
      --zerozero                               do zero/zero lock
      --exacterrors                            use exact error codes
      --unclist=STRING                         unclist
      --user1=[DOMAIN/]USERNAME[%PASSWORD]     Set first network username
      --user2=[DOMAIN/]USERNAME[%PASSWORD]     Set second network username

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER        Use these name resolution
                                               services only
  -O, --socket-options=SOCKETOPTIONS           socket options to use
  -m, --max-protocol=MAXPROTOCOL               Set max protocol level
  -n, --netbiosname=NETBIOSNAME                Primary netbios name
      --netbios-scope=SCOPE                    Use this Netbios scope
  -W, --workgroup=WORKGROUP                    Set the workgroup name
      --realm=REALM                            Set the realm name

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Version options:
  -V, --version                                Print version

Deprecated legacy options:
  -k, --kerberos=STRING                        DEPRECATED: Migrate to
                                               --use-kerberos
```

***

**masktest**

Find differences in wildcard matching between Samba’s implementation and that of a remote server.

```
:~# masktest --help
Usage: <unc>
      --seed=INT                               Seed to use for randomizer
      --num-ops=INT                            num ops
      --maxlength=INT                          maximum length
      --dieonerror                             die on errors
      --showall                                display all operations
      --oldlist                                use old list call
      --maskchars=STRING                       mask characters
      --filechars=STRING                       file characters

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER        Use these name resolution
                                               services only
  -O, --socket-options=SOCKETOPTIONS           socket options to use
  -m, --max-protocol=MAXPROTOCOL               Set max protocol level
  -n, --netbiosname=NETBIOSNAME                Primary netbios name
      --netbios-scope=SCOPE                    Use this Netbios scope
  -W, --workgroup=WORKGROUP                    Set the workgroup name
      --realm=REALM                            Set the realm name

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Version options:
  -V, --version                                Print version

Deprecated legacy options:
  -k, --kerberos=STRING                        DEPRECATED: Migrate to
                                               --use-kerberos
```

***

**ndrdump**

DCE/RPC Packet Parser and Dumper

```
:~# ndrdump --help
Usage: ndrdump <pipe|uuid> <format> <in|out|struct> [<filename>]
  -c, --context-file=CTX-FILE         In-filename to parse first
      --validate                      try to validate the data
      --dump-data                     dump the hex data
      --load-dso=STRING               load from shared object file
      --ndr64                         Assume NDR64 data
      --quiet                         Don't actually dump anything
      --base64-input                  Read the input file in as a base64 string
      --hex-input                     Read the input file in as a hex dump
      --input=INPUT                   Provide the input on the command line
                                      (use with --base64-input)
      --print-after-parse-failure     Try to print structures that fail to
                                      parse (used to develop parsers,
                                      segfaults are likely).

Help options:
  -?, --help                          Show this help message
      --usage                         Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL         Set debug level
      --debug-stdout                  Send debug output to standard output
  -s, --configfile=CONFIGFILE         Use alternative configuration file
      --option=name=value             Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE      Basename for log/debug files
      --leak-report                   enable talloc leak reporting on exit
      --leak-report-full              enable full talloc leak reporting on exit

Version options:
  -V, --version                       Print version
```

***

**smbtorture**

Run a series of tests against a SMB server

```
:~# smbtorture --help
smbtorture 4.17.5-Debian
Usage: <binding>|<unc> TEST1 TEST2 ...
      --fullname                               use full name for the test
      --format=STRING                          Output format (one of: simple,
                                               subunit)
  -p, --smb-ports=STRING                       SMB ports
      --basedir=BASEDIR                        base directory
      --seed=INT                               Seed to use for randomizer
      --num-progs=INT                          num progs
      --num-ops=INT                            num ops
      --entries=INT                            entries
      --loadfile=STRING                        NBench load file to use
      --list-suites                            List available testsuites and
                                               exit
      --list                                   List available tests in
                                               specified suites and exit
      --unclist=STRING                         unclist
  -t, --timelimit=INT                          Set time limit (in seconds)
  -f, --failures=INT                           failures
  -D, --parse-dns=STRING                       parse-dns
  -X, --dangerous                              run dangerous tests (eg. wiping
                                               out password database)
      --load-module=SOFILE                     load tests from DSO file
      --shell                                  Run shell
  -T, --target=STRING                          samba3|samba4|other
  -a, --async                                  run async tests
      --num-async=INT                          number of simultaneous async
                                               requests
      --maximum-runtime=seconds                set maximum time for smbtorture
                                               to live
      --extra-user=STRING                      extra user credentials
      --load-list=STRING                       load a test id list from a text
                                               file

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER        Use these name resolution
                                               services only
  -O, --socket-options=SOCKETOPTIONS           socket options to use
  -m, --max-protocol=MAXPROTOCOL               Set max protocol level
  -n, --netbiosname=NETBIOSNAME                Primary netbios name
      --netbios-scope=SCOPE                    Use this Netbios scope
  -W, --workgroup=WORKGROUP                    Set the workgroup name
      --realm=REALM                            Set the realm name

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Version options:
  -V, --version                                Print version

Deprecated legacy options:
  -k, --kerberos=STRING                        DEPRECATED: Migrate to
                                               --use-kerberos
```

***

#### samba-vfs-modules <a href="#samba-vfs-modules" id="samba-vfs-modules"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as a domain controller or member server in both NT4-style and Active Directory domains.

Virtual FileSystem modules are stacked shared libraries extending the functionality of Samba. Some examples are:

* vfs\_acl\_xattr: Save NTFS-ACLs in Extended Attributes
* vfs\_audit: record selected Samba VFS operations in the system log
* vfs\_readonly: Make a Samba share read only for a specified time period
* vfs\_recycle: Give the same effect as the Recycle Bin on Windows computers
* vfs\_shadow\_copy2: Expose snapshots to Windows clients as shadow copies
* vfs\_worm: Disallow writes for older file

Note: The runtime dependencies of vfs\_ceph, vfs\_glusterfs and vfs\_snapper are moved to Recommends.

**Installed size:** `1.75 MB`\
**How to install:** `sudo apt install samba-vfs-modules`

<details>

<summary>Dependencies:</summary>

* libbsd0
* libc6
* libgnutls30
* libtalloc2
* libtdb1
* libtevent0
* libtirpc3
* liburing2
* samba-libs

</details>

***

#### smbclient <a href="#smbclient" id="smbclient"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file and printer sharing with Microsoft Windows, OS X, and other Unix systems.

This package contains command-line utilities for accessing Microsoft Windows and Samba servers, including smbclient, smbtar, and smbspool. Utilities for mounting shares locally are found in the package cifs-utils.

**Installed size:** `1.92 MB`\
**How to install:** `sudo apt install smbclient`

<details>

<summary>Dependencies:</summary>

* libarchive13
* libbsd0
* libc6
* libgnutls30
* libpopt0
* libreadline8
* libsmbclient
* libtalloc2
* libtevent0
* samba-common
* samba-libs

</details>

**cifsdd**

Convert and copy a file over SMB

```
:~# cifsdd --help
Usage: cifsdd [OPTION...]

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER        Use these name resolution
                                               services only
  -O, --socket-options=SOCKETOPTIONS           socket options to use
  -m, --max-protocol=MAXPROTOCOL               Set max protocol level
  -n, --netbiosname=NETBIOSNAME                Primary netbios name
      --netbios-scope=SCOPE                    Use this Netbios scope
  -W, --workgroup=WORKGROUP                    Set the workgroup name
      --realm=REALM                            Set the realm name

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Deprecated legacy options:
  -k, --kerberos=STRING                        DEPRECATED: Migrate to
                                               --use-kerberos

Version options:
  -V, --version                                Print version

CIFS dd options:
  bs=SIZE                force ibs and obs to SIZE bytes
  ibs=SIZE               read SIZE bytes at a time
  obs=SIZE               write SIZE bytes at a time
  count=COUNT            copy COUNT input blocks
  seek=COUNT             skip COUNT blocks at start of output
  skip=COUNT             skip COUNT blocks at start of input
  if=FILE                read input from FILE
  of=FILE                write output to FILE
  direct=BOOLEAN         use direct I/O if non-zero
  sync=BOOLEAN           use synchronous writes if non-zero
  oplock=BOOLEAN         take oplocks on the input and output files

FILE can be a local filename or a UNC path of the form //server/share/path.

```

***

**mdsearch**

Run Spotlight searches against an SMB server

```
:~# mdsearch --help
Usage: mdsearch [OPTIONS] <server> <share> <query>

  -p, --path=STRING                            Server-relative search path
  -L, --live                                   live query

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Deprecated legacy options:
  -k, --kerberos                               DEPRECATED: Migrate to
                                               --use-kerberos

Version options:
  -V, --version                                Print version
```

***

**rpcclient**

Tool for executing client side MS-RPC functions

```
:~# rpcclient --help
Usage: rpcclient [OPTION...] BINDING-STRING|HOST
Options:
  -c, --command=COMMANDS                       Execute semicolon separated cmds
  -I, --dest-ip=IP                             Specify destination IP address
  -p, --port=PORT                              Specify port number

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER        Use these name resolution
                                               services only
  -O, --socket-options=SOCKETOPTIONS           socket options to use
  -m, --max-protocol=MAXPROTOCOL               Set max protocol level
  -n, --netbiosname=NETBIOSNAME                Primary netbios name
      --netbios-scope=SCOPE                    Use this Netbios scope
  -W, --workgroup=WORKGROUP                    Set the workgroup name
      --realm=REALM                            Set the realm name

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Deprecated legacy options:
  -k, --kerberos                               DEPRECATED: Migrate to
                                               --use-kerberos

Version options:
  -V, --version                                Print version
```

***

**smbcacls**

Set or get ACLs on an NT file or directory names

```
:~# smbcacls --help
Usage: smbcacls //server1/share1 filename
ACLs look like: 'ACL:user:[ALLOWED|DENIED]/flags/permissions'
  -D, --delete=ACL                             Delete an acl
  -M, --modify=ACL                             Modify an acl
  -a, --add=ACL                                Add an acl
  -S, --set=ACLS                               Set acls
  -C, --chown=USERNAME                         Change ownership of a file
  -G, --chgrp=GROUPNAME                        Change group ownership of a file
  -I, --inherit=STRING                         Inherit allow|remove|copy
      --propagate-inheritance                  Supports propagation of
                                               inheritable ACE(s) when used in
                                               conjunction with add, delete,
                                               set or modify
      --numeric                                Don't resolve sids or masks to
                                               names
      --sddl                                   Output and input acls in sddl
                                               format
      --query-security-info=INT                The security-info flags for
                                               queries
      --set-security-info=INT                  The security-info flags for
                                               modifications
  -t, --test-args                              Test arguments
      --domain-sid=SID                         Domain SID for sddl
  -x, --maximum-access                         Query maximum permissions

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER        Use these name resolution
                                               services only
  -O, --socket-options=SOCKETOPTIONS           socket options to use
  -m, --max-protocol=MAXPROTOCOL               Set max protocol level
  -n, --netbiosname=NETBIOSNAME                Primary netbios name
      --netbios-scope=SCOPE                    Use this Netbios scope
  -W, --workgroup=WORKGROUP                    Set the workgroup name
      --realm=REALM                            Set the realm name

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Deprecated legacy options:
  -k, --kerberos                               DEPRECATED: Migrate to
                                               --use-kerberos

Version options:
  -V, --version                                Print version
```

***

**smbclient**

Ftp-like client to access SMB/CIFS resources on servers

```
:~# smbclient --help
Usage: smbclient [OPTIONS] service <password>
  -M, --message=HOST                           Send message
  -I, --ip-address=IP                          Use this IP to connect to
  -E, --stderr                                 Write messages to stderr
                                               instead of stdout
  -L, --list=HOST                              Get a list of shares available
                                               on a host
  -T, --tar=<c|x>IXFvgbNan                     Command line tar
  -D, --directory=DIR                          Start from directory
  -c, --command=STRING                         Execute semicolon separated
                                               commands
  -b, --send-buffer=BYTES                      Changes the transmit/send buffer
  -t, --timeout=SECONDS                        Changes the per-operation
                                               timeout
  -p, --port=PORT                              Port to connect to
  -g, --grepable                               Produce grepable output
  -q, --quiet                                  Suppress help message
  -B, --browse                                 Browse SMB servers using DNS

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Connection options:
  -R, --name-resolve=NAME-RESOLVE-ORDER        Use these name resolution
                                               services only
  -O, --socket-options=SOCKETOPTIONS           socket options to use
  -m, --max-protocol=MAXPROTOCOL               Set max protocol level
  -n, --netbiosname=NETBIOSNAME                Primary netbios name
      --netbios-scope=SCOPE                    Use this Netbios scope
  -W, --workgroup=WORKGROUP                    Set the workgroup name
      --realm=REALM                            Set the realm name

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Deprecated legacy options:
  -k, --kerberos                               DEPRECATED: Migrate to
                                               --use-kerberos

Version options:
  -V, --version                                Print version
```

***

**smbcquotas**

Set or get QUOTAs of NTFS 5 shares

```
kali:~# smbcquotas --help
Usage: smbcquotas //server1/share1
  -u, --quota-user=USER                        Show quotas for user
  -L, --list                                   List user quotas
  -F, --fs                                     Show filesystem quotas
  -S, --set=SETSTRING                          Set acls
SETSTRING:
                                               UQLIM:<username>/<softlimit>/<hardlimit> for user quotas
FSQLIM:<softlimit>/<hardlimit> for filesystem defaults
FSQFLAGS:QUOTA_ENABLED/DENY_DISK/LOG_SOFTLIMIT/LOG_HARD_LIMIT
  -n, --numeric                                Don't resolve sids or limits to
                                               names
  -v, --verbose                                be verbose
  -t, --test-args                              Test arguments
  -m, --max-protocol=LEVEL                     Set the max protocol level

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Deprecated legacy options:
  -k, --kerberos                               DEPRECATED: Migrate to
                                               --use-kerberos

Version options:
  -V, --version                                Print version
```

***

**smbget**

Wget-like utility for download files over SMB

```
:~# smbget --help
Usage: smbget [OPTION...]
  -w, --workgroup=STRING      Workgroup to use (optional)
  -U, --user=STRING           Username to use
  -a, --guest                 Work as user guest
  -n, --nonprompt             Don't ask anything (non-interactive)
  -d, --debuglevel=INT        Debuglevel to use
  -e, --encrypt               Encrypt SMB transport
  -r, --resume                Automatically resume aborted files
  -u, --update                Download only when remote file is newer than
                              local file or local file is missing
  -R, --recursive             Recursively download files
  -b, --blocksize=INT         Change number of bytes in a block
  -o, --outputfile=STRING     Write downloaded data to specified file
  -O, --stdout                Write data to stdout
  -D, --dots                  Show dots as progress indication
  -q, --quiet                 Be quiet
  -v, --verbose               Be verbose
  -f, --rcfile=STRING         Use specified rc file

Help options:
  -?, --help                  Show this help message
      --usage                 Display brief usage message
```

***

**smbspool**

Send a print file to an SMB printer

```
:~# smbspool -h
Usage: smbspool [DEVICE_URI] job-id user title copies options [file]
       The DEVICE_URI environment variable can also contain the
       destination printer:

           smb://[username:][workgroup/]server[:port]/printer
```

***

**smbtar**

Shell script for backing up SMB/CIFS shares directly to UNIX tape drives

```
:~# smbtar -h
Illegal option -h
Usage: smbtar [<options>] [<include/exclude files>]
Function: backup/restore a Windows PC directories to a local tape file
Options:         (Description)                 (Default)
  -r             Restore from tape file to PC  Save from PC to tapefile
  -i             Incremental mode              Full backup mode
  -a             Reset archive bit mode        Don't reset archive bit
  -v             Verbose mode: echo command    Don't echo anything
  -s <server>    Specify PC Server             
  -p <password>  Specify PC Password           
  -x <share>     Specify PC Share              backup
  -X             Exclude mode                  Include
  -N <newer>     File for date comparison      
  -b <blocksize> Specify tape's blocksize      
  -d <dir>       Specify a directory in share  \
  -l <log>       Specify a Samba Log Level     2
  -u <user>      Specify User Name             root
  -t <tape>      Specify Tape device           tar.out

Invalid switch specified - abort.
```

***

**smbtree**

A text based smb network browser

```
:~# smbtree --help
Usage: [OPTION...]
  -D, --domains                                List only domains (workgroups)
                                               of tree
  -S, --servers                                List domains(workgroups) and
                                               servers of tree

Help options:
  -?, --help                                   Show this help message
      --usage                                  Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL                  Set debug level
      --debug-stdout                           Send debug output to standard
                                               output
  -s, --configfile=CONFIGFILE                  Use alternative configuration
                                               file
      --option=name=value                      Set smb.conf option from
                                               command line
  -l, --log-basename=LOGFILEBASE               Basename for log/debug files
      --leak-report                            enable talloc leak reporting on
                                               exit
      --leak-report-full                       enable full talloc leak
                                               reporting on exit

Credential options:
  -U, --user=[DOMAIN/]USERNAME[%PASSWORD]      Set the network username
  -N, --no-pass                                Don't ask for a password
      --password=STRING                        Password
      --pw-nt-hash                             The supplied password is the NT
                                               hash
  -A, --authentication-file=FILE               Get the credentials from a file
  -P, --machine-pass                           Use stored machine account
                                               password
      --simple-bind-dn=DN                      DN to use for a simple bind
      --use-kerberos=desired|required|off      Use Kerberos authentication
      --use-krb5-ccache=CCACHE                 Credentials cache location for
                                               Kerberos
      --use-winbind-ccache                     Use the winbind ccache for
                                               authentication
      --client-protection=sign|encrypt|off     Configure used protection for
                                               client connections

Version options:
  -V, --version                                Print version
```

***

#### winbind <a href="#winbind" id="winbind"></a>

Samba is an implementation of the SMB/CIFS protocol for Unix systems, providing support for cross-platform file sharing with Microsoft Windows, OS X, and other Unix systems. Samba can also function as a domain controller or member server in both NT4-style and Active Directory domains.

This package provides winbindd, a daemon which integrates authentication and directory service (user/group lookup) mechanisms from a Windows domain on a Linux system.

Winbind based user/group lookups via /etc/nsswitch.conf can be enabled via the libnss-winbind package. Winbind based Windows domain authentication can be enabled via the libpam-winbind package.

**Installed size:** `1.55 MB`\
**How to install:** `sudo apt install winbind`

<details>

<summary>Dependencies:</summary>

* init-system-helpers
* libbsd0
* libc6
* libgnutls30
* libldap-2.5-0
* libpopt0
* libtalloc2
* libtdb1
* libtevent0
* libwbclient0
* passwd
* samba-common
* samba-common-bin
* samba-libs

</details>

**ntlm\_auth**

Tool to allow external access to Winbind’s NTLM authentication function

```
:~# ntlm_auth --help
Usage: [OPTION...]
      --helper-protocol=helper protocol to use     operate as a stdio-based
                                                   helper
      --username=STRING                            username
      --domain=STRING                              domain name
      --workstation=STRING                         workstation
      --challenge=STRING                           challenge (HEX encoded)
      --lm-response=STRING                         LM Response to the
                                                   challenge (HEX encoded)
      --nt-response=STRING                         NT or NTLMv2 Response to
                                                   the challenge (HEX encoded)
      --password=STRING                            User's plaintext password
      --request-lm-key                             Retrieve LM session key
                                                   (or, with --diagnostics,
                                                   expect LM support)
      --request-nt-key                             Retrieve User (NT) session
                                                   key
      --use-cached-creds                           Use cached credentials if
                                                   no password is given
      --allow-mschapv2                             Explicitly allow MSCHAPv2
      --offline-logon                              Use cached passwords when
                                                   DC is offline
      --diagnostics                                Perform diagnostics on the
                                                   authentication chain
      --require-membership-of=STRING               Require that a user be a
                                                   member of this group
                                                   (either name or SID) for
                                                   authentication to succeed
      --pam-winbind-conf=STRING                    Require that request must
                                                   set
                                                   WBFLAG_PAM_CONTACT_TRUSTDOM
                                                   when krb5 auth is required
      --target-service=STRING                      Target service (eg http)
      --target-hostname=STRING                     Target hostname

Help options:
  -?, --help                                       Show this help message
      --usage                                      Display brief usage message

Common debug options:
  -d, --debuglevel=DEBUGLEVEL                      Set debug level
      --debug-stdout                               Send debug output to
                                                   standard output

Config file:
      --configfile=CONFIGFILE                      Use alternative
                                                   configuration file

Options:
      --option=name=value                          Set smb.conf option from
                                                   command line

Version options:
  -V, --version                                    Print version
```

***

**wbinfo**

Query information from winbind daemon

```
:~# wbinfo --help
Usage: wbinfo [OPTION...]
  -u, --domain-users                                 Lists all domain users
  -g, --domain-groups                                Lists all domain groups
  -N, --WINS-by-name=NETBIOS-NAME                    Converts NetBIOS name to
                                                     IP
  -I, --WINS-by-ip=IP                                Converts IP address to
                                                     NetBIOS name
  -n, --name-to-sid=NAME                             Converts name to sid
  -s, --sid-to-name=SID                              Converts sid to name
      --sid-to-fullname=SID                          Converts sid to fullname
  -R, --lookup-rids=RIDs                             Converts RIDs to names
      --lookup-sids=Sid-List                         Converts SIDs to types
                                                     and names
  -U, --uid-to-sid=UID                               Converts uid to sid
  -G, --gid-to-sid=GID                               Converts gid to sid
  -S, --sid-to-uid=SID                               Converts sid to uid
  -Y, --sid-to-gid=SID                               Converts sid to gid
      --allocate-uid                                 Get a new UID out of idmap
      --allocate-gid                                 Get a new GID out of idmap
      --set-uid-mapping=UID,SID                      Create or modify uid to
                                                     sid mapping in idmap
      --set-gid-mapping=GID,SID                      Create or modify gid to
                                                     sid mapping in idmap
      --remove-uid-mapping=UID,SID                   Remove uid to sid mapping
                                                     in idmap
      --remove-gid-mapping=GID,SID                   Remove gid to sid mapping
                                                     in idmap
      --sids-to-unix-ids=Sid-List                    Translate SIDs to Unix IDs
      --unix-ids-to-sids=ID-List (u<num> g<num>)     Translate Unix IDs to SIDs
  -t, --check-secret                                 Check shared secret
  -c, --change-secret                                Change shared secret
  -P, --ping-dc                                      Check the NETLOGON
                                                     connection
  -m, --trusted-domains                              List trusted domains
      --all-domains                                  List all domains (trusted
                                                     and own domain)
      --own-domain                                   List own domain
      --sequence                                     Deprecated command, see
                                                     --online-status
      --online-status                                Show whether domains
                                                     maintain an active
                                                     connection
  -D, --domain-info=STRING                           Show most of the info we
                                                     have about the domain
  -i, --user-info=USER                               Get user info
      --uid-info=UID                                 Get user info from uid
      --group-info=GROUP                             Get group info
      --user-sidinfo=SID                             Get user info from sid
      --gid-info=GID                                 Get group info from gid
  -r, --user-groups=USER                             Get user groups
      --user-domgroups=SID                           Get user domain groups
      --sid-aliases=SID                              Get sid aliases
      --user-sids=SID                                Get user group sids for
                                                     user SID
  -a, --authenticate=user%password                   authenticate user
      --pam-logon=user%password                      do a pam logon equivalent
      --logoff                                       log off user
      --logoff-user=STRING                           username to log off
      --logoff-uid=INT                               uid to log off
      --set-auth-user=user%password                  Store user and password
                                                     used by winbindd (root
                                                     only)
      --ccache-save=user%password                    Store user and password
                                                     for ccache operation
      --getdcname=domainname                         Get a DC name for a
                                                     foreign domain
      --dsgetdcname=domainname                       Find a DC for a domain
      --dc-info=domainname                           Find the currently known
                                                     DCs
      --get-auth-user                                Retrieve user and
                                                     password used by winbindd
                                                     (root only)
  -p, --ping                                         Ping winbindd to see if
                                                     it is alive
      --domain=domain                                Define to the domain to
                                                     restrict operation
  -K, --krb5auth=user%password                       authenticate user using
                                                     Kerberos
      --krb5ccname=krb5ccname                        authenticate user using
                                                     Kerberos and specific
                                                     credential cache type
      --separator                                    Get the active winbind
                                                     separator
      --verbose                                      Print additional
                                                     information per command
      --change-user-password=STRING                  Change the password for a
                                                     user
      --ntlmv1                                       Use NTLMv1 cryptography
                                                     for user authentication
      --ntlmv2                                       Use NTLMv2 cryptography
                                                     for user authentication
      --lanman                                       Use lanman cryptography
                                                     for user authentication

Help options:
  -?, --help                                         Show this help message
      --usage                                        Display brief usage
                                                     message

Version options:
  -V, --version                                      Print version
```

***

**winbindd**

Name Service Switch daemon for resolving names from NT servers

```
:~# winbindd --help
Usage: winbindd [OPTION...]
  -n, --no-caching                   Disable caching

Help options:
  -?, --help                         Show this help message
      --usage                        Display brief usage message

Common Samba options:
  -d, --debuglevel=DEBUGLEVEL        Set debug level
      --debug-stdout                 Send debug output to standard output
  -s, --configfile=CONFIGFILE        Use alternative configuration file
      --option=name=value            Set smb.conf option from command line
  -l, --log-basename=LOGFILEBASE     Basename for log/debug files
      --leak-report                  enable talloc leak reporting on exit
      --leak-report-full             enable full talloc leak reporting on exit

Daemon options:
  -D, --daemon                       Become a daemon (default)
  -i, --interactive                  Run interactive (not a daemon) and log to
                                     stdout
  -F, --foreground                   Run daemon in foreground (for
                                     daemontools, etc.)
      --no-process-group             Don't create a new process group

Version options:
  -V, --version                      Print version
```

***

Updated on: 2023-Mar-08\


***
