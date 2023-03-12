---
description: >-
  Bettercap is a Swiss Army knife for network attacks and monitoring. It enables
  attackers to perform various tasks, such as sniffing and spoofing.
---

# 🌐 bettercap

Bettercap is a versatile and powerful open-source security tool that is used by security professionals to test network security and perform security assessments. It is built on top of the popular packet sniffing and manipulation tool, libpcap, and provides a modular framework that enables developers to create their own plugins or modules to extend its functionality.

Bettercap can be used to perform various types of network attacks and analyze network traffic. Its features include network sniffing, ARP spoofing, DNS spoofing, SSL stripping, session hijacking, and packet injection capabilities. With these features, Bettercap can be used to detect and intercept network traffic, spoof network traffic, and inject arbitrary packets into the network.

One of the primary uses of Bettercap is for penetration testing and vulnerability assessment. It can be used to detect vulnerabilities in network devices, services, and applications, as well as to test the effectiveness of security controls such as firewalls, intrusion detection systems, and antivirus software. It can also be used to simulate attacks and test the effectiveness of security incident response plans.

Another use case for Bettercap is for network monitoring and troubleshooting. It can be used to analyze network traffic and identify performance issues, network bottlenecks, and other network-related problems. It can also be used to monitor network activity and detect unusual or malicious behavior.

Bettercap is available for Linux, macOS, and Windows platforms, and can be installed using package managers such as apt, homebrew, or chocolatey, or directly from the source code on GitHub. It has a command-line interface and supports a wide range of network protocols, including ARP, DNS, DHCP, HTTP, and others.

While Bettercap is a powerful tool for testing network security, it can also be used maliciously. Therefore, it should only be used by authorized personnel who have obtained the necessary permissions to perform security assessments or penetration testing. Additionally, it is important to use Bettercap in a responsible and ethical manner and to respect the privacy and security of others.

### bettercap Usage Example <a href="#bettercap-usage-example" id="bettercap-usage-example"></a>

Scan the system in quiet mode (`-Q`) and output in cronjob format (`–cronjob`):

```
:~# bettercap
bettercap v2.11 (type 'help' for a list of commands)

172.16.10.0/24 > 172.16.10.212  » [12:34:15] [endpoint.new] endpoint 172.16.10.254 detected as 00:50:56:01:33:70 (VMware, Inc.).
172.16.10.0/24 > 172.16.10.212  » help

           help MODULE : List available commands or show module specific help if no module name is provided.
                active : Show information about active modules.
                  quit : Close the session and exit.
         sleep SECONDS : Sleep for the given amount of seconds.
              get NAME : Get the value of variable NAME, use * alone for all, or NAME* as a wildcard.
        set NAME VALUE : Set the VALUE of variable NAME.
  read VARIABLE PROMPT : Show a PROMPT to ask the user for input that will be saved inside VARIABLE.
                 clear : Clear the screen.
        include CAPLET : Load and run this caplet in the current session.
             ! COMMAND : Execute a shell command and print its output.
        alias MAC NAME : Assign an alias to a given endpoint given its MAC address.

Modules

      any.proxy > not running
       api.rest > not running
      arp.spoof > not running
      ble.recon > not running
        caplets > not running
    dhcp6.spoof > not running
      dns.spoof > not running
  events.stream > running
            gps > not running
     http.proxy > not running
    http.server > not running
    https.proxy > not running
    mac.changer > not running
   mysql.server > not running
      net.probe > not running
      net.recon > running
      net.sniff > not running
   packet.proxy > not running
       syn.scan > not running
      tcp.proxy > not running
         ticker > not running
         update > not running
           wifi > not running
            wol > not running

172.16.10.0/24 > 172.16.10.212  » net.show

+-----------------+--------------------+----------+-------------------------+---------+---------+------------+
|       IP        |        MAC         |  Name    |         Vendor          | Sent    | Recvd  | Last Seen  |
+-----------------+--------------------+----------+-------------------------+---------+---------+------------+
| 172.16.10.212   | 00:b0:52:af:4a:50  | eth0     | Atheros Communications  | 0 B     | 0 B     | 12:34:15   |
| 172.16.10.2     | 00:50:56:13:37:0a  | gateway  | VMware, Inc.            | 49 kB   | 20 kB   | 12:34:15   |
|                 |                    |          |                         |         |         |            |
| 172.16.10.254   | 00:50:56:01:33:70  |          | VMware, Inc.            | 2.4 kB  | 2.4 kB  | 12:35:15   |
+-----------------+--------------------+----------+-------------------------+---------+---------+------------+

↑ 0 B / ↓ 3.2 MB / 11354 pkts / 0 errs
```

***

\


### Packages and Binaries:

#### bettercap <a href="#bettercap" id="bettercap"></a>

The Swiss Army knife for 802.11, BLE, IPv4 and IPv6 networks reconnaissance and MITM attacks.

bettercap is a powerful, easily extensible and portable framework written in Go which aims to offer to security researchers, red teamers and reverse engineers an easy to use, all-in-one solution with all the features they might possibly need for performing reconnaissance and attacking WiFi networks, Bluetooth Low Energy devices, wireless HID devices and Ethernet networks.

Main Features:

* WiFi networks scanning, deauthentication attack, clientless PMKID association attack and automatic WPA/WPA2 client handshakes capture.
* Bluetooth Low Energy devices scanning, characteristics enumeration, reading and writing.
* 2.4Ghz wireless devices scanning and MouseJacking attacks with over-the-air HID frames injection (with DuckyScript support).
* Passive and active IP network hosts probing and recon.
* ARP, DNS, NDP and DHCPv6 spoofers for MITM attacks on IPv4 and IPv6 based networks.
* Proxies at packet level, TCP level and HTTP/HTTPS application level fully scriptable with easy to implement javascript plugins.
* A powerful network sniffer for credentials harvesting which can also be used as a network protocol fuzzer.
* A very fast port scanner.
* A powerful REST API with support for asynchronous events notification on websocket to orchestrate your attacks easily.
* A very convenient web UI.
* More! ([https://www.bettercap.org/modules/](https://www.bettercap.org/modules/))

This package contains a Swiss Army knife for 802.11, BLE and Ethernet networks reconnaissance and attacks.

**Installed size:** `24.05 MB`\
**How to install:** `sudo apt install bettercap`

<details>

<summary>Dependencies:</summary>

* ca-certificates
* iproute2
* iptables
* iw
* libc6
* libnetfilter-queue1
* libpcap0.8
* libusb-1.0-0

</details>

**bettercap**

```
:~# bettercap -h
Usage of bettercap:
  -autostart string
    	Comma separated list of modules to auto start. (default "events.stream")
  -caplet string
    	Read commands from this file and execute them in the interactive session.
  -caplets-path string
    	Specify an alternative base path for caplets.
  -cpu-profile file
    	Write cpu profile file.
  -debug
    	Print debug messages.
  -env-file string
    	Load environment variables from this file if found, set to empty to disable environment persistence.
  -eval string
    	Run one or more commands separated by ; in the interactive session, used to set variables via command line.
  -gateway-override string
    	Use the provided IP address instead of the default gateway. If not specified or invalid, the default gateway will be used.
  -iface string
    	Network interface to bind to, if empty the default interface will be auto selected.
  -mem-profile file
    	Write memory profile to file.
  -no-colors
    	Disable output color effects.
  -no-history
    	Disable interactive session history file.
  -pcap-buf-size int
    	PCAP buffer size, leave to 0 for the default value. (default -1)
  -script string
    	Load a session script.
  -silent
    	Suppress all logs which are not errors.
  -version
    	Print the version and exit.
```

***

Updated on: 2023-Mar-08\


***
