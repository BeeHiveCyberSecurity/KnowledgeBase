---
description: >-
  Netcat is a versatile network utility used for port scanning, file transfer,
  remote shell access, and network troubleshooting, popular among security
  professionals and network engineers.
---

# 🌐 netcat

Netcat is a powerful and versatile network utility that can be used for a wide range of tasks such as port scanning, file transfer, and network troubleshooting. It is commonly referred to as the "Swiss Army Knife" of networking tools due to its extensive capabilities and ease of use.

Netcat was originally developed in 1995 by Hobbit, a member of the hacker group L0pht Heavy Industries. It was designed as a simple yet powerful networking tool that could be used to perform a variety of tasks, including file transfers, port scanning, and remote shell access. Since then, netcat has become a popular tool among security professionals, system administrators, and network engineers.

One of the most popular uses of netcat is for port scanning. This involves sending packets to a target system to identify open ports and services that may be vulnerable to attack. Netcat makes it easy to perform port scanning by allowing users to specify a range of ports to scan and providing a variety of options for customizing the scan.

Another popular use of netcat is for file transfers. Netcat can be used to send and receive files between two systems, making it a valuable tool for transferring data across a network or the internet. Netcat uses a simple command-line interface for file transfer, making it easy to use even for users with limited experience.

Netcat is also frequently used for remote shell access. This involves connecting to a remote system and executing commands as if you were sitting at the local console. Netcat provides a variety of options for connecting to a remote system, including TCP, UDP, and Unix sockets.

In addition to these core features, netcat also provides a variety of advanced options for network debugging and troubleshooting. For example, netcat can be used to simulate a variety of network protocols and services, allowing users to test the behavior of network applications and services without the need for specialized hardware or software.

Overall, netcat is a powerful and versatile network tool that is well-suited for a wide range of tasks, from simple port scanning and file transfers to advanced network troubleshooting and debugging. Its ease of use and extensive capabilities make it a valuable tool for security professionals, system administrators, and network engineers.

### Packages and Binaries:

#### netcat-traditional <a href="#netcat-traditional" id="netcat-traditional"></a>

A simple Unix utility which reads and writes data across network connections using TCP or UDP protocol. It is designed to be a reliable “back-end” tool that can be used directly or easily driven by other programs and scripts. At the same time it is a feature-rich network debugging and exploration tool, since it can create almost any kind of connection you would need and has several interesting built-in capabilities.

This is the “classic” netcat, written by _Hobbit_. It lacks many features found in netcat-openbsd.

**Installed size:** `143 KB`\
**How to install:** `sudo apt install netcat-traditional`

<details>

<summary>Dependencies:</summary>

* libc6

</details>

**nc.traditional**

TCP/IP swiss army knife

```
:~# nc.traditional -h
[v1.10-47]
connect to somewhere:	nc [-options] hostname port[s] [ports] ... 
listen for inbound:	nc -l -p port [-options] [hostname] [port]
options:
	-c shell commands	as `-e'; use /bin/sh to exec [dangerous!!]
	-e filename		program to exec after connect [dangerous!!]
	-b			allow broadcasts
	-g gateway		source-routing hop point[s], up to 8
	-G num			source-routing pointer: 4, 8, 12, ...
	-h			this cruft
	-i secs			delay interval for lines sent, ports scanned
        -k                      set keepalive option on socket
	-l			listen mode, for inbound connects
	-n			numeric-only IP addresses, no DNS
	-o file			hex dump of traffic
	-p port			local port number
	-r			randomize local and remote ports
	-q secs			quit after EOF on stdin and delay of secs
	-s addr			local source address
	-T tos			set Type Of Service
	-t			answer TELNET negotiation
	-u			UDP mode
	-v			verbose [use twice to be more verbose]
	-w secs			timeout for connects and final net reads
	-C			Send CRLF as line-ending
	-z			zero-I/O mode [used for scanning]
port numbers can be individual or ranges: lo-hi [inclusive];
hyphens in port names must be backslash escaped (e.g. 'ftp\-data').
```

***

Updated on: 2022-Nov-16\


***
