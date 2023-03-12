---
description: >-
  TCPdump is a powerful open-source network protocol analyzer that captures and
  analyzes network traffic in real-time, useful for network troubleshooting and
  security threat detection.
---

# 🌐 tcpdump

TCPdump is a powerful and widely-used command-line network sniffer tool that is capable of capturing and analyzing network traffic in real-time. It is an open-source network protocol analyzer that runs on various Unix-like operating systems such as Linux, FreeBSD, and macOS. TCPdump captures network packets and displays their contents in a human-readable format.

TCPdump is a highly useful security tool for network administrators and security professionals to detect and troubleshoot network issues, including network intrusion attempts and malware infections. By capturing and analyzing network packets, TCPdump can provide valuable insight into the behavior of network traffic and help identify any abnormal or suspicious activity.

TCPdump works by listening on a designated network interface, such as an Ethernet card or a Wi-Fi adapter, for incoming and outgoing network traffic. It captures all network packets that match the specified filter criteria, which can include protocol types, source and destination IP addresses, port numbers, and more. The captured packets can be saved to a file for later analysis, or analyzed in real-time using TCPdump's command-line interface.

TCPdump's output includes a wealth of information about each captured packet, such as the source and destination IP addresses and port numbers, protocol type, packet size, and packet content. The output can also be customized using various command-line options to filter and format the captured packets according to specific requirements.

TCPdump is an invaluable tool for network troubleshooting and analysis, as well as for detecting and mitigating network security threats. For example, it can be used to monitor network traffic for signs of network attacks such as port scanning, denial of service attacks, and intrusion attempts. It can also help identify malware infections by detecting suspicious network activity or communications with known malicious hosts.

TCPdump's flexibility and power come at the cost of a steep learning curve, however. Users must have a solid understanding of network protocols and packet analysis to make the most of this tool. Additionally, since TCPdump captures all network traffic that matches the specified filter criteria, it can generate large amounts of data that can be difficult to manage and analyze.

In conclusion, TCPdump is a highly effective and versatile network protocol analyzer that provides valuable insights into network traffic and helps detect and mitigate security threats. It is a must-have tool for network administrators and security professionals, but it requires a certain level of expertise to use effectively. With the right training and experience, however, TCPdump can be an invaluable asset in any network security toolkit.

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
