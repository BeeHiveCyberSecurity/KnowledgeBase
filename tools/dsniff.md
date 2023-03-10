---
description: >-
  dsniff: network security tool that intercepts/analyzes traffic,
  detects/prevents threats. Decryption, hijacking, DNS spoofing features.
---

# ℹ dsniff

dsniff is a powerful security tool that has been designed to help network administrators and security professionals detect, intercept and monitor network traffic. This tool can be used to identify vulnerabilities in the network and prevent attacks before they occur. dsniff can be installed on a variety of platforms, including Linux, macOS, and Windows.

The primary purpose of dsniff is to sniff network traffic and analyze it for potential security threats. It does this by intercepting packets that are sent over the network, and then analyzing the data contained within those packets. This analysis can be used to detect a variety of security issues, including passwords that are being sent in plain text, sensitive data that is being transmitted insecurely, and other vulnerabilities that could be exploited by hackers.

One of the key features of dsniff is its ability to detect and analyze encrypted traffic. This is achieved by using various techniques to decrypt the traffic, including man-in-the-middle (MITM) attacks, which involve intercepting and modifying the traffic in order to decrypt it. This can be especially useful when trying to identify security issues with secure protocols such as HTTPS or SSH.

In addition to its ability to analyze network traffic, dsniff also includes a number of other powerful features. For example, it can be used to perform DNS spoofing, which involves tricking a computer into connecting to a fake website or server by manipulating the DNS response. This can be used to steal login credentials or other sensitive data.

Another useful feature of dsniff is its ability to perform session hijacking. This involves intercepting a session between two computers and taking over the session in order to gain unauthorized access to the data being transmitted. This can be used to steal sensitive data or even take control of a remote computer.

Overall, dsniff is a powerful security tool that can be used to identify and prevent a wide range of security threats. It is easy to use and can be installed on a variety of platforms. Whether you are a network administrator, security professional, or simply concerned about the security of your network, dsniff is an excellent tool to have in your arsenal.

#### dsniff <a href="#dsniff" id="dsniff"></a>

This package contains several tools to listen to and create network traffic:

* arpspoof - Send out unrequested (and possibly forged) arp replies.
* dnsspoof - forge replies to arbitrary DNS address / pointer queries on the Local Area Network.
* dsniff - password sniffer for several protocols.
* filesnarf - saves selected files sniffed from NFS traffic.
* macof - flood the local network with random MAC addresses.
* mailsnarf - sniffs mail on the LAN and stores it in mbox format.
* msgsnarf - record selected messages from different Instant Messengers.
* sshmitm - SSH monkey-in-the-middle. proxies and sniffs SSH traffic.
* sshow - SSH traffic analyser.
* tcpkill - kills specified in-progress TCP connections.
* tcpnice - slow down specified TCP connections via “active” traffic shaping.
* urlsnarf - output selected URLs sniffed from HTTP traffic in CLF.
* webmitm - HTTP / HTTPS monkey-in-the-middle. transparently proxies.
* webspy - sends URLs sniffed from a client to your local browser (requires libx11-6 installed).

Please do not abuse this software.

**Installed size:** `430 KB`\
**How to install:** `sudo apt install dsniff`

<details>

<summary>Dependencies:</summary>

* libc6
* libdb5.3
* libnet1
* libnids1.21
* libpcap0.8
* libssl3
* libtirpc3
* libx11-6
* libxmu6
* openssl

</details>

**arpspoof**

Intercept packets on a switched LAN

```
:~# arpspoof --help
arpspoof: invalid option -- '-'
Version: 2.4
Usage: arpspoof [-i interface] [-c own|host|both] [-t target] [-r] host
```

***

**dnsspoof**

Forge replies to DNS address / pointer queries

```
:~# dnsspoof --help
dnsspoof: invalid option -- '-'
Version: 2.4
Usage: dnsspoof [-i interface] [-f hostsfile] [expression]
```

***

**dsniff**

Password sniffer

```
:~# dsniff --help
dsniff: invalid option -- '-'
Version: 2.4
Usage: dsniff [-cdmn] [-i interface | -p pcapfile] [-s snaplen]
              [-f services] [-t trigger[,...]] [-r|-w savefile]
              [expression]
```

***

**filesnarf**

Sniff files from NFS traffic

```
:~# filesnarf --help
filesnarf: invalid option -- '-'
Version: 2.4
Usage: filesnarf [-i interface | -p pcapfile] [[-v] pattern [expression]]
```

***

**macof**

Flood a switched LAN with random MAC addresses

```
:~# macof --help
macof: invalid option -- '-'
Version: 2.4
Usage: macof [-s src] [-d dst] [-e tha] [-x sport] [-y dport]
             [-i interface] [-n times]
```

***

**mailsnarf**

Sniff mail messages in Berkeley mbox format

```
:~# mailsnarf --help
mailsnarf: invalid option -- '-'
Version: 2.4
Usage: mailsnarf [-i interface | -p pcapfile] [[-v] pattern [expression]]
```

***

**msgsnarf**

Sniff chat messages

```
:~# msgsnarf --help
msgsnarf: invalid option -- '-'
Version: 2.4
Usage: msgsnarf [-i interface | -p pcapfile] [[-v] pattern [expression]]
```

***

**sshmitm**

SSH monkey-in-the-middle

```
:~# sshmitm --help
sshmitm: invalid option -- '-'
Version: 2.4
Usage: sshmitm [-d] [-I] [-p port] host [port]
```

***

**sshow**

SSH traffic analysis tool

```
:~# sshow --help
sshow: invalid option -- '-'
Usage: sshow [-d] [-i interface | -p pcapfile]
```

***

**tcpkill**

Kill TCP connections on a LAN

```
:~# tcpkill --help
tcpkill: invalid option -- '-'
Version: 2.4
Usage: tcpkill [-i interface] [-1..9] expression
```

***

**tcpnice**

Slow down TCP connections on a LAN

```
:~# tcpnice --help
tcpnice: invalid option -- '-'
Version: 2.4
Usage: tcpnice [-A] [-I] [-M] [-i interface] expression
```

***

**urlsnarf**

Sniff HTTP requests in Common Log Format

```
:~# urlsnarf --help
urlsnarf: invalid option -- '-'
Version: 2.4
Usage: urlsnarf [-n] [-i interface | -p pcapfile] [[-v] pattern [expression]]
```

***

**webmitm**

HTTP / HTTPS monkey-in-the-middle

```
:~# webmitm --help
webmitm: invalid option -- '-'
Version: 2.4
Usage: webmitm [-d] [host]
```

***

**webspy**

Display sniffed URLs in Netscape in real-time

```
:~# webspy --help
webspy: invalid option -- '-'
Version: 2.4
Usage: webspy [-i interface | -p pcapfile] host
```

***
