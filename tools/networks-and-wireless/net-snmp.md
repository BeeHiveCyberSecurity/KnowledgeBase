---
description: >-
  Net-SNMP is an open-source suite of tools for managing and monitoring network
  devices. It supports various devices and operating systems, security features,
  and extensions.
---

# 🌐 net-snmp

Net-SNMP is a free and open-source suite of tools used to manage and monitor network-attached devices. It is based on the Simple Network Management Protocol (SNMP) and provides a range of features for monitoring and controlling network devices such as routers, switches, servers, and printers.

The Net-SNMP suite includes a number of different tools, including the snmpget and snmpset utilities for retrieving and setting data from SNMP-capable devices, the snmptrap utility for receiving and processing SNMP traps, and the snmpwalk utility for walking through the SNMP tree of a target device.

One of the key benefits of Net-SNMP is its ability to work with a wide range of different devices and operating systems. It supports both IPv4 and IPv6, and can communicate with devices running a variety of different operating systems, including Linux, Windows, and MacOS.

Net-SNMP also includes support for a range of different security features, including SNMPv3, which provides authentication and encryption for SNMP traffic. This makes it a valuable tool for securing networked devices and protecting against attacks such as SNMP spoofing.

In addition to its core features, Net-SNMP also includes a range of different plugins and extensions, which can be used to extend its functionality and add support for specific devices or applications. For example, there are plugins available for monitoring Apache web servers, MySQL databases, and Postfix mail servers.

Overall, Net-SNMP is a powerful and flexible suite of tools for managing and monitoring network-attached devices. Its support for a wide range of different devices and operating systems, along with its robust security features and extensibility, make it a valuable tool for network administrators and security professionals.

#### libnetsnmptrapd40 <a href="#libnetsnmptrapd40" id="libnetsnmptrapd40"></a>

The Simple Network Management Protocol (SNMP) provides a framework for the exchange of management information between agents (servers) and clients.

The Net-SNMP trap library contains functions for receiving SNMP trap and inform messages.

**Installed size:** `70 KB`\
**How to install:** `sudo apt install libnetsnmptrapd40`

<details>

<summary>Dependencies:</summary>

* libc6
* libmariadb3
* libsnmp-base
* libsnmp40

</details>

***

#### libsnmp-base <a href="#libsnmp-base" id="libsnmp-base"></a>

The Simple Network Management Protocol (SNMP) provides a framework for the exchange of management information between agents (servers) and clients.

This package includes documentation and MIBs (Management Information Bases) for the SNMP libraries, agents and applications. MIBs contain a formal description of the data that can be managed using SNMP and applications.

NOTE: If you want the OIDs (Object Identifiers) to resolve to their text description, you need to activate the non-free repository and install the “snmp-mibs-downloader” package.

**Installed size:** `2.11 MB`\
**How to install:** `sudo apt install libsnmp-base`

***

#### libsnmp-dev <a href="#libsnmp-dev" id="libsnmp-dev"></a>

The Simple Network Management Protocol (SNMP) provides a framework for the exchange of management information between agents (servers) and clients.

The Net-SNMP development files include the library headers, static libraries, net-snmp-config scripts and documentation needed for development of custom SNMP applications.

**Installed size:** `1.25 MB`\
**How to install:** `sudo apt install libsnmp-dev`

<details>

<summary>Dependencies:</summary>

* libc6-dev
* libnetsnmptrapd40
* libpci-dev
* libsensors-dev
* libsnmp40
* libssl-dev
* libwrap0-dev
* procps

</details>

**mib2c**

Generate template code for extending the agent

```
:~# mib2c -h
/usr/bin/mib2c [-h] [-c configfile] [-f prefix] mibNode

  -h		This message.

  -c configfile	Specifies the configuration file to use
		that dictates what the output of mib2c will look like.

  -I PATH	Specifies a path to look for configuration files in

  -f prefix	Specifies the output prefix to use.  All code
		will be put into prefix.c and prefix.h

  -d		debugging output (don't do it.  trust me.)

  -S VAR=VAL	Set $VAR variable to $VAL

  -i		Don't run indent on the resulting code

  -s		Don't look for mibNode.sed and run sed on the resulting code

  mibNode	The name of the top level mib node you want to
		generate code for.  By default, the code will be stored in
		mibNode.c and mibNode.h (use the -f flag to change this)

```

***

**mib2c-update**

Script to merge custom code into updated mib2c code

```
:~# mib2c-update -h
Starting regneration of ipAddressTable using mib2c.mfd.conf at 2023-03-08_09.39
Creating patch for your custom code
   no custom code!
mib2c -h -c mib2c.mfd.conf  ipAddressTable
/usr/bin/mib2c [-h] [-c configfile] [-f prefix] mibNode

  -h		This message.

  -c configfile	Specifies the configuration file to use
		that dictates what the output of mib2c will look like.

  -I PATH	Specifies a path to look for configuration files in

  -f prefix	Specifies the output prefix to use.  All code
		will be put into prefix.c and prefix.h

  -d		debugging output (don't do it.  trust me.)

  -S VAR=VAL	Set $VAR variable to $VAL

  -i		Don't run indent on the resulting code

  -s		Don't look for mibNode.sed and run sed on the resulting code

  mibNode	The name of the top level mib node you want to
		generate code for.  By default, the code will be stored in
		mibNode.c and mibNode.h (use the -f flag to change this)

```

***

**net-snmp-config**

Returns information about installed net-snmp libraries and binaries

```
:~# net-snmp-config -h
unknown option -h

Usage:
  net-snmp-config [--cflags] [--agent-libs] [--libs] [--version]
                  ... [see below for complete flag list]

    --version         displays the net-snmp version number
    --indent-options  displays the indent options from the Coding Style
    --debug-tokens    displays a example command line to search to source
                      code for a list of available debug tokens

  SNMP Setup commands:

    --create-snmpv3-user creates a SNMPv3 user in Net-SNMP config file.
                         See net-snmp-create-v3-user --help for list of
                         accepted options.

  These options produce the various compilation flags needed when
  building external SNMP applications:

    --base-lib-cflags lists additional compilation flags needed for linking
                      against libsnmp
    --base-cflags     lists additional compilation flags needed
    --cflags          lists additional compilation flags needed
                      (includes -I. and extra developer warning flags)

  These options produce the various link flags needed when
  building external SNMP applications:

    --libs            lists libraries needed for building applications
    --agent-libs      lists libraries needed for building subagents

  These options produce various link flags broken down into parts.
  (Most of the time the simple options above should be used.)

    --libdir              path to netsnmp libraries

    --base-agent-libs     netsnmp specific agent libraries

    --netsnmp-libs        netsnmp specific libraries (with path)
    --netsnmp-agent-libs  netsnmp specific agent libraries (with path)

    --ldflags             link flags for external libraries
    --external-libs       external libraries needed by netsnmp libs
    --external-agent-libs external libraries needed by netsnmp agent libs

  These options produce various link flags used when linking an
  external application against an uninstalled build directory.

    --build-includes      include path to build/source includes
    --build-lib-dirs      link path to libraries
    --build-lib-deps      path to libraries for dependency target
    --build-command       command to compile $3... to $2

  Automated subagent building (produces an OUTPUTNAME binary file):
  [this feature has not been tested very well yet.  use at your risk.]

    --compile-subagent OUTPUTNAME [--norm] [--cflags flags]
                                  [--ldflags flags] mibmodule1.c [...]]

         --norm           leave the generated .c file around to read.
         --cflags flags   extra cflags to use (e.g. -I...).
         --ldflags flags  extra ld flags to use (e.g. -L... -l...).

  Details on how the net-snmp package was compiled:

    --configure-options   display original configure arguments
    --prefix              display the installation prefix
    --snmpd-module-list   display the modules compiled into the agent
    --default-mibs        display default list of MIBs
    --default-mibdirs     display default list of MIB directories
    --snmpconfpath        display default SNMPCONFPATH
    --persistent-directory display default persistent directory
    --perlprog            display path to perl for the perl modules

```

***

#### libsnmp-perl <a href="#libsnmp-perl" id="libsnmp-perl"></a>

The Simple Network Management Protocol (SNMP) provides a framework for the exchange of management information between agents (servers) and clients.

The Net-SNMP Perl5 support files provide the Perl functions for integration of SNMP into applications written in Perl.

**Installed size:** `2.10 MB`\
**How to install:** `sudo apt install libsnmp-perl`

<details>

<summary>Dependencies:</summary>

* libc6
* libnetsnmptrapd40
* libsnmp40
* perl
* perlapi-5.36.0

</details>

***

#### libsnmp40 <a href="#libsnmp40" id="libsnmp40"></a>

The Simple Network Management Protocol (SNMP) provides a framework for the exchange of management information between agents (servers) and clients.

The Net-SNMP library contains common functions for the construction, sending, receiving, decoding, and manipulation of the SNMP requests and responses.

**Installed size:** `5.27 MB`\
**How to install:** `sudo apt install libsnmp40`

<details>

<summary>Dependencies:</summary>

* libc6
* libpci3
* libperl5.36
* libsensors5
* libsnmp-base
* libssl3
* libwrap0

</details>

***

#### snmp <a href="#snmp" id="snmp"></a>

The Simple Network Management Protocol (SNMP) provides a framework for the exchange of management information between agents (servers) and clients.

The Net-SNMP applications are a collection of command line clients for issuing SNMP requests to agents.

**Installed size:** `681 KB`\
**How to install:** `sudo apt install snmp`

<details>

<summary>Dependencies:</summary>

* libc6
* libsnmp-base
* libsnmp40
* libssl3

</details>

**agentxtrap**

Send an AgentX NotifyPDU to an AgentX master agent

```
:~# agentxtrap -h
USAGE: agentxtrap [OPTIONS] TRAP-PARAMETERS

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h			display this help message
  -V			display package version number
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
  -d			dump all traffic
  -P MIBOPTS		Toggle various defaults controlling mib parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -c context
  -U uptime
  -x ADDRESS		use ADDRESS as AgentX address

TRAP-PARAMETERS:
  trapoid [OID TYPE VALUE] ...
```

***

**encode\_keychange**

Produce the KeyChange string for SNMPv3

```
:~# encode_keychange -h
Usage: encode_keychange [-fhPvV] -t (md5|sha1) [-O "<old_passphrase>"][-N "<new_passphrase>"][-E [0x]<engineID>]

    -E [0x]<engineID>		EngineID used for kul generation.
    -f				Force passphrases to be read from stdin.
    -h				Help.
    -N "<new_passphrase>"	Passphrase used to generate new Ku.
    -O "<old_passphrase>"	Passphrase used to generate old Ku.
    -P				Turn off prompt indicators.
    -t md5 | sha1		HMAC hash transform type.
    -v				Verbose.
    -V				Visible.  Echo passphrases to terminal.
		

Only -t is mandatory.  The transform is used to convert P=>Ku, convert
    Ku=>Kul, and to hash the old Kul with the random bits.

    Passphrase will be taken from the first successful source as follows:
	a) Commandline options,
	b) The file "/root/.snmp/passphrase.ek",
	c) stdin  -or-  User input from the terminal.

-f will require reading from the stdin/terminal, ignoring a) and b).
    -P will prevent prompts for passphrases to stdout from being printed.

    <engineID> is interpreted as a hex string when preceded by "0x",
    otherwise it is created to contain "text".  If nothing is given,
    <engineID> is constructed from the first IP address for the local host.
		
```

***

**fixproc**

Fixes a process by performing the specified action.

```
:~# man fixproc
fixproc(1)                         Net-SNMP                         fixproc(1)

NAME
       fixproc - Fixes a process by performing the specified action.

SYNOPSIS
       fixproc  [-min  n] [-max n] [-check | -kill | -restart | -exist | -fix]
       proc ...

DESCRIPTION
       Fixes a process named "proc" by performing the specified  action.   The
       actions  can  be  check,  kill,  restart, exist, or fix.  The action is
       specified on the command line or is read from a default database, which
       describes  the  default  action to take for each process.  The database
       format and the meaning of each action are described below.

OPTIONS
       -min n minimum number of processes that should be running, defaults  to
              1

       -max n maximum  number of processes that should be running, defaults to
              1

       -check check process against database /local/etc/fixproc.conf.

       -kill  kill process, wait 5 seconds, kill -9 if still exist

       -restart
              kill process, wait 5 seconds, kill -9 if still exist, then start
              again

       -exist checks if proc exists in ps && (min <= num. of processes <= max)

       -fix   check  process against database /local/etc/fixproc.conf. Perform
              defined action, if check fails.

V5.9.3                            16 Nov 2006                       fixproc(1)
```

***

**snmp-bridge-mib**

Provide Linux bridge information via SNMP

```
:~# snmp-bridge-mib -h
MIB search path: /root/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf
Cannot find module (SNMPv2-MIB): At line 1 in (none)
Cannot find module (IF-MIB): At line 1 in (none)
Cannot find module (IP-MIB): At line 1 in (none)
Cannot find module (TCP-MIB): At line 1 in (none)
Cannot find module (UDP-MIB): At line 1 in (none)
Cannot find module (HOST-RESOURCES-MIB): At line 1 in (none)
Cannot find module (NOTIFICATION-LOG-MIB): At line 1 in (none)
Cannot find module (DISMAN-EVENT-MIB): At line 1 in (none)
Cannot find module (DISMAN-SCHEDULE-MIB): At line 1 in (none)
Cannot find module (HOST-RESOURCES-TYPES): At line 1 in (none)
Cannot find module (MTA-MIB): At line 1 in (none)
Cannot find module (NETWORK-SERVICES-MIB): At line 1 in (none)
Cannot find module (SNMPv2-TC): At line 15 in /usr/share/snmp/mibs/UCD-DISKIO-MIB.txt
Cannot find module (SNMPv2-SMI): At line 34 in /usr/share/snmp/mibs/UCD-SNMP-MIB.txt
Cannot find module (HCNUM-TC): At line 37 in /usr/share/snmp/mibs/UCD-SNMP-MIB.txt
Cannot find module (SNMPv2-TC): At line 40 in /usr/share/snmp/mibs/UCD-SNMP-MIB.txt
Did not find 'enterprises' in module #-1 (/usr/share/snmp/mibs/UCD-SNMP-MIB.txt)
Did not find 'CounterBasedGauge64' in module #-1 (/usr/share/snmp/mibs/UCD-SNMP-MIB.txt)
Did not find 'DisplayString' in module #-1 (/usr/share/snmp/mibs/UCD-SNMP-MIB.txt)
Did not find 'TruthValue' in module #-1 (/usr/share/snmp/mibs/UCD-SNMP-MIB.txt)
Unlinked OID in UCD-SNMP-MIB: ucdavis ::= { enterprises 2021 }
Undefined identifier: enterprises near line 42 of /usr/share/snmp/mibs/UCD-SNMP-MIB.txt
Did not find 'DisplayString' in module #-1 (/usr/share/snmp/mibs/UCD-DISKIO-MIB.txt)
Did not find 'ucdExperimental' in module UCD-SNMP-MIB (/usr/share/snmp/mibs/UCD-DISKIO-MIB.txt)
Unlinked OID in UCD-DISKIO-MIB: ucdDiskIOMIB ::= { ucdExperimental 15 }
Undefined identifier: ucdExperimental near line 19 of /usr/share/snmp/mibs/UCD-DISKIO-MIB.txt
Cannot find module (SNMPv2-TC): At line 10 in /usr/share/snmp/mibs/UCD-DLMOD-MIB.txt
Did not find 'DisplayString' in module #-1 (/usr/share/snmp/mibs/UCD-DLMOD-MIB.txt)
Did not find 'ucdExperimental' in module UCD-SNMP-MIB (/usr/share/snmp/mibs/UCD-DLMOD-MIB.txt)
Unlinked OID in UCD-DLMOD-MIB: ucdDlmodMIB ::= { ucdExperimental 14 }
Undefined identifier: ucdExperimental near line 13 of /usr/share/snmp/mibs/UCD-DLMOD-MIB.txt
Cannot find module (SNMPv2-TC): At line 15 in /usr/share/snmp/mibs/LM-SENSORS-MIB.txt
Did not find 'DisplayString' in module #-1 (/usr/share/snmp/mibs/LM-SENSORS-MIB.txt)
Did not find 'ucdExperimental' in module UCD-SNMP-MIB (/usr/share/snmp/mibs/LM-SENSORS-MIB.txt)
Unlinked OID in LM-SENSORS-MIB: lmSensors ::= { ucdExperimental 16 }
Undefined identifier: ucdExperimental near line 32 of /usr/share/snmp/mibs/LM-SENSORS-MIB.txt
Did not find 'ucdavis' in module UCD-SNMP-MIB (/usr/share/snmp/mibs/UCD-DEMO-MIB.txt)
Unlinked OID in UCD-DEMO-MIB: ucdDemoMIB ::= { ucdavis 14 }
Undefined identifier: ucdavis near line 7 of /usr/share/snmp/mibs/UCD-DEMO-MIB.txt
Cannot find module (SNMP-TARGET-MIB): At line 1 in (none)
Cannot find module (SNMP-FRAMEWORK-MIB): At line 9 in /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Cannot find module (SNMPv2-SMI): At line 8 in /usr/share/snmp/mibs/NET-SNMP-MIB.txt
Did not find 'enterprises' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-MIB.txt)
Unlinked OID in NET-SNMP-MIB: netSnmp ::= { enterprises 8072 }
Undefined identifier: enterprises near line 10 of /usr/share/snmp/mibs/NET-SNMP-MIB.txt
Cannot find module (SNMPv2-TC): At line 21 in /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Did not find 'SnmpAdminString' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt)
Did not find 'netSnmpObjects' in module NET-SNMP-MIB (/usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt)
Did not find 'netSnmpModuleIDs' in module NET-SNMP-MIB (/usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt)
Did not find 'netSnmpNotifications' in module NET-SNMP-MIB (/usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt)
Did not find 'netSnmpGroups' in module NET-SNMP-MIB (/usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt)
Did not find 'DisplayString' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt)
Did not find 'RowStatus' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt)
Did not find 'TruthValue' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt)
Unlinked OID in NET-SNMP-AGENT-MIB: nsAgentNotifyGroup ::= { netSnmpGroups 9 }
Undefined identifier: netSnmpGroups near line 545 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsTransactionGroup ::= { netSnmpGroups 8 }
Undefined identifier: netSnmpGroups near line 536 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsConfigGroups ::= { netSnmpGroups 7 }
Undefined identifier: netSnmpGroups near line 515 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsCacheGroup ::= { netSnmpGroups 4 }
Undefined identifier: netSnmpGroups near line 505 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsModuleGroup ::= { netSnmpGroups 2 }
Undefined identifier: netSnmpGroups near line 495 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: netSnmpAgentMIB ::= { netSnmpModuleIDs 2 }
Undefined identifier: netSnmpModuleIDs near line 24 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsTransactions ::= { netSnmpObjects 8 }
Undefined identifier: netSnmpObjects near line 55 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsConfiguration ::= { netSnmpObjects 7 }
Undefined identifier: netSnmpObjects near line 54 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsErrorHistory ::= { netSnmpObjects 6 }
Undefined identifier: netSnmpObjects near line 53 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsCache ::= { netSnmpObjects 5 }
Undefined identifier: netSnmpObjects near line 52 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsDLMod ::= { netSnmpObjects 4 }
Undefined identifier: netSnmpObjects near line 51 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsExtensions ::= { netSnmpObjects 3 }
Undefined identifier: netSnmpObjects near line 50 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsMibRegistry ::= { netSnmpObjects 2 }
Undefined identifier: netSnmpObjects near line 49 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsVersion ::= { netSnmpObjects 1 }
Undefined identifier: netSnmpObjects near line 48 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsNotifyRestart ::= { netSnmpNotifications 3 }
Undefined identifier: netSnmpNotifications near line 482 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsNotifyShutdown ::= { netSnmpNotifications 2 }
Undefined identifier: netSnmpNotifications near line 476 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Unlinked OID in NET-SNMP-AGENT-MIB: nsNotifyStart ::= { netSnmpNotifications 1 }
Undefined identifier: netSnmpNotifications near line 470 of /usr/share/snmp/mibs/NET-SNMP-AGENT-MIB.txt
Cannot find module (SNMP-FRAMEWORK-MIB): At line 1 in (none)
Cannot find module (SNMP-MPD-MIB): At line 1 in (none)
Cannot find module (SNMP-USER-BASED-SM-MIB): At line 1 in (none)
Cannot find module (SNMP-VIEW-BASED-ACM-MIB): At line 1 in (none)
Cannot find module (SNMP-COMMUNITY-MIB): At line 1 in (none)
Cannot find module (IPV6-ICMP-MIB): At line 1 in (none)
Cannot find module (IPV6-MIB): At line 1 in (none)
Cannot find module (IPV6-TCP-MIB): At line 1 in (none)
Cannot find module (IPV6-UDP-MIB): At line 1 in (none)
Cannot find module (IP-FORWARD-MIB): At line 1 in (none)
Cannot find module (SNMP-FRAMEWORK-MIB): At line 10 in /usr/share/snmp/mibs/NET-SNMP-PASS-MIB.txt
Cannot find module (SNMP-FRAMEWORK-MIB): At line 10 in /usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt
Cannot find module (SNMPv2-TC): At line 12 in /usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt
Cannot find module (INET-ADDRESS-MIB): At line 13 in /usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt
Did not find 'SnmpAdminString' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt)
Did not find 'netSnmp' in module NET-SNMP-MIB (/usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt)
Did not find 'RowStatus' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt)
Did not find 'StorageType' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt)
Did not find 'InetAddressType' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt)
Did not find 'InetAddress' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt)
Unlinked OID in NET-SNMP-EXAMPLES-MIB: netSnmpExamples ::= { netSnmp 2 }
Undefined identifier: netSnmp near line 16 of /usr/share/snmp/mibs/NET-SNMP-EXAMPLES-MIB.txt
Did not find 'SnmpAdminString' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-PASS-MIB.txt)
Did not find 'netSnmpExamples' in module NET-SNMP-EXAMPLES-MIB (/usr/share/snmp/mibs/NET-SNMP-PASS-MIB.txt)
Unlinked OID in NET-SNMP-PASS-MIB: netSnmpPassExamples ::= { netSnmpExamples 255 }
Undefined identifier: netSnmpExamples near line 14 of /usr/share/snmp/mibs/NET-SNMP-PASS-MIB.txt
Cannot find module (SNMPv2-TC): At line 16 in /usr/share/snmp/mibs/NET-SNMP-EXTEND-MIB.txt
Did not find 'nsExtensions' in module NET-SNMP-AGENT-MIB (/usr/share/snmp/mibs/NET-SNMP-EXTEND-MIB.txt)
Did not find 'DisplayString' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-EXTEND-MIB.txt)
Did not find 'RowStatus' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-EXTEND-MIB.txt)
Did not find 'StorageType' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-EXTEND-MIB.txt)
Unlinked OID in NET-SNMP-EXTEND-MIB: nsExtendGroups ::= { nsExtensions 3 }
Undefined identifier: nsExtensions near line 39 of /usr/share/snmp/mibs/NET-SNMP-EXTEND-MIB.txt
Unlinked OID in NET-SNMP-EXTEND-MIB: nsExtendObjects ::= { nsExtensions 2 }
Undefined identifier: nsExtensions near line 38 of /usr/share/snmp/mibs/NET-SNMP-EXTEND-MIB.txt
Unlinked OID in NET-SNMP-EXTEND-MIB: netSnmpExtendMIB ::= { nsExtensions 1 }
Undefined identifier: nsExtensions near line 19 of /usr/share/snmp/mibs/NET-SNMP-EXTEND-MIB.txt
Cannot find module (SNMP-NOTIFICATION-MIB): At line 1 in (none)
Cannot find module (SNMPv2-TM): At line 1 in (none)
Cannot find module (SNMP-FRAMEWORK-MIB): At line 9 in /usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt
Cannot find module (SNMP-VIEW-BASED-ACM-MIB): At line 16 in /usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt
Cannot find module (SNMPv2-TC): At line 25 in /usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt
Did not find 'SnmpAdminString' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Did not find 'netSnmpObjects' in module NET-SNMP-MIB (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Did not find 'netSnmpGroups' in module NET-SNMP-MIB (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Did not find 'vacmGroupName' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Did not find 'vacmAccessContextPrefix' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Did not find 'vacmAccessSecurityModel' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Did not find 'vacmAccessSecurityLevel' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Did not find 'DisplayString' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Did not find 'RowStatus' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Did not find 'StorageType' in module #-1 (/usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt)
Unlinked OID in NET-SNMP-VACM-MIB: netSnmpVacmMIB ::= { netSnmpObjects 9 }
Undefined identifier: netSnmpObjects near line 28 of /usr/share/snmp/mibs/NET-SNMP-VACM-MIB.txt
Cannot adopt OID in UCD-SNMP-MIB: logMatchRegExCompilation ::= { logMatchEntry 101 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchErrorFlag ::= { logMatchEntry 100 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchCycle ::= { logMatchEntry 11 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchCount ::= { logMatchEntry 10 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchCounter ::= { logMatchEntry 9 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchCurrentCount ::= { logMatchEntry 8 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchCurrentCounter ::= { logMatchEntry 7 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchGlobalCount ::= { logMatchEntry 6 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchGlobalCounter ::= { logMatchEntry 5 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchRegEx ::= { logMatchEntry 4 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchFilename ::= { logMatchEntry 3 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchName ::= { logMatchEntry 2 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchIndex ::= { logMatchEntry 1 }
Cannot adopt OID in NET-SNMP-VACM-MIB: nsVacmAccessEntry ::= { nsVacmAccessTable 1 }
Cannot adopt OID in UCD-SNMP-MIB: extErrFixCmd ::= { extEntry 103 }
Cannot adopt OID in UCD-SNMP-MIB: extErrFix ::= { extEntry 102 }
Cannot adopt OID in UCD-SNMP-MIB: extOutput ::= { extEntry 101 }
Cannot adopt OID in UCD-SNMP-MIB: extResult ::= { extEntry 100 }
Cannot adopt OID in UCD-SNMP-MIB: extCommand ::= { extEntry 3 }
Cannot adopt OID in UCD-SNMP-MIB: extNames ::= { extEntry 2 }
Cannot adopt OID in UCD-SNMP-MIB: extIndex ::= { extEntry 1 }
Cannot adopt OID in UCD-DEMO-MIB: ucdDemoPublic ::= { ucdDemoMIBObjects 1 }
Cannot adopt OID in UCD-DLMOD-MIB: dlmodTable ::= { ucdDlmodMIB 2 }
Cannot adopt OID in UCD-DLMOD-MIB: dlmodNextIndex ::= { ucdDlmodMIB 1 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExamples ::= { netSnmp 2 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpConformance ::= { netSnmp 5 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpNotificationPrefix ::= { netSnmp 4 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpExperimental ::= { netSnmp 9999 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpEnumerations ::= { netSnmp 3 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpObjects ::= { netSnmp 1 }
Cannot adopt OID in UCD-SNMP-MIB: versionDoDebugging ::= { version 20 }
Cannot adopt OID in UCD-SNMP-MIB: versionSavePersistentData ::= { version 13 }
Cannot adopt OID in UCD-SNMP-MIB: versionRestartAgent ::= { version 12 }
Cannot adopt OID in UCD-SNMP-MIB: versionUpdateConfig ::= { version 11 }
Cannot adopt OID in UCD-SNMP-MIB: versionClearCache ::= { version 10 }
Cannot adopt OID in UCD-SNMP-MIB: versionConfigureOptions ::= { version 6 }
Cannot adopt OID in UCD-SNMP-MIB: versionIdent ::= { version 5 }
Cannot adopt OID in UCD-SNMP-MIB: versionCDate ::= { version 4 }
Cannot adopt OID in UCD-SNMP-MIB: versionDate ::= { version 3 }
Cannot adopt OID in UCD-SNMP-MIB: versionTag ::= { version 2 }
Cannot adopt OID in UCD-SNMP-MIB: versionIndex ::= { version 1 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleHeartbeatNotification ::= { netSnmpExampleNotificationPrefix 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsCacheStatus ::= { nsCacheEntry 3 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsCacheTimeout ::= { nsCacheEntry 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsCachedOID ::= { nsCacheEntry 1 }
Cannot adopt OID in UCD-SNMP-MIB: unknown ::= { ucdSnmpAgent 255 }
Cannot adopt OID in UCD-SNMP-MIB: dragonfly ::= { ucdSnmpAgent 17 }
Cannot adopt OID in UCD-SNMP-MIB: macosx ::= { ucdSnmpAgent 16 }
Cannot adopt OID in UCD-SNMP-MIB: aix ::= { ucdSnmpAgent 15 }
Cannot adopt OID in UCD-SNMP-MIB: hpux11 ::= { ucdSnmpAgent 14 }
Cannot adopt OID in UCD-SNMP-MIB: win32 ::= { ucdSnmpAgent 13 }
Cannot adopt OID in UCD-SNMP-MIB: openbsd ::= { ucdSnmpAgent 12 }
Cannot adopt OID in UCD-SNMP-MIB: bsdi ::= { ucdSnmpAgent 11 }
Cannot adopt OID in UCD-SNMP-MIB: linux ::= { ucdSnmpAgent 10 }
Cannot adopt OID in UCD-SNMP-MIB: irix ::= { ucdSnmpAgent 9 }
Cannot adopt OID in UCD-SNMP-MIB: freebsd ::= { ucdSnmpAgent 8 }
Cannot adopt OID in UCD-SNMP-MIB: netbsd1 ::= { ucdSnmpAgent 7 }
Cannot adopt OID in UCD-SNMP-MIB: hpux10 ::= { ucdSnmpAgent 6 }
Cannot adopt OID in UCD-SNMP-MIB: ultrix ::= { ucdSnmpAgent 5 }
Cannot adopt OID in UCD-SNMP-MIB: osf ::= { ucdSnmpAgent 4 }
Cannot adopt OID in UCD-SNMP-MIB: solaris ::= { ucdSnmpAgent 3 }
Cannot adopt OID in UCD-SNMP-MIB: sunos4 ::= { ucdSnmpAgent 2 }
Cannot adopt OID in UCD-SNMP-MIB: hpux9 ::= { ucdSnmpAgent 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendOutputGroup ::= { nsExtendGroups 2 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendConfigGroup ::= { nsExtendGroups 1 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIOEntry ::= { diskIOTable 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsTransactionEntry ::= { nsTransactionTable 1 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpGroups ::= { netSnmpConformance 2 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpCompliances ::= { netSnmpConformance 1 }
Cannot adopt OID in UCD-SNMP-MIB: mrModuleName ::= { mrEntry 2 }
Cannot adopt OID in UCD-SNMP-MIB: mrIndex ::= { mrEntry 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsDebugTokenEntry ::= { nsDebugTokenTable 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendStatus ::= { nsExtendConfigEntry 21 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendStorage ::= { nsExtendConfigEntry 20 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendRunType ::= { nsExtendConfigEntry 7 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendExecType ::= { nsExtendConfigEntry 6 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendCacheTime ::= { nsExtendConfigEntry 5 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendInput ::= { nsExtendConfigEntry 4 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendArgs ::= { nsExtendConfigEntry 3 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendCommand ::= { nsExtendConfigEntry 2 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendToken ::= { nsExtendConfigEntry 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsModuleTable ::= { nsMibRegistry 1 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpPlaypen ::= { netSnmpExperimental 9999 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpIETFWGEntry ::= { netSnmpIETFWGTable 1 }
Cannot adopt OID in UCD-SNMP-MIB: prErrFixCmd ::= { prEntry 103 }
Cannot adopt OID in UCD-SNMP-MIB: prErrFix ::= { prEntry 102 }
Cannot adopt OID in UCD-SNMP-MIB: prErrMessage ::= { prEntry 101 }
Cannot adopt OID in UCD-SNMP-MIB: prErrorFlag ::= { prEntry 100 }
Cannot adopt OID in UCD-SNMP-MIB: prCount ::= { prEntry 5 }
Cannot adopt OID in UCD-SNMP-MIB: prMax ::= { prEntry 4 }
Cannot adopt OID in UCD-SNMP-MIB: prMin ::= { prEntry 3 }
Cannot adopt OID in UCD-SNMP-MIB: prNames ::= { prEntry 2 }
Cannot adopt OID in UCD-SNMP-MIB: prIndex ::= { prEntry 1 }
Cannot adopt OID in UCD-DLMOD-MIB: dlmodEntry ::= { dlmodTable 1 }
Cannot adopt OID in UCD-SNMP-MIB: memSwapErrorMsg ::= { memory 101 }
Cannot adopt OID in UCD-SNMP-MIB: memSwapError ::= { memory 100 }
Cannot adopt OID in UCD-SNMP-MIB: memSysAvail ::= { memory 27 }
Cannot adopt OID in UCD-SNMP-MIB: memCachedX ::= { memory 26 }
Cannot adopt OID in UCD-SNMP-MIB: memBufferX ::= { memory 25 }
Cannot adopt OID in UCD-SNMP-MIB: memSharedX ::= { memory 24 }
Cannot adopt OID in UCD-SNMP-MIB: memMinimumSwapX ::= { memory 23 }
Cannot adopt OID in UCD-SNMP-MIB: memTotalFreeX ::= { memory 22 }
Cannot adopt OID in UCD-SNMP-MIB: memAvailRealX ::= { memory 21 }
Cannot adopt OID in UCD-SNMP-MIB: memTotalRealX ::= { memory 20 }
Cannot adopt OID in UCD-SNMP-MIB: memAvailSwapX ::= { memory 19 }
Cannot adopt OID in UCD-SNMP-MIB: memTotalSwapX ::= { memory 18 }
Cannot adopt OID in UCD-SNMP-MIB: memUsedRealTXT ::= { memory 17 }
Cannot adopt OID in UCD-SNMP-MIB: memUsedSwapTXT ::= { memory 16 }
Cannot adopt OID in UCD-SNMP-MIB: memCached ::= { memory 15 }
Cannot adopt OID in UCD-SNMP-MIB: memBuffer ::= { memory 14 }
Cannot adopt OID in UCD-SNMP-MIB: memShared ::= { memory 13 }
Cannot adopt OID in UCD-SNMP-MIB: memMinimumSwap ::= { memory 12 }
Cannot adopt OID in UCD-SNMP-MIB: memTotalFree ::= { memory 11 }
Cannot adopt OID in UCD-SNMP-MIB: memAvailRealTXT ::= { memory 10 }
Cannot adopt OID in UCD-SNMP-MIB: memTotalRealTXT ::= { memory 9 }
Cannot adopt OID in UCD-SNMP-MIB: memAvailSwapTXT ::= { memory 8 }
Cannot adopt OID in UCD-SNMP-MIB: memTotalSwapTXT ::= { memory 7 }
Cannot adopt OID in UCD-SNMP-MIB: memAvailReal ::= { memory 6 }
Cannot adopt OID in UCD-SNMP-MIB: memTotalReal ::= { memory 5 }
Cannot adopt OID in UCD-SNMP-MIB: memAvailSwap ::= { memory 4 }
Cannot adopt OID in UCD-SNMP-MIB: memTotalSwap ::= { memory 3 }
Cannot adopt OID in UCD-SNMP-MIB: memErrorName ::= { memory 2 }
Cannot adopt OID in UCD-SNMP-MIB: memIndex ::= { memory 1 }
Cannot adopt OID in UCD-DEMO-MIB: ucdDemoMIBObjects ::= { ucdDemoMIB 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsModuleTimeout ::= { nsModuleEntry 6 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsModuleModes ::= { nsModuleEntry 5 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsModuleName ::= { nsModuleEntry 4 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsmRegistrationPriority ::= { nsModuleEntry 3 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsmRegistrationPoint ::= { nsModuleEntry 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsmContextName ::= { nsModuleEntry 1 }
Cannot adopt OID in LM-SENSORS-MIB: lmMiscSensorsEntry ::= { lmMiscSensorsTable 1 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpNotificationObjects ::= { netSnmpNotificationPrefix 1 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpNotifications ::= { netSnmpNotificationPrefix 0 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassTable ::= { netSnmpPassExamples 2 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassOIDValue ::= { netSnmpPassExamples 99 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassInteger64 ::= { netSnmpPassExamples 8 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassCounter64 ::= { netSnmpPassExamples 7 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassGauge ::= { netSnmpPassExamples 6 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassCounter ::= { netSnmpPassExamples 5 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassIpAddress ::= { netSnmpPassExamples 4 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassTimeTicks ::= { netSnmpPassExamples 3 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassString ::= { netSnmpPassExamples 1 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpDomains ::= { netSnmpEnumerations 3 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpAgentOIDs ::= { netSnmpEnumerations 2 }
Cannot adopt OID in NET-SNMP-MIB: netSnmpModuleIDs ::= { netSnmpEnumerations 1 }
Cannot adopt OID in LM-SENSORS-MIB: lmFanSensorsEntry ::= { lmFanSensorsTable 1 }
Cannot adopt OID in LM-SENSORS-MIB: lmTempSensorsEntry ::= { lmTempSensorsTable 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsModuleGroup ::= { netSnmpGroups 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsCacheGroup ::= { netSnmpGroups 4 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsConfigGroups ::= { netSnmpGroups 7 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsTransactionGroup ::= { netSnmpGroups 8 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsAgentNotifyGroup ::= { netSnmpGroups 9 }
Cannot adopt OID in UCD-SNMP-MIB: fileEntry ::= { fileTable 1 }
Cannot adopt OID in NET-SNMP-VACM-MIB: nsVacmStatus ::= { nsVacmAccessEntry 5 }
Cannot adopt OID in NET-SNMP-VACM-MIB: nsVacmStorageType ::= { nsVacmAccessEntry 4 }
Cannot adopt OID in NET-SNMP-VACM-MIB: nsVacmViewName ::= { nsVacmAccessEntry 3 }
Cannot adopt OID in NET-SNMP-VACM-MIB: nsVacmContextMatch ::= { nsVacmAccessEntry 2 }
Cannot adopt OID in NET-SNMP-VACM-MIB: nsVacmAuthType ::= { nsVacmAccessEntry 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: netSnmpExtendMIB ::= { nsExtensions 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendObjects ::= { nsExtensions 2 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendGroups ::= { nsExtensions 3 }
Cannot adopt OID in LM-SENSORS-MIB: lmVoltSensorsEntry ::= { lmVoltSensorsTable 1 }
Cannot adopt OID in NET-SNMP-MIB: netSnmp ::= { enterprises 8072 }
Cannot adopt OID in UCD-SNMP-MIB: ucdavis ::= { enterprises 2021 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIOBusyTime ::= { diskIOEntry 14 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIONWrittenX ::= { diskIOEntry 13 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIONReadX ::= { diskIOEntry 12 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIOLA15 ::= { diskIOEntry 11 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIOLA5 ::= { diskIOEntry 10 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIOLA1 ::= { diskIOEntry 9 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIOWrites ::= { diskIOEntry 6 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIOReads ::= { diskIOEntry 5 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIONWritten ::= { diskIOEntry 4 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIONRead ::= { diskIOEntry 3 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIODevice ::= { diskIOEntry 2 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIOIndex ::= { diskIOEntry 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsTransactionMode ::= { nsTransactionEntry 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsTransactionID ::= { nsTransactionEntry 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsDebugTokenStatus ::= { nsDebugTokenEntry 4 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsDebugTokenPrefix ::= { nsDebugTokenEntry 2 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: nsIETFWGChair2 ::= { netSnmpIETFWGEntry 3 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: nsIETFWGChair1 ::= { netSnmpIETFWGEntry 2 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: nsIETFWGName ::= { netSnmpIETFWGEntry 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsLoggingTable ::= { nsConfigLogging 1 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpHostsEntry ::= { netSnmpHostsTable 1 }
Cannot adopt OID in UCD-DLMOD-MIB: dlmodStatus ::= { dlmodEntry 5 }
Cannot adopt OID in UCD-DLMOD-MIB: dlmodError ::= { dlmodEntry 4 }
Cannot adopt OID in UCD-DLMOD-MIB: dlmodPath ::= { dlmodEntry 3 }
Cannot adopt OID in UCD-DLMOD-MIB: dlmodName ::= { dlmodEntry 2 }
Cannot adopt OID in UCD-DLMOD-MIB: dlmodIndex ::= { dlmodEntry 1 }
Cannot adopt OID in LM-SENSORS-MIB: lmMiscSensorsValue ::= { lmMiscSensorsEntry 3 }
Cannot adopt OID in LM-SENSORS-MIB: lmMiscSensorsDevice ::= { lmMiscSensorsEntry 2 }
Cannot adopt OID in LM-SENSORS-MIB: lmMiscSensorsIndex ::= { lmMiscSensorsEntry 1 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassEntry ::= { netSnmpPassTable 1 }
Cannot adopt OID in LM-SENSORS-MIB: lmSensors ::= { ucdExperimental 16 }
Cannot adopt OID in UCD-DLMOD-MIB: ucdDlmodMIB ::= { ucdExperimental 14 }
Cannot adopt OID in UCD-DISKIO-MIB: ucdDiskIOMIB ::= { ucdExperimental 15 }
Cannot adopt OID in UCD-SNMP-MIB: dskEntry ::= { dskTable 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: netSnmpAgentMIB ::= { netSnmpModuleIDs 2 }
Cannot adopt OID in LM-SENSORS-MIB: lmFanSensorsValue ::= { lmFanSensorsEntry 3 }
Cannot adopt OID in LM-SENSORS-MIB: lmFanSensorsDevice ::= { lmFanSensorsEntry 2 }
Cannot adopt OID in LM-SENSORS-MIB: lmFanSensorsIndex ::= { lmFanSensorsEntry 1 }
Cannot adopt OID in LM-SENSORS-MIB: lmTempSensorsValue ::= { lmTempSensorsEntry 3 }
Cannot adopt OID in LM-SENSORS-MIB: lmTempSensorsDevice ::= { lmTempSensorsEntry 2 }
Cannot adopt OID in LM-SENSORS-MIB: lmTempSensorsIndex ::= { lmTempSensorsEntry 1 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchTable ::= { logMatch 2 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchMaxEntries ::= { logMatch 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsLoggingEntry ::= { nsLoggingTable 1 }
Cannot adopt OID in UCD-SNMP-MIB: fileErrorMsg ::= { fileEntry 101 }
Cannot adopt OID in UCD-SNMP-MIB: fileErrorFlag ::= { fileEntry 100 }
Cannot adopt OID in UCD-SNMP-MIB: fileMax ::= { fileEntry 4 }
Cannot adopt OID in UCD-SNMP-MIB: fileSize ::= { fileEntry 3 }
Cannot adopt OID in UCD-SNMP-MIB: fileName ::= { fileEntry 2 }
Cannot adopt OID in UCD-SNMP-MIB: fileIndex ::= { fileEntry 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendOutput2Table ::= { nsExtendObjects 4 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendOutput1Table ::= { nsExtendObjects 3 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendConfigTable ::= { nsExtendObjects 2 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendNumEntries ::= { nsExtendObjects 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendOutput1Entry ::= { nsExtendOutput1Table 1 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuNumCpus ::= { systemStats 67 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawGuestNice ::= { systemStats 66 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawGuest ::= { systemStats 65 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawSteal ::= { systemStats 64 }
Cannot adopt OID in UCD-SNMP-MIB: ssRawSwapOut ::= { systemStats 63 }
Cannot adopt OID in UCD-SNMP-MIB: ssRawSwapIn ::= { systemStats 62 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawSoftIRQ ::= { systemStats 61 }
Cannot adopt OID in UCD-SNMP-MIB: ssRawContexts ::= { systemStats 60 }
Cannot adopt OID in UCD-SNMP-MIB: ssRawInterrupts ::= { systemStats 59 }
Cannot adopt OID in UCD-SNMP-MIB: ssIORawReceived ::= { systemStats 58 }
Cannot adopt OID in UCD-SNMP-MIB: ssIORawSent ::= { systemStats 57 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawInterrupt ::= { systemStats 56 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawKernel ::= { systemStats 55 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawWait ::= { systemStats 54 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawIdle ::= { systemStats 53 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawSystem ::= { systemStats 52 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawNice ::= { systemStats 51 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuRawUser ::= { systemStats 50 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuIdle ::= { systemStats 11 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuSystem ::= { systemStats 10 }
Cannot adopt OID in UCD-SNMP-MIB: ssCpuUser ::= { systemStats 9 }
Cannot adopt OID in UCD-SNMP-MIB: ssSysContext ::= { systemStats 8 }
Cannot adopt OID in UCD-SNMP-MIB: ssSysInterrupts ::= { systemStats 7 }
Cannot adopt OID in UCD-SNMP-MIB: ssIOReceive ::= { systemStats 6 }
Cannot adopt OID in UCD-SNMP-MIB: ssIOSent ::= { systemStats 5 }
Cannot adopt OID in UCD-SNMP-MIB: ssSwapOut ::= { systemStats 4 }
Cannot adopt OID in UCD-SNMP-MIB: ssSwapIn ::= { systemStats 3 }
Cannot adopt OID in UCD-SNMP-MIB: ssErrorName ::= { systemStats 2 }
Cannot adopt OID in UCD-SNMP-MIB: ssIndex ::= { systemStats 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendOutput2Entry ::= { nsExtendOutput2Table 1 }
Cannot adopt OID in UCD-SNMP-MIB: laEntry ::= { laTable 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsCacheTable ::= { nsCache 3 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsCacheEnabled ::= { nsCache 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsCacheDefaultTimeout ::= { nsCache 1 }
Cannot adopt OID in UCD-SNMP-MIB: logMatchEntry ::= { logMatchTable 1 }
Cannot adopt OID in UCD-SNMP-MIB: extEntry ::= { extTable 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsConfigLogging ::= { nsConfiguration 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsConfigDebug ::= { nsConfiguration 1 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleString ::= { netSnmpExampleScalars 3 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleSleeper ::= { netSnmpExampleScalars 2 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleInteger ::= { netSnmpExampleScalars 1 }
Cannot adopt OID in LM-SENSORS-MIB: lmVoltSensorsValue ::= { lmVoltSensorsEntry 3 }
Cannot adopt OID in LM-SENSORS-MIB: lmVoltSensorsDevice ::= { lmVoltSensorsEntry 2 }
Cannot adopt OID in LM-SENSORS-MIB: lmVoltSensorsIndex ::= { lmVoltSensorsEntry 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsCacheEntry ::= { nsCacheTable 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsDebugTokenTable ::= { nsConfigDebug 4 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsDebugDumpPdu ::= { nsConfigDebug 3 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsDebugOutputAll ::= { nsConfigDebug 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsDebugEnabled ::= { nsConfigDebug 1 }
Cannot adopt OID in UCD-DEMO-MIB: ucdDemoPassphrase ::= { ucdDemoPublic 4 }
Cannot adopt OID in UCD-DEMO-MIB: ucdDemoUserList ::= { ucdDemoPublic 3 }
Cannot adopt OID in UCD-DEMO-MIB: ucdDemoPublicString ::= { ucdDemoPublic 2 }
Cannot adopt OID in UCD-DEMO-MIB: ucdDemoResetKeys ::= { ucdDemoPublic 1 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleHeartbeatName ::= { netSnmpExampleNotificationObjects 2 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleHeartbeatRate ::= { netSnmpExampleNotificationObjects 1 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassExamples ::= { netSnmpExamples 255 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleNotifications ::= { netSnmpExamples 3 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleTables ::= { netSnmpExamples 2 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleScalars ::= { netSnmpExamples 1 }
Cannot adopt OID in NET-SNMP-VACM-MIB: nsVacmAccessTable ::= { netSnmpVacmMIB 1 }
Cannot adopt OID in UCD-SNMP-MIB: ucdShutdown ::= { ucdTraps 2 }
Cannot adopt OID in UCD-SNMP-MIB: ucdStart ::= { ucdTraps 1 }
Cannot adopt OID in LM-SENSORS-MIB: lmMiscSensorsTable ::= { lmSensors 5 }
Cannot adopt OID in LM-SENSORS-MIB: lmVoltSensorsTable ::= { lmSensors 4 }
Cannot adopt OID in LM-SENSORS-MIB: lmFanSensorsTable ::= { lmSensors 3 }
Cannot adopt OID in LM-SENSORS-MIB: lmTempSensorsTable ::= { lmSensors 2 }
Cannot adopt OID in LM-SENSORS-MIB: lmSensorsMIB ::= { lmSensors 1 }
Cannot adopt OID in UCD-SNMP-MIB: mrEntry ::= { mrTable 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendConfigEntry ::= { nsExtendConfigTable 1 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpHostRowStatus ::= { netSnmpHostsEntry 5 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpHostStorage ::= { netSnmpHostsEntry 4 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpHostAddress ::= { netSnmpHostsEntry 3 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpHostAddressType ::= { netSnmpHostsEntry 2 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpHostName ::= { netSnmpHostsEntry 1 }
Cannot adopt OID in UCD-SNMP-MIB: prEntry ::= { prTable 1 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleNotification ::= { netSnmpExampleNotifications 1 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleNotificationObjects ::= { netSnmpExampleNotifications 2 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpExampleNotificationPrefix ::= { netSnmpExampleNotifications 0 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpHostsTable ::= { netSnmpExampleTables 2 }
Cannot adopt OID in NET-SNMP-EXAMPLES-MIB: netSnmpIETFWGTable ::= { netSnmpExampleTables 1 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassOID ::= { netSnmpPassEntry 3 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassInteger ::= { netSnmpPassEntry 2 }
Cannot adopt OID in NET-SNMP-PASS-MIB: netSnmpPassIndex ::= { netSnmpPassEntry 1 }
Cannot adopt OID in NET-SNMP-VACM-MIB: netSnmpVacmMIB ::= { netSnmpObjects 9 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsVersion ::= { netSnmpObjects 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsMibRegistry ::= { netSnmpObjects 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsExtensions ::= { netSnmpObjects 3 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsDLMod ::= { netSnmpObjects 4 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsCache ::= { netSnmpObjects 5 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsErrorHistory ::= { netSnmpObjects 6 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsConfiguration ::= { netSnmpObjects 7 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsTransactions ::= { netSnmpObjects 8 }
Cannot adopt OID in UCD-DEMO-MIB: ucdDemoMIB ::= { ucdavis 14 }
Cannot adopt OID in UCD-SNMP-MIB: logMatch ::= { ucdavis 16 }
Cannot adopt OID in UCD-SNMP-MIB: fileTable ::= { ucdavis 15 }
Cannot adopt OID in UCD-SNMP-MIB: ucdTraps ::= { ucdavis 251 }
Cannot adopt OID in UCD-SNMP-MIB: systemStats ::= { ucdavis 11 }
Cannot adopt OID in UCD-SNMP-MIB: mrTable ::= { ucdavis 102 }
Cannot adopt OID in UCD-SNMP-MIB: snmperrs ::= { ucdavis 101 }
Cannot adopt OID in UCD-SNMP-MIB: version ::= { ucdavis 100 }
Cannot adopt OID in UCD-SNMP-MIB: laTable ::= { ucdavis 10 }
Cannot adopt OID in UCD-SNMP-MIB: dskTable ::= { ucdavis 9 }
Cannot adopt OID in UCD-SNMP-MIB: memory ::= { ucdavis 4 }
Cannot adopt OID in UCD-SNMP-MIB: extTable ::= { ucdavis 8 }
Cannot adopt OID in UCD-SNMP-MIB: prTable ::= { ucdavis 2 }
Cannot adopt OID in UCD-SNMP-MIB: ucdSnmpAgent ::= { ucdavis 250 }
Cannot adopt OID in UCD-SNMP-MIB: ucdExperimental ::= { ucdavis 13 }
Cannot adopt OID in UCD-SNMP-MIB: ucdInternal ::= { ucdavis 12 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsModuleEntry ::= { nsModuleTable 1 }
Cannot adopt OID in UCD-SNMP-MIB: dskErrorMsg ::= { dskEntry 101 }
Cannot adopt OID in UCD-SNMP-MIB: dskErrorFlag ::= { dskEntry 100 }
Cannot adopt OID in UCD-SNMP-MIB: dskUsedHigh ::= { dskEntry 16 }
Cannot adopt OID in UCD-SNMP-MIB: dskUsedLow ::= { dskEntry 15 }
Cannot adopt OID in UCD-SNMP-MIB: dskAvailHigh ::= { dskEntry 14 }
Cannot adopt OID in UCD-SNMP-MIB: dskAvailLow ::= { dskEntry 13 }
Cannot adopt OID in UCD-SNMP-MIB: dskTotalHigh ::= { dskEntry 12 }
Cannot adopt OID in UCD-SNMP-MIB: dskTotalLow ::= { dskEntry 11 }
Cannot adopt OID in UCD-SNMP-MIB: dskPercentNode ::= { dskEntry 10 }
Cannot adopt OID in UCD-SNMP-MIB: dskPercent ::= { dskEntry 9 }
Cannot adopt OID in UCD-SNMP-MIB: dskUsed ::= { dskEntry 8 }
Cannot adopt OID in UCD-SNMP-MIB: dskAvail ::= { dskEntry 7 }
Cannot adopt OID in UCD-SNMP-MIB: dskTotal ::= { dskEntry 6 }
Cannot adopt OID in UCD-SNMP-MIB: dskMinPercent ::= { dskEntry 5 }
Cannot adopt OID in UCD-SNMP-MIB: dskMinimum ::= { dskEntry 4 }
Cannot adopt OID in UCD-SNMP-MIB: dskDevice ::= { dskEntry 3 }
Cannot adopt OID in UCD-SNMP-MIB: dskPath ::= { dskEntry 2 }
Cannot adopt OID in UCD-SNMP-MIB: dskIndex ::= { dskEntry 1 }
Cannot adopt OID in UCD-DISKIO-MIB: diskIOTable ::= { ucdDiskIOMIB 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsLoggingGroup ::= { nsConfigGroups 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsDebugGroup ::= { nsConfigGroups 1 }
Cannot adopt OID in UCD-SNMP-MIB: snmperrErrMessage ::= { snmperrs 101 }
Cannot adopt OID in UCD-SNMP-MIB: snmperrErrorFlag ::= { snmperrs 100 }
Cannot adopt OID in UCD-SNMP-MIB: snmperrNames ::= { snmperrs 2 }
Cannot adopt OID in UCD-SNMP-MIB: snmperrIndex ::= { snmperrs 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsTransactionTable ::= { nsTransactions 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsLogStatus ::= { nsLoggingEntry 5 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsLogMaxLevel ::= { nsLoggingEntry 4 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsLogType ::= { nsLoggingEntry 3 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsLogToken ::= { nsLoggingEntry 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsLogLevel ::= { nsLoggingEntry 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendResult ::= { nsExtendOutput1Entry 4 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendOutNumLines ::= { nsExtendOutput1Entry 3 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendOutputFull ::= { nsExtendOutput1Entry 2 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendOutput1Line ::= { nsExtendOutput1Entry 1 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendOutLine ::= { nsExtendOutput2Entry 2 }
Cannot adopt OID in NET-SNMP-EXTEND-MIB: nsExtendLineIndex ::= { nsExtendOutput2Entry 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsNotifyStart ::= { netSnmpNotifications 1 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsNotifyShutdown ::= { netSnmpNotifications 2 }
Cannot adopt OID in NET-SNMP-AGENT-MIB: nsNotifyRestart ::= { netSnmpNotifications 3 }
Cannot adopt OID in UCD-SNMP-MIB: laErrMessage ::= { laEntry 101 }
Cannot adopt OID in UCD-SNMP-MIB: laErrorFlag ::= { laEntry 100 }
Cannot adopt OID in UCD-SNMP-MIB: laLoadFloat ::= { laEntry 6 }
Cannot adopt OID in UCD-SNMP-MIB: laLoadInt ::= { laEntry 5 }
Cannot adopt OID in UCD-SNMP-MIB: laConfig ::= { laEntry 4 }
Cannot adopt OID in UCD-SNMP-MIB: laLoad ::= { laEntry 3 }
Cannot adopt OID in UCD-SNMP-MIB: laNames ::= { laEntry 2 }
Cannot adopt OID in UCD-SNMP-MIB: laIndex ::= { laEntry 1 }
Warning: Failed to connect to the agentx master agent ([NIL]): 
Killed
```

***

**snmpbulkget**

Communicates with a network entity using SNMP GETBULK requests.

```
:~# snmpbulkget -h
USAGE: snmpbulkget [OPTIONS] AGENT OID [OID]...

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviours:
			  n<NUM>:  set non-repeaters to <NUM>
			  r<NUM>:  set max-repeaters to <NUM>
```

***

**snmpbulkwalk**

Retrieve a subtree of management values using SNMP GETBULK requests

```
:~# snmpbulkwalk -h
USAGE: snmpbulkwalk [OPTIONS] AGENT [OID]

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviours:
			  c:       do not check returned OIDs are increasing
			  i:       include given OIDs in the search range
			  n<NUM>:  set non-repeaters to <NUM>
			  p:       print the number of variables found
			  r<NUM>:  set max-repeaters to <NUM>
```

***

**snmpcheck**

Check hosts SNMP access

```
:~# man snmpcheck
snmpcheck(1)                       Net-SNMP                       snmpcheck(1)

NAME
       snmpcheck - check hosts SNMP access

SYNOPSIS
       snmpcheck [options] [[-a] HOSTS]...

DESCRIPTION
       snmpcheck  is  a  program  that checks the SNMP status of the specified
       hosts

OPTIONS
   Common Options
       -h     Display this message.

       -a     check error log file AND hosts specified on command line.

       -p     Don't try and ping-echo the host first

       -f     Only check for things I can fix

       HOSTS  check these hosts for problems.

   X Options:
       -x     forces ascii base if $DISPLAY set (instead of tk).

       -H     start in hidden mode.  (hides user interface)

       -V NUM sets the initial verbosity level of the command log (def: 1)

       -L     Show the log window at startup

       -d     Don't start by checking anything.  Just bring up the interface.

   Ascii Options:
       -n     Don't ever try and fix the problems found.  Just list.

       -y     Always fix problems found.

V5.7.3                            2018-03-30                      snmpcheck(1)
```

***

**snmpconf**

Creates and modifies SNMP configuration files

```
:~# snmpconf -h
/usr/bin/snmpconf [options] [FILETOCREATE...]
options:
  -f           overwrite existing files without prompting
  -i           install created files into /usr/share/snmp.
  -p           install created files into /root/.snmp.
  -I DIR       install created files into DIR.
  -a           Don't ask any questions, just read in current
                   current .conf files and comment them
  -r all|none  Read in all or none of the .conf files found.
  -R file,...  Read in a particular list of .conf files.
  -g GROUP     Ask a series of GROUPed questions.
  -G           List known GROUPs.
  -c conf_dir  use alternate configuration directory.
  -q           run more quietly with less advice.
  -d           turn on debugging output.
  -D           turn on debugging dumper output.
```

***

**snmpdelta**

Monitor delta differences in SNMP Counter values

```
:~# snmpdelta -h
Usage: snmpdelta [-Cf] [-CF commandFile] [-Cl] [-CL SumFileName]
	[-Cs] [-Ck] [-Ct] [-CS] [-Cv vars/pkt] [-Cp period]
	[-CP peaks] [OPTIONS] AGENT oid [oid ...]
  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
snmpdelta specific options
  -Cf		Don't fix errors and retry the request.
  -Cl		write configuration to file
  -CF config	load configuration from file
  -Cp period	specifies the poll period
  -CP peaks	reporting period in poll periods
  -Cv vars/pkt	number of variables per packet
  -Ck		keep seconds in output time
  -Cm		show max values
  -CS		log to a sum file
  -Cs		show timestamps
  -Ct		get timing from agent
  -CT		print output in tabular form
  -CL sumfile	specifies the sum file name
```

***

**snmpdf**

Display disk space usage on a network entity via SNMP

```
:~# snmpdf -h
Usage: snmpdf [-Cu] [OPTIONS] AGENT

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'

snmpdf options:
	-Cu	Use UCD-SNMP dskTable to do the calculations.
		[Normally the HOST-RESOURCES-MIB is consulted first.]
	-Ch	Print using human readable format (MiB, GiB, TiB)
	-CH	Print using human readable SI format (MB, GB, TB)
```

***

**snmpget**

Communicates with a network entity using SNMP GET requests

```
:~# snmpget -h
USAGE: snmpget [OPTIONS] AGENT OID [OID]...

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviours:
			  f:  do not fix errors and retry the request
```

***

**snmpgetnext**

Communicates with a network entity using SNMP GETNEXT requests

```
:~# snmpgetnext -h
USAGE: snmpgetnext [OPTIONS] AGENT OID [OID]...

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviours:
			  f:  do not fix errors and retry the request
```

***

**snmpinform**

Sends an SNMP notification to a manager

```
:~# snmpinform -h
USAGE: snmpinform [OPTIONS] AGENT TRAP-PARAMETERS

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviour:
			  i:  send an INFORM instead of a TRAP

  -v 1 TRAP-PARAMETERS:
	 enterprise-oid agent trap-type specific-type uptime [OID TYPE VALUE]...
  or
  -v 2 TRAP-PARAMETERS:
	 uptime trapoid [OID TYPE VALUE] ...
```

***

**snmpnetstat**

Display networking status and configuration information from a network entity via SNMP

```
:~# snmpnetstat -h
usage: snmpnetstat [snmp_opts] [-Canv] [-Cf address_family]
       snmpnetstat [snmp_opts] [-Cibodnv] [-CI interface] [-Cw wait]
       snmpnetstat [snmp_opts] [-Cs[s]] [-Cp protocol]
       snmpnetstat [snmp_opts] [-Crnv] [-Cf address_family]
```

***

**snmpping**

Command an agent to ping a remote host

```
:~# snmpping -h
Usage: snmpping [OPTIONS] AGENT DESTINATION

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'

snmpping options:
	-Cc<pings>	Specify the number of pings (1-15)
	-Cs<size>	Specify the amount of extra data (0-65507)
```

***

**snmpset**

Communicates with a network entity using SNMP SET requests

```
:~# snmpset -h
USAGE: snmpset [OPTIONS] AGENT OID TYPE VALUE [OID TYPE VALUE]...

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviours:
			  q:  don't print results on success

  TYPE: one of i, u, t, a, o, s, x, d, b
	i: INTEGER, u: unsigned INTEGER, t: TIMETICKS, a: IPADDRESS
	o: OBJID, s: STRING, x: HEX STRING, d: DECIMAL STRING, b: BITS
	U: unsigned int64, I: signed int64, F: float, D: double
```

***

**snmpstatus**

Retrieves a fixed set of management information from a network entity

```
:~# snmpstatus -h
USAGE: snmpstatus [OPTIONS] AGENT

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviours:
			  f:  do not fix errors and retry the request
```

***

**snmptable**

Retrieve an SNMP table and display it in tabular form

```
:~# snmptable -h
USAGE: snmptable [OPTIONS] AGENT TABLE-OID

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviours:
			  b:       brief field names
			  B:       do not use GETBULK requests
			  c<NUM>:  print table in columns of <NUM> chars width
			  f<STR>:  print table delimitied with <STR>
			  h:       print only the column headers
			  H:       print no column headers
			  i:       print index values
			  l:       left justify output
			  r<NUM>:  for GETBULK: set max-repeaters to <NUM>
			           for GETNEXT: retrieve <NUM> entries at a time
			  w<NUM>:  print table in parts of <NUM> chars width
```

***

**snmptest**

Communicates with a network entity using SNMP requests

```
:~# snmptest -h
USAGE: snmptest [OPTIONS] AGENT

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
```

***

**snmptls**

```
:~# snmptls -h
USAGE: snmptls [-Cm mapTypeOID] [-Cd data] [-Cs storageType] [OPTIONS] AGENT<command> [command options]

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  [options]   certToSecName add <priority> <hashType> <fingerprint>
	-Cm		Maptype; [snmpTlstmCertCommonName|snmpTlstmCertSANRFC822Name|snmpTlstmCertSANIpAddress|snmpTlstmCertSANDNSName|snmpTlstmCertSpecified]
			(default is snmpTlstmCertSpecified)
	-Cd		Data; data for snmpTlstmCertSpecified.
	-Cs		storageType; default is nonVolatile.
  [options]   targetParamsFingerprint add <params-name> <hashType> <fingerprint>
	-Cs		storageType; default is nonVolatile.
  [options]   targetAddr add <target-name> <hashType> [<hash_type> <remote-fingerprint>] [server-identity]
	-Cs		storageType; default is nonVolatile.
```

***

**snmptranslate**

Translate MIB OID names between numeric and textual forms

```
:~# snmptranslate --help
snmptranslate: invalid option -- '-'
invalid option: -?
USAGE: snmptranslate [OPTIONS] OID [OID]...

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h			display this help message
  -V			display package version number
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
  -w WIDTH		set width of tree and detail output
  -T TRANSOPTS		Set various options controlling report produced:
			  B:  print all matching objects for a regex search
			  d:  print full details of the given OID
			  p:  print tree format symbol table
			  a:  print ASCII format symbol table
			  l:  enable labeled OID report
			  o:  enable OID report
			  s:  enable dotted symbolic report
			  z:  enable MIB child OID report
			  t:  enable alternate format symbolic suffix report
  -P MIBOPTS		Toggle various defaults controlling mib parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
```

***

**snmptrap**

Sends an SNMP notification to a manager

```
:~# snmptrap -h
USAGE: snmptrap [OPTIONS] AGENT TRAP-PARAMETERS

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviour:
			  i:  send an INFORM instead of a TRAP

  -v 1 TRAP-PARAMETERS:
	 enterprise-oid agent trap-type specific-type uptime [OID TYPE VALUE]...
  or
  -v 2 TRAP-PARAMETERS:
	 uptime trapoid [OID TYPE VALUE] ...
```

***

**snmpusm**

Creates and maintains SNMPv3 users on a network entity

```
:~# snmpusm -h
Usage: snmpusm [OPTIONS] AGENT COMMAND

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'

snmpusm commands:
  [options]               create     USER [CLONEFROM-USER]
  [options]               delete     USER
  [options]               activate   USER
  [options]               deactivate USER
  [options] [-Cw]         cloneFrom  USER CLONEFROM-USER
  [options] [-Ca] [-Cx]   changekey  [USER]
  [options] [-Ca] [-Cx]   passwd     OLD-PASSPHRASE NEW-PASSPHRASE [USER]
  [options] (-Ca|-Cx) -Ck passwd     OLD-KEY-OR-PASS NEW-KEY-OR-PASS [USER]

snmpusm options:
	-CE ENGINE-ID	Set usmUserEngineID (e.g. 800000020109840301).
	-Cp STRING	Set usmUserPublic value to STRING.
	-Cw		Create the user with createAndWait.
			(it won't be active until you active it)
	-Cx		Change the privacy key.
	-Ca		Change the authentication key.
	-Ck		Allows one to use localized key (must start with 0x)
			instead of passphrase.
```

***

**snmpvacm**

Creates and maintains SNMPv3 View-based Access Control entries on a network entity

```
:~# snmpvacm -h
Usage: snmpvacm [OPTIONS] AGENT COMMAND

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'

snmpvacm commands:
        createAccess     GROUPNAME [CONTEXTPREFIX] SECURITYMODEL SECURITYLEVEL CONTEXTMATCH READVIEWNAME WRITEVIEWNAME NOTIFYVIEWNAME
        deleteAccess     GROUPNAME [CONTEXTPREFIX] SECURITYMODEL SECURITYLEVEL
        createSec2Group  MODEL SECURITYNAME  GROUPNAME
        deleteSec2Group  MODEL SECURITYNAME
  [-Ce] createView       NAME SUBTREE [MASK]
        deleteView       NAME SUBTREE
        createAuth       GROUPNAME [CONTEXTPREFIX] SECURITYMODEL SECURITYLEVEL AUTHTYPE CONTEXTMATCH VIEWNAME
        deleteAuth       GROUPNAME [CONTEXTPREFIX] SECURITYMODEL SECURITYLEVEL AUTHTYPE
```

***

**snmpwalk**

Retrieve a subtree of management values using SNMP GETNEXT requests

```
:~# snmpwalk -h
USAGE: snmpwalk [OPTIONS] AGENT [OID]

  Version:  5.9.3
  Web:      http://www.net-snmp.org/
  Email:    

OPTIONS:
  -h, --help		display this help message
  -H			display configuration file directives understood
  -v 1|2c|3		specifies SNMP version to use
  -V, --version		display package version number
SNMP Version 1 or 2c specific
  -c COMMUNITY		set the community string
SNMP Version 3 specific
  -a PROTOCOL		set authentication protocol (MD5|SHA|SHA-224|SHA-256|SHA-384|SHA-512)
  -A PASSPHRASE		set authentication protocol pass phrase
  -e ENGINE-ID		set security engine ID (e.g. 800000020109840301)
  -E ENGINE-ID		set context engine ID (e.g. 800000020109840301)
  -l LEVEL		set security level (noAuthNoPriv|authNoPriv|authPriv)
  -n CONTEXT		set context name (e.g. bridge1)
  -u USER-NAME		set security name (e.g. bert)
  -x PROTOCOL		set privacy protocol (DES|AES|AES-192|AES-256)
  -X PASSPHRASE		set privacy protocol pass phrase
  -Z BOOTS,TIME		set destination engine boots/time
General communication options
  -r RETRIES		set the number of retries
  -t TIMEOUT		set the request timeout (in seconds)
Debugging
  -d			dump input/output packets in hexadecimal
  -D[TOKEN[,...]]	turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
General options
  -m MIB[:...]		load given list of MIBs (ALL loads everything)
  -M DIR[:...]		look in given list of directories for MIBs
    (default: $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -P MIBOPTS		Toggle various defaults controlling MIB parsing:
			  u:  allow the use of underlines in MIB symbols
			  c:  disallow the use of "--" to terminate comments
			  d:  save the DESCRIPTIONs of the MIB objects
			  e:  disable errors when MIB symbols conflict
			  w:  enable warnings when MIB symbols conflict
			  W:  enable detailed warnings when MIB symbols conflict
			  R:  replace MIB symbols from latest module
  -O OUTOPTS		Toggle various defaults controlling output display:
			  0:  print leading 0 for single-digit hex characters
			  a:  print all strings in ascii format
			  b:  do not break OID indexes down
			  e:  print enums numerically
			  E:  escape quotes in string indices
			  f:  print full OIDs on output
			  n:  print OIDs numerically
			  p PRECISION:  display floating point values with specified PRECISION (printf format string)
			  q:  quick print for easier parsing
			  Q:  quick print with equal-signs
			  s:  print only last symbolic element of OID
			  S:  print MIB module-id plus last element
			  t:  print timeticks unparsed as numeric integers
			  T:  print human-readable text along with hex strings
			  u:  print OIDs using UCD-style prefix suppression
			  U:  don't print units
			  v:  print values only (not OID = value)
			  x:  print all strings in hex format
			  X:  extended index format
  -I INOPTS		Toggle various defaults controlling input parsing:
			  b:  do best/regex matching to find a MIB node
			  h:  don't apply DISPLAY-HINTs
			  r:  do not check values for range/type legality
			  R:  do random access to OID labels
			  u:  top-level OIDs must have '.' prefix (UCD-style)
			  s SUFFIX:  Append all textual OIDs with SUFFIX before parsing
			  S PREFIX:  Prepend all textual OIDs with PREFIX before parsing
  -L LOGOPTS		Toggle various defaults controlling logging:
			  e:           log to standard error
			  o:           log to standard output
			  n:           don't log at all
			  f file:      log to the specified file
			  s facility:  log to syslog (via the specified facility)

			  (variants)
			  [EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			  [EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			  [FS] pri token:    log to file/syslog for level 'pri' and above
			  [FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -C APPOPTS		Set various application specific behaviours:
			  p:  print the number of variables found
			  i:  include given OID in the search range
			  I:  don't include the given OID, even if no results are returned
			  c:  do not check returned OIDs are increasing
			  t:  Display wall-clock time to complete the walk
			  T:  Display wall-clock time to complete each request
			  E {OID}:  End the walk at the specified OID
```

***

#### snmpd <a href="#snmpd" id="snmpd"></a>

The Simple Network Management Protocol (SNMP) provides a framework for the exchange of management information between agents (servers) and clients.

The Net-SNMP agent is a daemon which listens for incoming SNMP requests from clients and provides responses.

**Installed size:** `147 KB`\
**How to install:** `sudo apt install snmpd`

<details>

<summary>Dependencies:</summary>

* adduser
* debconf
* debconf | debconf-2.0
* init-system-helpers
* libc6
* libsnmp-base
* libsnmp40
* lsb-base

</details>

**net-snmp-create-v3-user**

Create a SNMPv3 user in net-snmp configuration file

```
:~# net-snmp-create-v3-user -h
unknown suboption to /usr/bin/net-snmp-create-v3-user: -h

Usage:
  net-snmp-create-v3-user [-ro] [-A authpass] [-X privpass]
                          [-a MD5|SHA|SHA-512|SHA-384|SHA-256|SHA-224] [-x DES|AES] [username]

```

***

**snmpd**

Daemon to respond to SNMP request packets.

```
:~# snmpd -h

Usage:  snmpd [OPTIONS] [LISTENING ADDRESSES]

	Version:  5.9.3
	Web:      http://www.net-snmp.org/
	Email:    

  -a			log addresses
  -A			append to the logfile rather than truncating it
  -c FILE[,...]		read FILE(s) as configuration file(s)
  -C			do not read the default configuration files
			  (config search path: /etc/snmp:/usr/share/snmp:/usr/lib/x86_64-linux-gnu/snmp:/root/.snmp)
  -d			dump sent and received SNMP packets
  -D[TOKEN[,...]]	turn on debugging output for the given TOKEN(s)
			  (try ALL for extremely verbose output)
			  Don't put space(s) between -D and TOKEN(s).
  -f			do not fork from the shell
  -g GID		change to this numeric gid after opening
			  transport endpoints
  -h, --help		display this usage message
  -H			display configuration file directives understood
  -I [-]INITLIST	list of mib modules to initialize (or not)
			  (run snmpd with -Dmib_init for a list)
  -L <LOGOPTS>		toggle options controlling where to log to
	e:           log to standard error
	o:           log to standard output
	n:           don't log at all
	f file:      log to the specified file
	s facility:  log to syslog (via the specified facility)

	(variants)
	[EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
	[EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
	[FS] pri token:    log to file/syslog for level 'pri' and above
	[FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
  -m MIBLIST		use MIBLIST instead of the default MIB list
  -M DIRLIST		use DIRLIST as the list of locations to look for MIBs
			  (default $HOME/.snmp/mibs:/usr/share/snmp/mibs:/usr/share/snmp/mibs/iana:/usr/share/snmp/mibs/ietf)
  -p FILE		store process id in FILE
  -q			print information in a more parsable format
  -r			do not exit if files only accessible to root
			  cannot be opened
  -u UID		change to this uid (numeric or textual) after
			  opening transport endpoints
  -v, --version		display version information
  -V			verbose display
  -x ADDRESS		use ADDRESS as AgentX address
  -X			run as an AgentX subagent rather than as an
			  SNMP master agent

Deprecated options:
  -l FILE		use -Lf <FILE> instead
  -P			use -p instead
  -s			use -Lsd instead
  -S d|i|0-7		use -Ls <facility> instead

```

***

#### snmptrapd <a href="#snmptrapd" id="snmptrapd"></a>

The Simple Network Management Protocol (SNMP) provides a framework for the exchange of management information between agents (servers) and clients.

snmptrapd is an SNMP application (daemon) that receives and logs SNMP TRAP and INFORM messages.

**Installed size:** `91 KB`\
**How to install:** `sudo apt install snmptrapd`

<details>

<summary>Dependencies:</summary>

* init-system-helpers
* libc6
* libnetsnmptrapd40
* libsnmp40
* libwrap0
* snmpd

</details>

**snmptrapd**

Receive and log SNMP trap messages.

```
:~# snmptrapd -h
Usage: snmptrapd [OPTIONS] [LISTENING ADDRESSES]

	NET-SNMP Version:  5.9.3
	Web:      http://www.net-snmp.org/
	Email:    

  -a			ignore authentication failure traps
  -A			append to log file rather than truncating it
  -c FILE		read FILE as a configuration file
  -C			do not read the default configuration files
  -d			dump sent and received SNMP packets
  -D[TOKEN[,...]]		turn on debugging output for the specified TOKENs
			   (ALL gives extremely verbose debugging output)
  -f			do not fork from the shell
  -F FORMAT		use specified format for logging to standard error
  -g GID		change to this numeric gid after opening
			  transport endpoints
  -h, --help		display this usage message
  -H			display configuration file directives understood
  -m MIBLIST		use MIBLIST instead of the default MIB list
  -M DIRLIST		use DIRLIST as the list of locations
			  to look for MIBs
  -n			use numeric addresses instead of attempting
			  hostname lookups (no DNS)
  -p FILE		store process id in FILE
  -t			Prevent traps from being logged to syslog
  -u UID		change to this uid (numeric or textual) after
			  opening transport endpoints
  -v, --version		display version information
  -x ADDRESS		use ADDRESS as AgentX address
  -X			don't become a subagent
  -O <OUTOPTS>		toggle options controlling output display
			0:  print leading 0 for single-digit hex characters
			a:  print all strings in ascii format
			b:  do not break OID indexes down
			e:  print enums numerically
			E:  escape quotes in string indices
			f:  print full OIDs on output
			n:  print OIDs numerically
			p PRECISION:  display floating point values with specified PRECISION (printf format string)
			q:  quick print for easier parsing
			Q:  quick print with equal-signs
			s:  print only last symbolic element of OID
			S:  print MIB module-id plus last element
			t:  print timeticks unparsed as numeric integers
			T:  print human-readable text along with hex strings
			u:  print OIDs using UCD-style prefix suppression
			U:  don't print units
			v:  print values only (not OID = value)
			x:  print all strings in hex format
			X:  extended index format
  -L <LOGOPTS>		toggle options controlling where to log to
			e:           log to standard error
			o:           log to standard output
			n:           don't log at all
			f file:      log to the specified file
			s facility:  log to syslog (via the specified facility)

			(variants)
			[EON] pri:   log to standard error, output or /dev/null for level 'pri' and above
			[EON] p1-p2: log to standard error, output or /dev/null for levels 'p1' to 'p2'
			[FS] pri token:    log to file/syslog for level 'pri' and above
			[FS] p1-p2 token:  log to file/syslog for levels 'p1' to 'p2'
```

***

**traptoemail**

Snmptrapd handler script to convert snmp traps into emails

```
:~# traptoemail -h

traptoemail [-s smtpserver] [-f fromaddress] toaddress [...]

  traptoemail shouldn't be called interatively by a user.  It is
  designed to be called as an snmptrapd extension via a "traphandle"
  directive in the snmptrapd.conf file.  See the snmptrapd.conf file for
  details.

  Options:
    -s smtpserver      Sets the smtpserver for where to send the mail through.
    -f fromaddress     Sets the email address to be used on the From: line.
    toaddress          Where you want the email sent to.

```

***

#### tkmib <a href="#tkmib" id="tkmib"></a>

The Simple Network Management Protocol (SNMP) provides a framework for the exchange of management information between agents (servers) and clients.

The Net-SNMP MIB (Management Information Base) Browser provides a graphical frontend for the Net-SNMP tools. It can be used to browse the MIB tree and interactively send requests to SNMP agents.

**Installed size:** `1.61 MB`\
**How to install:** `sudo apt install tkmib`

<details>

<summary>Dependencies:</summary>

* libsnmp-perl
* perl-tk

</details>

**tkmib**

An interactive graphical MIB browser for SNMP

```
:~# tkmib -h
setting opts

tkmib [-C] [-o OID] [SNMPCMD arguments] [host]
  -f CONFIG_FILE  load CONFIG_FILE after starting up. (default: ~/.snmp/tkmibrc)
                  (use -f /dev/null to not read one).

  See the snmpcmd manual page for related SNMPCMD arguments.  (Not all
  options are currently supported.)
```

***
