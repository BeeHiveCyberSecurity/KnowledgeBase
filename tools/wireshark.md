---
description: >-
  Wireshark is a popular open-source network protocol analyzer that is used to
  capture, analyze, and troubleshoot network traffic. It is widely used by
  network administrators & security professionals.
---

# 🌐 wireshark

### Screenshots <a href="#screenshots" id="screenshots"></a>

```
wireshark
```

[![wireshark](<../.gitbook/assets/wireshark (1).png>)](<../.gitbook/assets/wireshark (1).png>)

### tshark Usage Example <a href="#tshark-usage-example" id="tshark-usage-example"></a>

```
:~# tshark -f "tcp port 80" -i eth0
```

***

\


### Packages and Binaries:

#### libwireshark-data <a href="#libwireshark-data" id="libwireshark-data"></a>

The libwireshark library provides the network packet dissection services developed by the Wireshark project.

This package contains the platform independent files.

**Installed size:** `7.25 MB`\
**How to install:** `sudo apt install libwireshark-data`

***

#### libwireshark-dev <a href="#libwireshark-dev" id="libwireshark-dev"></a>

The “libwireshark” library provides the network packet dissection services developed by the Wireshark project.

This package contains the static library and the C header files that are needed for applications to use libwireshark services.

**Installed size:** `4.44 MB`\
**How to install:** `sudo apt install libwireshark-dev`

<details>

<summary>Dependencies:</summary>

* libwireshark16
* libwiretap-dev
* libwsutil-dev

</details>

***

#### libwireshark16 <a href="#libwireshark16" id="libwireshark16"></a>

The libwireshark library provides the network packet dissection services developed by the Wireshark project.

**Installed size:** `107.87 MB`\
**How to install:** `sudo apt install libwireshark16`

<details>

<summary>Dependencies:</summary>

* libbcg729-0
* libbrotli1
* libc-ares2
* libc6
* libgcrypt20
* libglib2.0-0
* libgnutls30
* libgpg-error0
* libk5crypto3
* libkrb5-3
* liblua5.2-0
* liblz4-1
* libnghttp2-14
* libpcre2-8-0
* libsbc1
* libsmi2ldbl
* libsnappy1v5
* libspandsp2
* libwireshark-data
* libwiretap13
* libwsutil14
* libxml2
* libzstd1
* zlib1g

</details>

***

#### libwiretap-dev <a href="#libwiretap-dev" id="libwiretap-dev"></a>

Wiretap, part of the Wireshark project, is a library that allows one to read and write several packet capture file formats.

Supported formats are:

* Libpcap
* Sniffer
* LANalyzer
* Network Monitor
* “snoop”
* “iptrace”
* Sniffer Basic (NetXRay)/Windows Sniffer Pro
* RADCOM WAN/LAN Analyzers
* Lucent/Ascend access products
* HP-UX nettl
* Toshiba ISDN Router
* ISDN4BSD “i4btrace” utility
* Cisco Secure Intrusion Detection System iplogging facility
* pppd logs (pppdump-format files)
* VMS TCPTRACE
* DBS Etherwatch (text format)
* Catapult DCT2000 (.out files)

Wiretap’s shortcomings are: no filter capability and no support for packet capture.

This package contains the static library and the C header files.

**Installed size:** `195 KB`\
**How to install:** `sudo apt install libwiretap-dev`

<details>

<summary>Dependencies:</summary>

* libwiretap13

</details>

***

#### libwiretap13 <a href="#libwiretap13" id="libwiretap13"></a>

Wiretap, part of the Wireshark project, is a library that allows one to read and write several packet capture file formats.

Supported formats are:

* Libpcap
* Sniffer
* LANalyzer
* Network Monitor
* “snoop”
* “iptrace”
* Sniffer Basic (NetXRay)/Windows Sniffer Pro
* RADCOM WAN/LAN Analyzers
* Lucent/Ascend access products
* HP-UX nettl
* Toshiba ISDN Router
* ISDN4BSD “i4btrace” utility
* Cisco Secure Intrusion Detection System iplogging facility
* pppd logs (pppdump-format files)
* VMS TCPTRACE
* DBS Etherwatch (text format)
* Catapult DCT2000 (.out files)

Wiretap’s shortcomings are: no filter capability and no support for packet capture.

**Installed size:** `694 KB`\
**How to install:** `sudo apt install libwiretap13`

<details>

<summary>Dependencies:</summary>

* libc6
* libglib2.0-0
* liblz4-1
* libwsutil14
* libzstd1
* zlib1g

</details>

***

#### libwsutil-dev <a href="#libwsutil-dev" id="libwsutil-dev"></a>

The libwsutil library provides utility functions for libwireshark6.

This package contains the static library and the C header files that are needed for applications to use the libwsutil library.

**Installed size:** `366 KB`\
**How to install:** `sudo apt install libwsutil-dev`

<details>

<summary>Dependencies:</summary>

* libwsutil14

</details>

***

#### libwsutil14 <a href="#libwsutil14" id="libwsutil14"></a>

The libwsutil library provides utility functions for libwireshark15.

**Installed size:** `269 KB`\
**How to install:** `sudo apt install libwsutil14`

<details>

<summary>Dependencies:</summary>

* libc6
* libgcrypt20
* libglib2.0-0
* libgnutls30
* libpcre2-8-0

</details>

***

#### tshark <a href="#tshark" id="tshark"></a>

Wireshark is a network “sniffer” - a tool that captures and analyzes packets off the wire. Wireshark can decode too many protocols to list here.

This package provides the console version of wireshark, named “tshark”.

**Installed size:** `403 KB`\
**How to install:** `sudo apt install tshark`

<details>

<summary>Dependencies:</summary>

* libc6
* libglib2.0-0
* libpcap0.8
* libpcre2-8-0
* libwireshark16
* libwiretap13
* libwsutil14
* wireshark-common
* zlib1g

</details>

**tshark**

Dump and analyze network traffic

```
:~# tshark -h
TShark (Wireshark) 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Dump and analyze network traffic.
See https://www.wireshark.org for more information.

Usage: tshark [options] ...

Capture interface:
  -i <interface>, --interface <interface>
                           name or idx of interface (def: first non-loopback)
  -f <capture filter>      packet filter in libpcap filter syntax
  -s <snaplen>, --snapshot-length <snaplen>
                           packet snapshot length (def: appropriate maximum)
  -p, --no-promiscuous-mode
                           don't capture in promiscuous mode
  -I, --monitor-mode       capture in monitor mode, if available
  -B <buffer size>, --buffer-size <buffer size>
                           size of kernel buffer (def: 2MB)
  -y <link type>, --linktype <link type>
                           link layer type (def: first appropriate)
  --time-stamp-type <type> timestamp method for interface
  -D, --list-interfaces    print list of interfaces and exit
  -L, --list-data-link-types
                           print list of link-layer types of iface and exit
  --list-time-stamp-types  print list of timestamp types for iface and exit

Capture stop conditions:
  -c <packet count>        stop after n packets (def: infinite)
  -a <autostop cond.> ..., --autostop <autostop cond.> ...
                           duration:NUM - stop after NUM seconds
                           filesize:NUM - stop this file after NUM KB
                              files:NUM - stop after NUM files
                            packets:NUM - stop after NUM packets
Capture output:
  -b <ringbuffer opt.> ..., --ring-buffer <ringbuffer opt.>
                           duration:NUM - switch to next file after NUM secs
                           filesize:NUM - switch to next file after NUM KB
                              files:NUM - ringbuffer: replace after NUM files
                            packets:NUM - switch to next file after NUM packets
                           interval:NUM - switch to next file when the time is
                                          an exact multiple of NUM secs
Input file:
  -r <infile>, --read-file <infile>
                           set the filename to read from (or '-' for stdin)

Processing:
  -2                       perform a two-pass analysis
  -M <packet count>        perform session auto reset
  -R <read filter>, --read-filter <read filter>
                           packet Read filter in Wireshark display filter syntax
                           (requires -2)
  -Y <display filter>, --display-filter <display filter>
                           packet displaY filter in Wireshark display filter
                           syntax
  -n                       disable all name resolutions (def: "mNd" enabled, or
                           as set in preferences)
  -N <name resolve flags>  enable specific name resolution(s): "mnNtdv"
  -d <layer_type>==<selector>,<decode_as_protocol> ...
                           "Decode As", see the man page for details
                           Example: tcp.port==8888,http
  -H <hosts file>          read a list of entries from a hosts file, which will
                           then be written to a capture file. (Implies -W n)
  --enable-protocol <proto_name>
                           enable dissection of proto_name
  --disable-protocol <proto_name>
                           disable dissection of proto_name
  --enable-heuristic <short_name>
                           enable dissection of heuristic protocol
  --disable-heuristic <short_name>
                           disable dissection of heuristic protocol
Output:
  -w <outfile|->           write packets to a pcapng-format file named "outfile"
                           (or '-' for stdout)
  --capture-comment <comment>
                           add a capture file comment, if supported
  -C <config profile>      start with specified configuration profile
  -F <output file type>    set the output file type, default is pcapng
                           an empty "-F" option will list the file types
  -V                       add output of packet tree        (Packet Details)
  -O <protocols>           Only show packet details of these protocols, comma
                           separated
  -P, --print              print packet summary even when writing to a file
  -S <separator>           the line separator to print between packets
  -x                       add output of hex and ASCII dump (Packet Bytes)
  --hexdump <hexoption>    add hexdump, set options for data source and ASCII dump
     all                   dump all data sources (-x default)
     frames                dump only frame data source
     ascii                 include ASCII dump text (-x default)
     delimit               delimit ASCII dump text with '|' characters
     noascii               exclude ASCII dump text
     help                  display help for --hexdump and exit
  -T pdml|ps|psml|json|jsonraw|ek|tabs|text|fields|?
                           format of text output (def: text)
  -j <protocolfilter>      protocols layers filter if -T ek|pdml|json selected
                           (e.g. "ip ip.flags text", filter does not expand child
                           nodes, unless child is specified also in the filter)
  -J <protocolfilter>      top level protocol filter if -T ek|pdml|json selected
                           (e.g. "http tcp", filter which expands all child nodes)
  -e <field>               field to print if -Tfields selected (e.g. tcp.port,
                           _ws.col.Info)
                           this option can be repeated to print multiple fields
  -E<fieldsoption>=<value> set options for output when -Tfields selected:
     bom=y|n               print a UTF-8 BOM
     header=y|n            switch headers on and off
     separator=/t|/s|<char> select tab, space, printable character as separator
     occurrence=f|l|a      print first, last or all occurrences of each field
     aggregator=,|/s|<char> select comma, space, printable character as
                           aggregator
     quote=d|s|n           select double, single, no quotes for values
  -t a|ad|adoy|d|dd|e|r|u|ud|udoy
                           output format of time stamps (def: r: rel. to first)
  -u s|hms                 output format of seconds (def: s: seconds)
  -l                       flush standard output after each packet
  -q                       be more quiet on stdout (e.g. when using statistics)
  -Q                       only log true errors to stderr (quieter than -q)
  -g                       enable group read access on the output file(s)
  -W n                     Save extra information in the file, if supported.
                           n = write network address resolution information
  -X <key>:<value>         eXtension options, see the man page for details
  -U tap_name              PDUs export mode, see the man page for details
  -z <statistics>          various statistics, see the man page for details
  --export-objects <protocol>,<destdir>
                           save exported objects for a protocol to a directory
                           named "destdir"
  --export-tls-session-keys <keyfile>
                           export TLS Session Keys to a file named "keyfile"
  --color                  color output text similarly to the Wireshark GUI,
                           requires a terminal with 24-bit color support
                           Also supplies color attributes to pdml and psml formats
                           (Note that attributes are nonstandard)
  --no-duplicate-keys      If -T json is specified, merge duplicate keys in an object
                           into a single key with as value a json array containing all
                           values
  --elastic-mapping-filter <protocols> If -G elastic-mapping is specified, put only the
                           specified protocols within the mapping file
  --temp-dir <directory>   write temporary files to this directory
                           (default: /tmp)

Diagnostic output:
  --log-level <level>      sets the active log level ("critical", "warning", etc.)
  --log-fatal <level>      sets level to abort the program ("critical" or "warning")
  --log-domains <[!]list>  comma separated list of the active log domains
  --log-debug <[!]list>    comma separated list of domains with "debug" level
  --log-noisy <[!]list>    comma separated list of domains with "noisy" level
  --log-file <path>        file to output messages to (in addition to stderr)

Miscellaneous:
  -h, --help               display this help and exit
  -v, --version            display version info and exit
  -o <name>:<value> ...    override preference setting
  -K <keytab>              keytab file to use for kerberos decryption
  -G [report]              dump one of several available reports and exit
                           default report="fields"
                           use "-G help" for more help

Dumpcap can benefit from an enabled BPF JIT compiler if available.
You might want to enable it by executing:
 "echo 1 > /proc/sys/net/core/bpf_jit_enable"
Note that this can make your system less secure!
```

***

#### wireshark <a href="#wireshark" id="wireshark"></a>

Wireshark is a network “sniffer” - a tool that captures and analyzes packets off the wire. Wireshark can decode too many protocols to list here.

This is a meta-package for Wireshark.

**Installed size:** `37 KB`\
**How to install:** `sudo apt install wireshark`

<details>

<summary>Dependencies:</summary>

* wireshark-qt

</details>

***

#### wireshark-common <a href="#wireshark-common" id="wireshark-common"></a>

Wireshark is a network “sniffer” - a tool that captures and analyzes packets off the wire. Wireshark can decode too many protocols to list here.

This package provides files common to both wireshark and tshark (the console version).

**Installed size:** `1.34 MB`\
**How to install:** `sudo apt install wireshark-common`

<details>

<summary>Dependencies:</summary>

* debconf
* debconf | debconf-2.0
* libc6
* libcap2
* libcap2-bin
* libgcrypt20
* libglib2.0-0
* libmaxminddb0
* libnl-3-200
* libnl-genl-3-200
* libpcap0.8
* libpcre2-8-0
* libspeexdsp1
* libssh-gcrypt-4
* libsystemd0
* libwireshark16
* libwiretap13
* libwsutil14
* zlib1g

</details>

**capinfos**

Prints information about capture files

```
:~# capinfos -h
Capinfos (Wireshark) 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Print various information (infos) about capture files.
See https://www.wireshark.org for more information.

Usage: capinfos [options] <infile> ...

General infos:
  -t display the capture file type
  -E display the capture file encapsulation
  -I display the capture file interface information
  -F display additional capture file information
  -H display the SHA256, RIPEMD160, and SHA1 hashes of the file
  -k display the capture comment

Size infos:
  -c display the number of packets
  -s display the size of the file (in bytes)
  -d display the total length of all packets (in bytes)
  -l display the packet size limit (snapshot length)

Time infos:
  -u display the capture duration (in seconds)
  -a display the capture start time
  -e display the capture end time
  -o display the capture file chronological status (True/False)
  -S display start and end times as seconds

Statistic infos:
  -y display average data rate (in bytes/sec)
  -i display average data rate (in bits/sec)
  -z display average packet size (in bytes)
  -x display average packet rate (in packets/sec)

Metadata infos:
  -n display number of resolved IPv4 and IPv6 addresses
  -D display number of decryption secrets

Output format:
  -L generate long report (default)
  -T generate table report
  -M display machine-readable values in long reports

Table report options:
  -R generate header record (default)
  -r do not generate header record

  -B separate infos with TAB character (default)
  -m separate infos with comma (,) character
  -b separate infos with SPACE character

  -N do not quote infos (default)
  -q quote infos with single quotes (')
  -Q quote infos with double quotes (")

Miscellaneous:
  -h, --help               display this help and exit
  -v, --version            display version info and exit
  -C cancel processing if file open fails (default is to continue)
  -A generate all infos (default)
  -K disable displaying the capture comment

Options are processed from left to right order with later options superseding
or adding to earlier options.

If no options are given the default is to display all infos in long report
output format.
```

***

**captype**

Prints the types of capture files

```
:~# captype -h
Captype (Wireshark) 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Print the file types of capture files.
See https://www.wireshark.org for more information.

Usage: captype [options] <infile> ...

Miscellaneous:
  -h, --help               display this help and exit
  -v, --version            display version info and exit
```

***

**dumpcap**

Dump network traffic

```
:~# dumpcap -h
Dumpcap (Wireshark) 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Capture network packets and dump them into a pcapng or pcap file.
See https://www.wireshark.org for more information.

Usage: dumpcap [options] ...

Capture interface:
  -i <interface>, --interface <interface>
                           name or idx of interface (def: first non-loopback),
                           or for remote capturing, use one of these formats:
                               rpcap://<host>/<interface>
                               <host>:<port>
  --ifname <name>          name to use in the capture file for a pipe from which
                           we're capturing
  --ifdescr <description>
                           description to use in the capture file for a pipe
                           from which we're capturing
  -f <capture filter>      packet filter in libpcap filter syntax
  -s <snaplen>, --snapshot-length <snaplen>
                           packet snapshot length (def: appropriate maximum)
  -p, --no-promiscuous-mode
                           don't capture in promiscuous mode
  -I, --monitor-mode       capture in monitor mode, if available
  -B <buffer size>, --buffer-size <buffer size>
                           size of kernel buffer in MiB (def: 2MiB)
  -y <link type>, --linktype <link type>
                           link layer type (def: first appropriate)
  --time-stamp-type <type> timestamp method for interface
  -D, --list-interfaces    print list of interfaces and exit
  -L, --list-data-link-types
                           print list of link-layer types of iface and exit
  --list-time-stamp-types  print list of timestamp types for iface and exit
  -d                       print generated BPF code for capture filter
  -k <freq>,[<type>],[<center_freq1>],[<center_freq2>]
                           set channel on wifi interface
  -S                       print statistics for each interface once per second
  -M                       for -D, -L, and -S, produce machine-readable output

Stop conditions:
  -c <packet count>        stop after n packets (def: infinite)
  -a <autostop cond.> ..., --autostop <autostop cond.> ...
                           duration:NUM - stop after NUM seconds
                           filesize:NUM - stop this file after NUM kB
                              files:NUM - stop after NUM files
                            packets:NUM - stop after NUM packets
Output (files):
  -w <filename>            name of file to save (def: tempfile)
  -g                       enable group read access on the output file(s)
  -b <ringbuffer opt.> ..., --ring-buffer <ringbuffer opt.>
                           duration:NUM - switch to next file after NUM secs
                           filesize:NUM - switch to next file after NUM kB
                              files:NUM - ringbuffer: replace after NUM files
                            packets:NUM - ringbuffer: replace after NUM packets
                           interval:NUM - switch to next file when the time is
                                          an exact multiple of NUM secs
                          printname:FILE - print filename to FILE when written
                                           (can use 'stdout' or 'stderr')
  -n                       use pcapng format instead of pcap (default)
  -P                       use libpcap format instead of pcapng
  --capture-comment <comment>
                           add a capture comment to the output file
                           (only for pcapng)
  --temp-dir <directory>   write temporary files to this directory
                           (default: /tmp)

Diagnostic output:
  --log-level <level>      sets the active log level ("critical", "warning", etc.)
  --log-fatal <level>      sets level to abort the program ("critical" or "warning")
  --log-domains <[!]list>  comma separated list of the active log domains
  --log-debug <[!]list>    comma separated list of domains with "debug" level
  --log-noisy <[!]list>    comma separated list of domains with "noisy" level
  --log-file <path>        file to output messages to (in addition to stderr)

Miscellaneous:
  -N <packet_limit>        maximum number of packets buffered within dumpcap
  -C <byte_limit>          maximum number of bytes used for buffering packets
                           within dumpcap
  -t                       use a separate thread per interface
  -q                       don't report packet capture counts
  -v, --version            print version information and exit
  -h, --help               display this help and exit

Dumpcap can benefit from an enabled BPF JIT compiler if available.
You might want to enable it by executing:
 "echo 1 > /proc/sys/net/core/bpf_jit_enable"
Note that this can make your system less secure!

Example: dumpcap -i eth0 -a duration:60 -w output.pcapng
"Capture packets from interface eth0 until 60s passed into output.pcapng"

Use Ctrl-C to stop capturing at any time.
```

***

**editcap**

Edit and/or translate the format of capture files

```
:~# editcap -h
Editcap (Wireshark) 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Edit and/or translate the format of capture files.
See https://www.wireshark.org for more information.

Usage: editcap [options] ... <infile> <outfile> [ <packet#>[-<packet#>] ... ]

<infile> and <outfile> must both be present; use '-' for stdin or stdout.
A single packet or a range of packets can be selected.

Packet selection:
  -r                     keep the selected packets; default is to delete them.
  -A <start time>        only read packets whose timestamp is after (or equal
                         to) the given time.
  -B <stop time>         only read packets whose timestamp is before the
                         given time.
                         Time format for -A/-B options is
                         YYYY-MM-DDThh:mm:ss[.nnnnnnnnn][Z|+-hh:mm]
                         Unix epoch timestamps are also supported.

Duplicate packet removal:
  --novlan               remove vlan info from packets before checking for duplicates.
  -d                     remove packet if duplicate (window == 5).
  -D <dup window>        remove packet if duplicate; configurable <dup window>.
                         Valid <dup window> values are 0 to 1000000.
                         NOTE: A <dup window> of 0 with -V (verbose option) is
                         useful to print MD5 hashes.
  -w <dup time window>   remove packet if duplicate packet is found EQUAL TO OR
                         LESS THAN <dup time window> prior to current packet.
                         A <dup time window> is specified in relative seconds
                         (e.g. 0.000001).
           NOTE: The use of the 'Duplicate packet removal' options with
           other editcap options except -V may not always work as expected.
           Specifically the -r, -t or -S options will very likely NOT have the
           desired effect if combined with the -d, -D or -w.
  --skip-radiotap-header skip radiotap header when checking for packet duplicates.
                         Useful when processing packets captured by multiple radios
                         on the same channel in the vicinity of each other.

Packet manipulation:
  -s <snaplen>           truncate each packet to max. <snaplen> bytes of data.
  -C [offset:]<choplen>  chop each packet by <choplen> bytes. Positive values
                         chop at the packet beginning, negative values at the
                         packet end. If an optional offset precedes the length,
                         then the bytes chopped will be offset from that value.
                         Positive offsets are from the packet beginning,
                         negative offsets are from the packet end. You can use
                         this option more than once, allowing up to 2 chopping
                         regions within a packet provided that at least 1
                         choplen is positive and at least 1 is negative.
  -L                     adjust the frame (i.e. reported) length when chopping
                         and/or snapping.
  -t <time adjustment>   adjust the timestamp of each packet.
                         <time adjustment> is in relative seconds (e.g. -0.5).
  -S <strict adjustment> adjust timestamp of packets if necessary to ensure
                         strict chronological increasing order. The <strict
                         adjustment> is specified in relative seconds with
                         values of 0 or 0.000001 being the most reasonable.
                         A negative adjustment value will modify timestamps so
                         that each packet's delta time is the absolute value
                         of the adjustment specified. A value of -0 will set
                         all packets to the timestamp of the first packet.
  -E <error probability> set the probability (between 0.0 and 1.0 incl.) that
                         a particular packet byte will be randomly changed.
  -o <change offset>     When used in conjunction with -E, skip some bytes from the
                         beginning of the packet. This allows one to preserve some
                         bytes, in order to have some headers untouched.
  --seed <seed>          When used in conjunction with -E, set the seed to use for
                         the pseudo-random number generator. This allows one to
                         repeat a particular sequence of errors.
  -I <bytes to ignore>   ignore the specified number of bytes at the beginning
                         of the frame during MD5 hash calculation, unless the
                         frame is too short, then the full frame is used.
                         Useful to remove duplicated packets taken on
                         several routers (different mac addresses for
                         example).
                         e.g. -I 26 in case of Ether/IP will ignore
                         ether(14) and IP header(20 - 4(src ip) - 4(dst ip)).
  -a <framenum>:<comment> Add or replace comment for given frame number

Output File(s):
  -c <packets per file>  split the packet output to different files based on
                         uniform packet counts with a maximum of
                         <packets per file> each.
  -i <seconds per file>  split the packet output to different files based on
                         uniform time intervals with a maximum of
                         <seconds per file> each.
  -F <capture type>      set the output file type; default is pcapng.
                         An empty "-F" option will list the file types.
  -T <encap type>        set the output file encapsulation type; default is the
                         same as the input file. An empty "-T" option will
                         list the encapsulation types.
  --inject-secrets <type>,<file>  Insert decryption secrets from <file>. List
                         supported secret types with "--inject-secrets help".
  --discard-all-secrets  Discard all decryption secrets from the input file
                         when writing the output file.  Does not discard
                         secrets added by "--inject-secrets" in the same
                         command line.
  --capture-comment <comment>
                         Add a capture file comment, if supported.
  --discard-capture-comment
                         Discard capture file comments from the input file
                         when writing the output file.  Does not discard
                         comments added by "--capture-comment" in the same
                         command line.

Miscellaneous:
  -h, --help             display this help and exit.
  -V                     verbose output.
                         If -V is used with any of the 'Duplicate Packet
                         Removal' options (-d, -D or -w) then Packet lengths
                         and MD5 hashes are printed to standard-error.
  -v, --version          print version information and exit.
```

***

**mergecap**

Merges two or more capture files into one

```
:~# mergecap -h
Mergecap (Wireshark) 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Merge two or more capture files into one.
See https://www.wireshark.org for more information.

Usage: mergecap [options] -w <outfile>|- <infile> [<infile> ...]

Output:
  -a                concatenate rather than merge files.
                    default is to merge based on frame timestamps.
  -s <snaplen>      truncate packets to <snaplen> bytes of data.
  -w <outfile>|-    set the output filename to <outfile> or '-' for stdout.
  -F <capture type> set the output file type; default is pcapng.
                    an empty "-F" option will list the file types.
  -I <IDB merge mode> set the merge mode for Interface Description Blocks; default is 'all'.
                    an empty "-I" option will list the merge modes.

Miscellaneous:
  -h, --help        display this help and exit.
  -V                verbose output.
  -v, --version     print version information and exit.
```

***

**mmdbresolve**

Read IPv4 and IPv6 addresses and print their IP geolocation information.

```
:~# mmdbresolve -h
Usage: mmdbresolve -f db_file [-f db_file ...]
```

***

**randpkt**

Random packet generator

```
:~# randpkt -h
Usage: randpkt [-b maxbytes] [-c count] [-t type] [-r] filename
Default max bytes (per packet) is 5000
Default count is 1000.
-r: random packet type selection

Types:
	arp             Address Resolution Protocol
	bgp             Border Gateway Protocol
	bvlc            BACnet Virtual Link Control
	dns             Domain Name Service
	eth             Ethernet
	fddi            Fiber Distributed Data Interface
	giop            General Inter-ORB Protocol
	icmp            Internet Control Message Protocol
	ieee802.15.4    IEEE 802.15.4
	ip              Internet Protocol
	ipv6            Internet Protocol Version 6
	llc             Logical Link Control
	m2m             WiMAX M2M Encapsulation Protocol
	megaco          MEGACO
	nbns            NetBIOS-over-TCP Name Service
	ncp2222         NetWare Core Protocol
	sctp            Stream Control Transmission Protocol
	syslog          Syslog message
	tds             TDS NetLib
	tcp             Transmission Control Protocol
	tr              Token-Ring
	udp             User Datagram Protocol
	usb-linux       Universal Serial Bus with Linux specific header

If type is not specified, a random packet will be chosen

```

***

**rawshark**

Dump and analyze raw pcap data

```
:~# rawshark -h
Rawshark (Wireshark) 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Dump and analyze network traffic.
See https://www.wireshark.org for more information.

Usage: rawshark [options] ...

Input file:
  -r <infile>              set the pipe or file name to read from

Processing:
  -d <encap:linktype>|<proto:protoname>
                           packet encapsulation or protocol
  -F <field>               field to display
  -m                       virtual memory limit, in bytes
  -n                       disable all name resolution (def: all enabled)
  -N <name resolve flags>  enable specific name resolution(s): "mnNtdv"
  -p                       use the system's packet header format
                           (which may have 64-bit timestamps)
  -R <read filter>         packet filter in Wireshark display filter syntax
  -s                       skip PCAP header on input

Output:
  -l                       flush output after each packet
  -S                       format string for fields
                           (%D - name, %S - stringval, %N numval)
  -t ad|a|r|d|dd|e         output format of time stamps (def: r: rel. to first)

Diagnostic output:
  --log-level <level>      sets the active log level ("critical", "warning", etc.)
  --log-fatal <level>      sets level to abort the program ("critical" or "warning")
  --log-domains <[!]list>  comma separated list of the active log domains
  --log-debug <[!]list>    comma separated list of domains with "debug" level
  --log-noisy <[!]list>    comma separated list of domains with "noisy" level
  --log-file <path>        file to output messages to (in addition to stderr)


Miscellaneous:
  -h                       display this help and exit
  -o <name>:<value> ...    override preference setting
  -v                       display version info and exit
```

***

**reordercap**

Reorder input file by timestamp into output file

```
:~# reordercap -h
Reordercap (Wireshark) 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Reorder timestamps of input file frames into output file.
See https://www.wireshark.org for more information.

Usage: reordercap [options] <infile> <outfile>

Options:
  -n        don't write to output file if the input file is ordered.
  -h        display this help and exit.
  -v        print version information and exit.
```

***

**sharkd**

```
:~# sharkd -h
Running as user "root" and group "root". This could be dangerous.

Usage: sharkd [<classic_options>|<gold_options>]

Classic (classic_options):
  [-|<socket>]

  <socket> examples:
  - unix:/tmp/sharkd.sock - listen on unix file /tmp/sharkd.sock

Gold (gold_options):
  -a <socket>, --api <socket>
                           listen on this socket
  -h, --help               show this help information
  -v, --version            show version information
  -C <config profile>, --config-profile <config profile>
                           start with specified configuration profile

  Examples:
    sharkd -C myprofile
    sharkd -a tcp:127.0.0.1:4446 -C myprofile

See the sharkd page of the Wireshark wiki for full details.

```

***

**text2pcap**

Generate a capture file from an ASCII hexdump of packets

```
:~# text2pcap -h
Text2pcap (Wireshark) 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Generate a capture file from an ASCII hexdump of packets.
See https://www.wireshark.org for more information.

Usage: text2pcap [options] <infile> <outfile>

where  <infile> specifies input  filename (use - for standard input)
      <outfile> specifies output filename (use - for standard output)

Input:
  -o hex|oct|dec|none    parse offsets as (h)ex, (o)ctal, (d)ecimal, or (n)one;
                         default is hex.
  -t <timefmt>           treat the text before the packet as a date/time code;
                         <timefmt> is a format string supported by strptime,
                         with an optional %f descriptor for fractional seconds.
                         Example: The time "10:15:14.5476" has the format code
                         "%H:%M:%S.%f"
                         The special format string ISO supports ISO-8601 times.
                         NOTE: Date/time fields from the current date/time are
                         used as the default for unspecified fields.
  -D                     the text before the packet starts with an I or an O,
                         indicating that the packet is inbound or outbound.
                         This is used when generating dummy headers if the
                         output format supports it (e.g. pcapng).
  -a                     enable ASCII text dump identification.
                         The start of the ASCII text dump can be identified
                         and excluded from the packet data, even if it looks
                         like a HEX dump.
                         NOTE: Do not enable it if the input file does not
                         contain the ASCII text dump.
  -r <regex>             enable regex mode. Scan the input using <regex>, a Perl
                         compatible regular expression matching a single packet.
                         Named capturing subgroups are used to identify fields:
                         <data> (mand.), and <time>, <dir>, and <seqno> (opt.)
                         The time field format is taken from the -t option
                         Example: -r '^(?<dir>[<>])\s(?<time>\d+:\d\d:\d\d.\d+)\s(?<data>[0-9a-fA-F]+)$'
                         could match a file with lines like
                         > 0:00:00.265620 a130368b000000080060
                         < 0:00:00.295459 a2010800000000000000000800000000
  -b 2|8|16|64           encoding base (radix) of the packet data in regex mode
                         (def: 16: hexadecimal) No effect in hexdump mode.

Output:
  -F <capture type>      set the output file type; default is pcapng.
                         an empty "-F" option will list the file types.
  -E <encap type>        set the output file encapsulation type; default is
                         ether (Ethernet). An empty "-E" option will list
                         the encapsulation types.
  -l <typenum>           set the output file encapsulation type via link-layer
                         type number; default is 1 (Ethernet). See
                         https://www.tcpdump.org/linktypes.html for a list of
                         numbers.
                         Example: -l 7 for ARCNet packets.
  -m <max-packet>        max packet length in output; default is 262144
  -N <intf-name>         assign name to the interface in the pcapng file.

Prepend dummy header:
  -e <l3pid>             prepend dummy Ethernet II header with specified L3PID
                         (in HEX).
                         Example: -e 0x806 to specify an ARP packet.
  -i <proto>             prepend dummy IP header with specified IP protocol
                         (in DECIMAL).
                         Automatically prepends Ethernet header as well if
                         link-layer type is Ethernet.
                         Example: -i 46
  -4 <srcip>,<destip>    prepend dummy IPv4 header with specified
                         dest and source address.
                         Example: -4 10.0.0.1,10.0.0.2
  -6 <srcip>,<destip>    prepend dummy IPv6 header with specified
                         dest and source address.
                         Example: -6 2001:db8::b3ff:fe1e:8329,2001:0db8:85a3::8a2e:0370:7334
  -u <srcp>,<destp>      prepend dummy UDP header with specified
                         source and destination ports (in DECIMAL).
                         Automatically prepends Ethernet & IP headers as well.
                         Example: -u 1000,69 to make the packets look like
                         TFTP/UDP packets.
  -T <srcp>,<destp>      prepend dummy TCP header with specified
                         source and destination ports (in DECIMAL).
                         Automatically prepends Ethernet & IP headers as well.
                         Example: -T 50,60
  -s <srcp>,<dstp>,<tag> prepend dummy SCTP header with specified
                         source/dest ports and verification tag (in DECIMAL).
                         Automatically prepends Ethernet & IP headers as well.
                         Example: -s 30,40,34
  -S <srcp>,<dstp>,<ppi> prepend dummy SCTP header with specified
                         source/dest ports and verification tag 0.
                         Automatically prepends a dummy SCTP DATA
                         chunk header with payload protocol identifier ppi.
                         Example: -S 30,40,34
  -P <dissector>         prepend EXPORTED_PDU header with specified dissector
                         as the payload DISSECTOR_NAME tag.
                         Automatically sets link type to Upper PDU Export.
                         EXPORTED_PDU payload defaults to "data" otherwise.

Diagnostic output:
  --log-level <level>      sets the active log level ("critical", "warning", etc.)
  --log-fatal <level>      sets level to abort the program ("critical" or "warning")
  --log-domains <[!]list>  comma separated list of the active log domains
  --log-debug <[!]list>    comma separated list of domains with "debug" level
  --log-noisy <[!]list>    comma separated list of domains with "noisy" level
  --log-file <path>        file to output messages to (in addition to stderr)

Miscellaneous:
  -h                     display this help and exit
  -v                     print version information and exit
  -q                     don't report processed packet counts
```

***

#### wireshark-dev <a href="#wireshark-dev" id="wireshark-dev"></a>

Wireshark is a network “sniffer” - a tool that captures and analyzes packets off the wire. Wireshark can decode too many protocols to list here.

This package provides idl2wrs and other files necessary for developing new packet dissectors.

**Installed size:** `552 KB`\
**How to install:** `sudo apt install wireshark-dev`

<details>

<summary>Dependencies:</summary>

* libglib2.0-dev
* libpcap0.8-dev
* libwireshark-dev
* libwiretap-dev
* omniidl
* python3
* python3-ply
* snacc

</details>

**asn2deb**

Create a Debian package for BER monitoring from ASN.1

```
:~# asn2deb -h
Usage: /usr/bin/asn2deb <parameters>
Parameters are
  --asn      -a asn1file, ASN.1 file to use (mandatory)
  --dbopts   -d opts,     options for dpkg-buildpackage
  --email    -e address,  use e-mail address
  --help     -h,          print help and exit
  --name     -n name,     use user name
  --preserve -p,          do not overwrite files
  --version  -v,          print version and exit
Example:
/usr/bin/asn2deb -e  -a bar.asn1 -n "My Name" -d "-rfakeroot -uc -us"
```

***

**idl2deb**

Create a Debian package for CORBA monitoring from IDL

```
:~# idl2deb -h
Usage: idl2deb [options]

Example: idl2deb -e  -i bar.idl -n "My Name" -d "-rfakeroot -uc -us"

Options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  -d opts, --dbopts=opts
                        options for dpkg-buildpackage
  -e address, --email=address
                        use e-mail address
  -i idlfile, --idl=idlfile
                        IDL file to use (mandatory)
  -n name, --name=name  use user name
  -p, --preserve        do not overwrite files
```

***

**idl2wrs**

CORBA IDL to Wireshark Plugin Generator

```
:~# idl2wrs -h

Usage: omniidl -b<back_end> [flags] file1 file2 ...

The supported flags are:

  -Dname[=value]  Define name for preprocessor
  -Uname          Undefine name for preprocessor
  -Idir           Include dir in search path for preprocessor
  -E              Run preprocessor only, print on stdout
  -Ycmd           Set command for the preprocessor
  -N              Do not run preprocessor
  -P              Add defines relevant to platform dependencies (internal use)
  -T              Use a temporary file, not a pipe, for preprocessor output
  -Wparg[,arg...] Send args to the preprocessor
  -bback_end      Select a back-end to be used. More than one permitted
  -Wbarg[,arg...] Send args to the back-end
  -nf             Do not warn about unresolved forward declarations
  -nc             Do not treat identifiers differing only in case as an error
  -k              Comments after declarations are kept for the back-ends
  -K              Comments before declarations are kept for the back-ends
  -Cdir           Change directory to dir before writing output
  -d              Dump the parsed IDL then exit
  -i              Enter interactive mode after parsing the IDL
  -pdir           Path to omniidl back-ends ($TOP/lib/python)
  -V              Print version info then exit
  -u              Print this usage message and exit
  -v              Trace compilation stages
```

***

#### wireshark-doc <a href="#wireshark-doc" id="wireshark-doc"></a>

Wireshark is a network “sniffer” - a tool that captures and analyzes packets off the wire. Wireshark can decode too many protocols to list here.

This package contains Wireshark User’s guide, Wireshark Developer’s Guide and the Lua Reference.

**Installed size:** `13.25 MB`\
**How to install:** `sudo apt install wireshark-doc`

***

#### wireshark-gtk <a href="#wireshark-gtk" id="wireshark-gtk"></a>

This is a transitional dummy package. It can safely be removed.

**Installed size:** `35 KB`\
**How to install:** `sudo apt install wireshark-gtk`

<details>

<summary>Dependencies:</summary>

* wireshark-qt

</details>

***

#### wireshark-qt <a href="#wireshark-qt" id="wireshark-qt"></a>

Wireshark is a network “sniffer” - a tool that captures and analyzes packets off the wire. Wireshark can decode too many protocols to list here.

This package provides the Qt version of Wireshark.

**Installed size:** `9.14 MB`\
**How to install:** `sudo apt install wireshark-qt`

<details>

<summary>Dependencies:</summary>

* libc6
* libgcc-s1
* libgcrypt20
* libglib2.0-0
* libminizip1
* libnl-3-200
* libnl-genl-3-200
* libnl-route-3-200
* libpcap0.8
* libpcre2-8-0
* libqt5core5a
* libqt5gui5 | libqt5gui5-gles
* libqt5multimedia5
* libqt5printsupport5
* libqt5svg5
* libqt5widgets5
* libspeexdsp1
* libstdc++6
* libwireshark16
* libwiretap13
* libwsutil14
* wireshark-common
* zlib1g

</details>

**wireshark**

Interactively dump and analyze network traffic

```
:~# wireshark -h
Wireshark 4.0.3 (Git v4.0.3 packaged as 4.0.3-1)
Interactively dump and analyze network traffic.
See https://www.wireshark.org for more information.

Usage: wireshark [options] ... [ <infile> ]

Capture interface:
  -i <interface>, --interface <interface>
                           name or idx of interface (def: first non-loopback)
  -f <capture filter>      packet filter in libpcap filter syntax
  -s <snaplen>, --snapshot-length <snaplen>
                           packet snapshot length (def: appropriate maximum)
  -p, --no-promiscuous-mode
                           don't capture in promiscuous mode
  -k                       start capturing immediately (def: do nothing)
  -S                       update packet display when new packets are captured
  -l                       turn on automatic scrolling while -S is in use
  -I, --monitor-mode       capture in monitor mode, if available
  -B <buffer size>, --buffer-size <buffer size>
                           size of kernel buffer (def: 2MB)
  -y <link type>, --linktype <link type>
                           link layer type (def: first appropriate)
  --time-stamp-type <type> timestamp method for interface
  -D, --list-interfaces    print list of interfaces and exit
  -L, --list-data-link-types
                           print list of link-layer types of iface and exit
  --list-time-stamp-types  print list of timestamp types for iface and exit

Capture stop conditions:
  -c <packet count>        stop after n packets (def: infinite)
  -a <autostop cond.> ..., --autostop <autostop cond.> ...
                           duration:NUM - stop after NUM seconds
                           filesize:NUM - stop this file after NUM KB
                              files:NUM - stop after NUM files
                            packets:NUM - stop after NUM packets
Capture output:
  -b <ringbuffer opt.> ..., --ring-buffer <ringbuffer opt.>
                           duration:NUM - switch to next file after NUM secs
                           filesize:NUM - switch to next file after NUM KB
                              files:NUM - ringbuffer: replace after NUM files
                            packets:NUM - switch to next file after NUM packets
                           interval:NUM - switch to next file when the time is
                                          an exact multiple of NUM secs
Input file:
  -r <infile>, --read-file <infile>
                           set the filename to read from (no pipes or stdin!)

Processing:
  -R <read filter>, --read-filter <read filter>
                           packet filter in Wireshark display filter syntax
  -n                       disable all name resolutions (def: all enabled)
  -N <name resolve flags>  enable specific name resolution(s): "mnNtdv"
  -d <layer_type>==<selector>,<decode_as_protocol> ...
                           "Decode As", see the man page for details
                           Example: tcp.port==8888,http
  --enable-protocol <proto_name>
                           enable dissection of proto_name
  --disable-protocol <proto_name>
                           disable dissection of proto_name
  --enable-heuristic <short_name>
                           enable dissection of heuristic protocol
  --disable-heuristic <short_name>
                           disable dissection of heuristic protocol

User interface:
  -C <config profile>      start with specified configuration profile
  -H                       hide the capture info dialog during packet capture
  -Y <display filter>, --display-filter <display filter>
                           start with the given display filter
  -g <packet number>       go to specified packet number after "-r"
  -J <jump filter>         jump to the first packet matching the (display)
                           filter
  -j                       search backwards for a matching packet after "-J"
  -t a|ad|adoy|d|dd|e|r|u|ud|udoy
                           format of time stamps (def: r: rel. to first)
  -u s|hms                 output format of seconds (def: s: seconds)
  -X <key>:<value>         eXtension options, see man page for details
  -z <statistics>          show various statistics, see man page for details

Output:
  -w <outfile|->           set the output filename (or '-' for stdout)
  --capture-comment <comment>
                           add a capture file comment, if supported
  --temp-dir <directory>   write temporary files to this directory
                           (default: /tmp)

Diagnostic output:
  --log-level <level>      sets the active log level ("critical", "warning", etc.)
  --log-fatal <level>      sets level to abort the program ("critical" or "warning")
  --log-domains <[!]list>  comma separated list of the active log domains
  --log-debug <[!]list>    comma separated list of domains with "debug" level
  --log-noisy <[!]list>    comma separated list of domains with "noisy" level
  --log-file <path>        file to output messages to (in addition to stderr)

Miscellaneous:
  -h, --help               display this help and exit
  -v, --version            display version info and exit
  -P <key>:<path>          persconf:path - personal configuration files
                           persdata:path - personal data files
  -o <name>:<value> ...    override preference or recent setting
  -K <keytab>              keytab file to use for kerberos decryption
  --display <X display>    X display to use
  --fullscreen             start Wireshark in full screen
```

***

Updated on: 2023-Mar-08\


***
