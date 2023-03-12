---
description: >-
  FreeRADIUS is an open-source security tool that provides centralized
  authentication and authorization for network devices and applications.
---

# 🌐 freeradius

FreeRADIUS is an open-source, high-performance, and highly configurable RADIUS server. It is used for centralized authentication, authorization, and accounting for network devices and services. With support for a wide range of authentication methods, including username and password, certificates, and smart cards, FreeRADIUS can authenticate users and devices against a variety of backend databases, such as MySQL, PostgreSQL, and LDAP.

FreeRADIUS also offers extensive logging and reporting capabilities, making it easy to monitor and troubleshoot network access issues. It can be integrated with various network devices, such as switches, routers, and firewalls, to provide granular access control and accounting. FreeRADIUS is highly scalable and can handle thousands of simultaneous connections, making it suitable for large enterprise deployments.

The server is highly customizable, and administrators can configure it to enforce different policies for different user groups or devices. Additionally, FreeRADIUS offers a range of advanced features, such as dynamic VLAN assignment, WPA2-Enterprise authentication, and network access control, making it a versatile tool for securing and managing network access.

FreeRADIUS is widely used in various industries, including telecommunications, education, healthcare, and government, as a highly reliable and cost-effective solution for securing network access. With its extensive documentation and active community support, FreeRADIUS is a popular choice for organizations looking to implement a robust and flexible RADIUS solution.

#### freeradius <a href="#freeradius" id="freeradius"></a>

FreeRADIUS is a high-performance RADIUS server with support for:

* Authentication by local files, SQL, Kerberos, LDAP, PAM, and more.
* Powerful policy configuration language.
* Proxying and replicating requests by any criteria.
* Support for many EAP types; TLS, PEAP, TTLS, etc.
* Many vendor-specific attributes.
* Regexp matching in string attributes. and lots more.

**Installed size:** `2.33 MB`\
**How to install:** `sudo apt install freeradius`

<details>

<summary>Dependencies:</summary>

* freeradius-common
* freeradius-config
* libc6
* libcrypt1
* libct4
* libfreeradius3
* libgdbm6
* libjson-c5
* libpam0g
* libperl5.36
* libreadline8
* libsqlite3-0
* libssl3
* libsystemd0
* libtalloc2
* libwbclient0
* lsb-base

</details>

**checkrad**

See if a user is (still) logged in on a certain port.

```
:~# checkrad -h
Usage: checkrad nas_type nas_ip nas_port login session_id
```

***

**freeradius**

Authentication, Authorization and Accounting server

```
:~# freeradius -h
Usage: freeradius [options]
Options:
  -C            Check configuration and exit.
  -f            Run as a foreground process, not a daemon.
  -h            Print this help message.
  -i <ipaddr>   Listen on ipaddr ONLY.
  -l <log_file> Logging output will be written to this file.
  -m            On SIGINT or SIGQUIT clean up all used memory instead of just exiting.
  -n <name>     Read raddb/name.conf instead of raddb/radiusd.conf.
  -p <port>     Listen on port ONLY.
  -P            Always write out PID, even with -f.
  -s            Do not spawn child processes to handle requests (same as -ft).
  -t            Disable threads.
  -v            Print server version information.
  -X            Turn on full debugging (similar to -tfxxl stdout).
  -x            Turn on additional debugging (-xx gives more debugging).
```

***

**rad\_counter**

Query and maintain FreeRADIUS rlm\_counter DB file.

```
:~# rad_counter -h
Usage: rad_counter --file=<counter filename> [OPTION...]
Query and maintain FreeRADIUS rlm_counter DB file.

Arguments:
--file=<filename>               Counter DB filename.

Options:
--user=<username>               Information for specific user.
--match=<regexp>                Information for matching users.
--reset=<number>                Reset counter to <number>.
                                If divisor is set use it,
                                else <number> means seconds.
--help                          Show this help screen.
--(hours|minutes|seconds)       Specify information divisor.
```

***

**raddebug**

Display debugging output from a running server.

```
:~# raddebug -h
Illegal option -h
Usage: raddebug: [-c condition] [-d directory] [-n name] [-D dictdir]  [-i client-ip-address] [-I client-ipv6-address] [-f socket_file] [-t timeout] [-u user]
```

***

**radmin**

FreeRADIUS Administration tool

```
:~# radmin -h
Usage: radmin [ args ]
  -d raddb_dir    Configuration files are in "raddbdir/*".
  -D <dictdir>    Set main dictionary directory (defaults to /usr/share/freeradius).
  -e command      Execute 'command' and then exit.
  -E              Echo commands as they are being executed.
  -f socket_file  Open socket_file directly, without reading radius.conf
  -h              Print usage help information.
  -i input_file   Read commands from 'input_file'.
  -n name         Read raddb/name.conf instead of raddb/radiusd.conf
  -q              Quiet mode.
  -v              Show program version information.
```

***

**rlm\_sqlippool\_tool**

Manage SQL IP pools

```
:~# rlm_sqlippool_tool -h
Usage:
  rlm_sqlippool_tool -p <pool_name> -s <range_start> -e <range_end> -t <table_name> (-d <sql_dialect> | -f <raddb_dir> [ -i <instance> ]) [ -c <capacity> ] [ -x <existing_ips_file> ]
or:
  rlm_sqlippool_tool -y <pool_defs_yaml_file> -t <table_name> (-d <dialect> | -f <raddb_dir> [ -i <instance> ]) [ -x <existing_ips_file> ]

```

***

#### freeradius-common <a href="#freeradius-common" id="freeradius-common"></a>

This package contains common files used by several of the other packages from the FreeRADIUS project.

**Installed size:** `1.22 MB`\
**How to install:** `sudo apt install freeradius-common`

<details>

<summary>Dependencies:</summary>

* adduser

</details>

***

#### freeradius-config <a href="#freeradius-config" id="freeradius-config"></a>

freeradius-config contains the default configuration for FreeRADIUS.

You can install a custom package which sets “Provides: freeradius-config” in order to use the FreeRADIUS packages without any default configuration getting into your way.

**Installed size:** `1.19 MB`\
**How to install:** `sudo apt install freeradius-config`

<details>

<summary>Dependencies:</summary>

* adduser
* ca-certificates
* freeradius-common
* make
* openssl
* ssl-cert

</details>

***

#### freeradius-dhcp <a href="#freeradius-dhcp" id="freeradius-dhcp"></a>

The FreeRADIUS server can act as a DHCP server, and this module is necessary for that.

**Installed size:** `98 KB`\
**How to install:** `sudo apt install freeradius-dhcp`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6

</details>

***

#### freeradius-iodbc <a href="#freeradius-iodbc" id="freeradius-iodbc"></a>

The FreeRADIUS server can use iODBC to access databases to authenticate users and do accounting, and this module is necessary for that.

**Installed size:** `41 KB`\
**How to install:** `sudo apt install freeradius-iodbc`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libiodbc2

</details>

***

#### freeradius-krb5 <a href="#freeradius-krb5" id="freeradius-krb5"></a>

The FreeRADIUS server can use Kerberos to authenticate users, and this module is necessary for that.

**Installed size:** `47 KB`\
**How to install:** `sudo apt install freeradius-krb5`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libcom-err2
* libkrb5-3

</details>

***

#### freeradius-ldap <a href="#freeradius-ldap" id="freeradius-ldap"></a>

The FreeRADIUS server can use LDAP to authenticate users, and this module is necessary for that.

**Installed size:** `125 KB`\
**How to install:** `sudo apt install freeradius-ldap`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libldap-2.5-0

</details>

***

#### freeradius-memcached <a href="#freeradius-memcached" id="freeradius-memcached"></a>

The FreeRADIUS server can cache data in memcached and this package contains the required module.

**Installed size:** `51 KB`\
**How to install:** `sudo apt install freeradius-memcached`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libmemcached11

</details>

***

#### freeradius-mysql <a href="#freeradius-mysql" id="freeradius-mysql"></a>

The FreeRADIUS server can use MySQL to authenticate users and do accounting, and this module is necessary for that.

**Installed size:** `51 KB`\
**How to install:** `sudo apt install freeradius-mysql`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libmariadb3

</details>

***

#### freeradius-postgresql <a href="#freeradius-postgresql" id="freeradius-postgresql"></a>

The FreeRADIUS server can use PostgreSQL to authenticate users and do accounting, and this module is necessary for that.

**Installed size:** `70 KB`\
**How to install:** `sudo apt install freeradius-postgresql`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libpq5

</details>

***

#### freeradius-python3 <a href="#freeradius-python3" id="freeradius-python3"></a>

This package is required to add Python 3 functionality to the FreeRADIUS server.

It was introduced in FreeRADIUS 3.0.20 as EXPERIMENTAL module. Use at your own risk.

**Installed size:** `64 KB`\
**How to install:** `sudo apt install freeradius-python3`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libpython3.11

</details>

***

#### freeradius-redis <a href="#freeradius-redis" id="freeradius-redis"></a>

This module is required to enable the FreeRADIUS server to access Redis databases.

**Installed size:** `54 KB`\
**How to install:** `sudo apt install freeradius-redis`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libhiredis0.14

</details>

***

#### freeradius-rest <a href="#freeradius-rest" id="freeradius-rest"></a>

The FreeRADIUS server can make calls to remote web APIs, and this module is necessary for that.

**Installed size:** `79 KB`\
**How to install:** `sudo apt install freeradius-rest`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libcurl4
* libjson-c5

</details>

***

#### freeradius-utils <a href="#freeradius-utils" id="freeradius-utils"></a>

This package contains various client programs and utilities from the FreeRADIUS Server project, including:

* radclient
* radeapclient
* radlast
* radsniff
* radsqlrelay
* radtest
* radwho
* radzap
* rlm\_ippool\_tool
* smbencrypt

**Installed size:** `362 KB`\
**How to install:** `sudo apt install freeradius-utils`

<details>

<summary>Dependencies:</summary>

* freeradius-common
* freeradius-config
* libc6
* libfreeradius3
* libgdbm6
* libpcap0.8
* libpcre3
* libssl3
* libtalloc2

</details>

**radclient**

Send packets to a RADIUS server, show reply

```
:~# radclient --help
radclient: invalid option -- '-'
Usage: radclient [options] server[:port] <command> [<secret>]
  <command>              One of auth, acct, status, coa, disconnect or auto.
  -4                     Use IPv4 address of server
  -6                     Use IPv6 address of server.
  -c <count>             Send each packet 'count' times.
  -d <raddb>             Set user dictionary directory (defaults to /etc/freeradius/3.0).
  -D <dictdir>           Set main dictionary directory (defaults to /usr/share/freeradius).
  -f <file>[:<file>]     Read packets from file, not stdin.
                         If a second file is provided, it will be used to verify responses
  -F                     Print the file name, packet number and reply code.
  -h                     Print usage help information.
  -n <num>               Send N requests/s
  -p <num>               Send 'num' packets from a file in parallel.
  -q                     Do not print anything out.
  -r <retries>           If timeout, retry sending the packet 'retries' times.
  -s                     Print out summary information of auth results.
  -S <file>              read secret from file, not command line.
  -t <timeout>           Wait 'timeout' seconds before retrying (may be a floating point number).
  -v                     Show program version information.
  -x                     Debugging mode.
  -P <proto>             Use proto (tcp or udp) for transport.
```

***

**radcrypt**

Generate password hash for use with radius, or validates a password hash

```
:~# radcrypt -h
Unknown option: h
Usage: radcrypt [--des|--md5|--check] plaintext_password [crypted_password]
```

***

**radeapclient**

Send EAP packets to a RADIUS server, calculate responses

```
:~# radeapclient -h
Usage: radeapclient [options] server[:port] <command> [<secret>]
  <command>              One of auth, acct, status, coa, disconnect or auto.
  -4                     Use IPv4 address of server
  -6                     Use IPv6 address of server.
  -d <raddb>             Set user dictionary directory (defaults to /etc/freeradius/3.0).
  -D <dictdir>           Set main dictionary directory (defaults to /usr/share/freeradius).
  -f <file>              Read packets from file, not stdin.
  -h                     Print usage help information.
  -p <num>               Send 'num' packets in parallel.
  -q                     Do not print anything out.
  -r <retries>           If timeout, retry sending the packet 'retries' times.
  -s                     Print out summary information of auth results.
  -S <file>              read secret from file, not command line.
  -t <timeout>           Wait 'timeout' seconds before retrying (may be a floating point number).
  -v                     Show program version information.
  -x                     Debugging mode.
```

***

**radlast**

Show “last” info from the radwtmp file

```
:~# radlast -h

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

**radsniff**

Dump radius protocol

```
:~# radsniff -h
Usage: radsniff [options][stats options] -- [pcap files]
options:
  -a                    List all interfaces available for capture.
  -c <count>            Number of packets to capture.
  -C                    Enable UDP checksum validation.
  -d <directory>        Set dictionary directory.
  -d <raddb>            Set configuration directory (defaults to /etc/freeradius/3.0).
  -D <dictdir>          Set main dictionary directory (defaults to /usr/share/freeradius).
  -e <event>[,<event>]  Only log requests with these event flags.
                        Event may be one of the following:
                        - received - a request or response.
                        - norsp    - seen for a request.
                        - rtx      - of a request that we've seen before.
                        - noreq    - could be matched with the response.
                        - reused   - ID too soon.
                        - error    - decoding the packet.
  -f <filter>           PCAP filter (default is 'udp port <port> or <port + 1> or 3799')
  -h                    This help message.
  -i <interface>        Capture packets from interface (defaults to all if supported).
  -I <file>             Read packets from file (overrides input of -F).
  -l <attr>[,<attr>]    Output packet sig and a list of attributes.
  -L <attr>[,<attr>]    Detect retransmissions using these attributes to link requests.
  -m                    Don't put interface(s) into promiscuous mode.
  -p <port>             Filter packets by port (default is 1812).
  -P <pidfile>          Daemonize and write out <pidfile>.
  -q                    Print less debugging information.
  -r <filter>           RADIUS attribute request filter.
  -R <filter>           RADIUS attribute response filter.
  -s <secret>           RADIUS secret.
  -S                    Write PCAP data to stdout.
  -v                    Show program version information.
  -w <file>             Write output packets to file.
  -x                    Print more debugging information.
stats options:
  -W <interval>         Periodically write out statistics every <interval> seconds.
  -T <timeout>          How many milliseconds before the request is counted as lost (defaults to 5200).
```

***

**radsqlrelay**

Relay SQL queries to a central database server

```
:~# radsqlrelay --help
/usr/bin/radsqlrelay version [unknown] calling Getopt::Std::getopts (version 1.13 [paranoid]),
running under Perl version 5.36.0.

Usage: radsqlrelay [-OPTIONS [-MORE_OPTIONS]] [--] [PROGRAM_ARG1 ...]

The following single-character options are accepted:
	With arguments: -b -d -f -h -P -p -u
	Boolean (without arguments): -x -1 -?

Options may be merged together.  -- stops processing of options.
Space is not required between options and their arguments.
  [Now continuing due to backward compatibility and excessive paranoia.
   See 'perldoc Getopt::Std' about $Getopt::Std::STANDARD_HELP_VERSION.]
usage: radsqlrelay [options] file_path
options:
	-?		Print this help message.
	-1		One-shot mode: push the file to database and exit.
	-b database	Name of the database to use.
	-d sql_driver	Driver to use: mysql, pg, oracle.
	-f file		Read password from file, instead of command line.
	-h host		Connect to host.
	-P port		Port number to use for connection.
	-p password	Password to use when connecting to server.
	-u user		User for login.
	-x		Turn on debugging.
```

***

**radtest**

Send packets to a RADIUS server, show reply

```
:~# radtest -h
Usage: radtest [OPTIONS] user passwd radius-server[:port] nas-port-number secret [ppphint] [nasname]
        -d RADIUS_DIR       Set radius directory
        -t <type>           Set authentication method
                            type can be pap, chap, mschap, or eap-md5
        -P protocol         Select udp (default) or tcp
        -x                  Enable debug output
        -4                  Use IPv4 for the NAS address (default)
        -6                  Use IPv6 for the NAS address
```

***

**radwho**

Show online users

```
:~# radwho -h
radwho: invalid option -- 'h'
Usage: radwho [-d raddb] [-cfihnprRsSZ] [-N nas] [-P nas_port] [-u user] [-U user]
  -c                   Show caller ID, if available.
  -d                   Set the raddb directory (default is /etc/freeradius/3.0).
  -F <file>            Use radutmp <file>.
  -i                   Show session ID.
  -n                   No full name.
  -N <nas-ip-address>  Show entries matching the given NAS IP address.
  -p                   Show port type.
  -P <port>            Show entries matching the given nas port.
  -r                   Print output as raw comma-delimited data.
  -R                   Print output as RADIUS attributes and values.
                       includes ALL information from the radutmp record.
  -s                   Show full name.
  -S                   Hide shell users from radius.
  -u <user>            Show entries matching the given user.
  -U <user>            Like -u, but case-sensitive.
  -v                   Show program version information.
  -Z                   Include accounting stop information in radius output.  Requires -R.
```

***

**radzap**

Remove rogue entries from the active sessions database

```
:~# radzap -h
       -h Print usage help information.
       -d raddb_directory: directory where radiusd.conf is located.
       -D dict_directory: directory where the dictionaries are located.
       -N nas_ip_address: IP address of the NAS to zap.
       -P nas_port: NAS port that the user is logged into.
       -u username: Name of user to zap (case insensitive).
       -U username: like -u, but case-sensitive.
       -x Enable debugging output.
```

***

**rlm\_ippool\_tool**

Dump the contents of the FreeRadius ippool database files

```
:~# rlm_ippool_tool -h
Usage: rlm_ippool_tool [-a] [-c] [-o] [-v] <filename> <index-db> [ipaddress]
  -a: print all active entries
  -c: report number of active entries
  -r: remove active entries
  -v: verbose report of all entries
  -o: Assume old database format (nas/port pair, not md5 output)
  If an ipaddress is specified then that address is used to
  limit the actions or output.
  Usage: rlm_ippool_tool -n  <filename> <index-db> <ipaddress> <nasIP> <nasPort>
  -n: Mark the entry nasIP/nasPort as having ipaddress
  Usage: rlm_ippool_tool -u <filename> <new-filename>
  -u: Update old format database to new.
```

***

**smbencrypt**

Produce LM & NT password hashes from cleartext passwords

```
:~# smbencrypt -h
DF760E4A0C771C76AAD3B435B51404EE	D5C2FA46EAAEADD4D21C7FB7E8F7322A
```

***

#### freeradius-yubikey <a href="#freeradius-yubikey" id="freeradius-yubikey"></a>

This package is required to add Yubikey functionality to the FreeRADIUS server.

**Installed size:** `55 KB`\
**How to install:** `sudo apt install freeradius-yubikey`

<details>

<summary>Dependencies:</summary>

* freeradius
* libc6
* libykclient3
* libyubikey0

</details>

***

#### libfreeradius-dev <a href="#libfreeradius-dev" id="libfreeradius-dev"></a>

The FreeRADIUS projects’ libfreeradius-radius and libfreeradius-eap, used by the FreeRADIUS server and some of the utilities.

This package contains the development headers and static library version.

**Installed size:** `1.16 MB`\
**How to install:** `sudo apt install libfreeradius-dev`

<details>

<summary>Dependencies:</summary>

* freeradius-dhcp
* libfreeradius3

</details>

***

#### libfreeradius3 <a href="#libfreeradius3" id="libfreeradius3"></a>

The FreeRADIUS projects’ libfreeradius-radius and libfreeradius-eap, used by the FreeRADIUS server and some of the utilities.

**Installed size:** `551 KB`\
**How to install:** `sudo apt install libfreeradius3`

<details>

<summary>Dependencies:</summary>

* libc6
* libcap2
* libpcap0.8
* libpcre3
* libssl3
* libtalloc2

</details>

***
