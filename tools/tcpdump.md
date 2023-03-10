# 🌐 tcpdump

### Packages and Binaries:

#### tcpdump <a href="#tcpdump" id="tcpdump"></a>

This program allows you to dump the traffic on a network. tcpdump is able to examine IPv4, ICMPv4, IPv6, ICMPv6, UDP, TCP, SNMP, AFS BGP, RIP, PIM, DVMRP, IGMP, SMB, OSPF, NFS and many other packet types.

It can be used to print out the headers of packets on a network interface, filter packets that match a certain expression. You can use this tool to track down network problems, to detect attacks or to monitor network activities.

**Installed size:** `1.30 MB`\
**How to install:** `sudo apt install tcpdump`

<details>

<summary>Dependencies:</summary>

* adduser
* libc6
* libpcap0.8
* libssl3

</details>

**tcpdump**

Dump traffic on a network

```
:~# tcpdump -h
tcpdump version 4.99.3
libpcap version 1.10.3 (with TPACKET_V3)
OpenSSL 3.0.8 7 Feb 2023
Usage: tcpdump [-AbdDefhHIJKlLnNOpqStuUvxX#] [ -B size ] [ -c count ] [--count]
		[ -C file_size ] [ -E algo:secret ] [ -F file ] [ -G seconds ]
		[ -i interface ] [ --immediate-mode ] [ -j tstamptype ]
		[ -M secret ] [ --number ] [ --print ] [ -Q in|out|inout ]
		[ -r file ] [ -s snaplen ] [ -T type ] [ --version ]
		[ -V file ] [ -w file ] [ -W filecount ] [ -y datalinktype ]
		[ --time-stamp-precision precision ] [ --micro ] [ --nano ]
		[ -z postrotate-command ] [ -Z user ] [ expression ]
```

***

Updated on: 2023-Mar-08\


***
