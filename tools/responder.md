---
description: >-
  Responder is an open-source security tool for detecting/responding to network
  attacks, with features like credential interception and MITM. Requires
  expertise.
---

# 🌐 responder

Responder is a powerful and open-source security tool designed for detecting and responding to network-based attacks. The tool is used for testing the security of various systems and services by simulating different attack scenarios.

Responder works by passively listening for traffic on the network and analyzing it for potential vulnerabilities. The tool can detect and respond to several types of attacks, including SMB relay, NTLMv1 and NTLMv2, HTTP and HTTPS, FTP and FTPS, and several others.

One of the main features of Responder is its ability to intercept and relay network traffic to authenticate credentials. This makes it a useful tool for capturing passwords, hashes, and other sensitive information. It can also be used to perform man-in-the-middle attacks, allowing an attacker to intercept and modify network traffic.

Responser is compatible with both Windows and Linux operating systems and can be run from a command-line interface. The tool has an extensive range of options and settings that allow users to customize it to their specific needs. The tool also supports various output formats, making it easy to integrate with other security tools and processes.

Despite its many capabilities, Responder is not a tool for novice users. Its complexity and power require a good understanding of networking and security concepts. Additionally, the tool can be used maliciously, making it important to use it responsibly and ethically.

In summary, Responder is a versatile and powerful security tool that can be used for detecting and responding to network-based attacks. Its ability to intercept and relay network traffic, authenticate credentials, and perform man-in-the-middle attacks make it a valuable tool for testing network security. However, it should be used responsibly and with caution by knowledgeable security professionals.

Specify the IP address to redirect to (`-i 192.168.1.202`), enabling the WPAD rogue proxy (`-w On`), answers for netbios wredir (`-r On`), and fingerprinting (`-f On`):

#### responder <a href="#responder" id="responder"></a>

This package contains Responder/MultiRelay, an LLMNR, NBT-NS and MDNS poisoner. It will answer to specific NBT-NS (NetBIOS Name Service) queries based on their name suffix (see: [http://support.microsoft.com/kb/163409)](http://support.microsoft.com/kb/163409\)). By default, the tool will only answer to File Server Service request, which is for SMB.

The concept behind this is to target your answers, and be stealthier on the network. This also helps to ensure that you don’t break legitimate NBT-NS behavior. You can set the -r option via command line if you want to answer to the Workstation Service request name suffix.

**Installed size:** `4.04 MB`\
**How to install:** `sudo apt install responder`

<details>

<summary>Dependencies:</summary>

* net-tools
* python3
* python3-netifaces
* python3-pkg-resources
* python3-pycryptodome
* python3-six

</details>

**responder**

```
:~# responder -h
                                         __
  .----.-----.-----.-----.-----.-----.--|  |.-----.----.
  |   _|  -__|__ --|  _  |  _  |     |  _  ||  -__|   _|
  |__| |_____|_____|   __|_____|__|__|_____||_____|__|
                   |__|

           NBT-NS, LLMNR & MDNS Responder 3.1.3.0

  To support this project:
  Patreon -> https://www.patreon.com/PythonResponder
  Paypal  -> https://paypal.me/PythonResponder

  Author: Laurent Gaffie ()
  To kill this script hit CTRL-C

Usage: responder -I eth0 -w -d
or:
responder -I eth0 -wd

Options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  -A, --analyze         Analyze mode. This option allows you to see NBT-NS,
                        BROWSER, LLMNR requests without responding.
  -I eth0, --interface=eth0
                        Network interface to use, you can use 'ALL' as a
                        wildcard for all interfaces
  -i 10.0.0.21, --ip=10.0.0.21
                        Local IP to use (only for OSX)
  -6 2002:c0a8:f7:1:3ba8:aceb:b1a9:81ed, --externalip6=2002:c0a8:f7:1:3ba8:aceb:b1a9:81ed
                        Poison all requests with another IPv6 address than
                        Responder's one.
  -e 10.0.0.22, --externalip=10.0.0.22
                        Poison all requests with another IP address than
                        Responder's one.
  -b, --basic           Return a Basic HTTP authentication. Default: NTLM
  -d, --DHCP            Enable answers for DHCP broadcast requests. This
                        option will inject a WPAD server in the DHCP response.
                        Default: False
  -D, --DHCP-DNS        This option will inject a DNS server in the DHCP
                        response, otherwise a WPAD server will be added.
                        Default: False
  -w, --wpad            Start the WPAD rogue proxy server. Default value is
                        False
  -u UPSTREAM_PROXY, --upstream-proxy=UPSTREAM_PROXY
                        Upstream HTTP proxy used by the rogue WPAD Proxy for
                        outgoing requests (format: host:port)
  -F, --ForceWpadAuth   Force NTLM/Basic authentication on wpad.dat file
                        retrieval. This may cause a login prompt. Default:
                        False
  -P, --ProxyAuth       Force NTLM (transparently)/Basic (prompt)
                        authentication for the proxy. WPAD doesn't need to be
                        ON. This option is highly effective. Default: False
  --lm                  Force LM hashing downgrade for Windows XP/2003 and
                        earlier. Default: False
  --disable-ess         Force ESS downgrade. Default: False
  -v, --verbose         Increase verbosity.
```

***

**responder-BrowserListener**

***

**responder-DHCP\_Auto**

***

**responder-FindSQLSrv**

***

**responder-Icmp-Redirect**

```
:~# responder-Icmp-Redirect -h
Usage: responder-Icmp-Redirect -I eth0 -i 10.20.30.40 -g 10.20.30.254 -t 10.20.30.48 -r 10.20.40.1

Options:
  -h, --help            show this help message and exit
  -i 10.20.30.40, --ip=10.20.30.40
                        The ip address to redirect the traffic to. (usually
                        yours)
  -g 10.20.30.254, --gateway=10.20.30.254
                        The ip address of the original gateway (issue the
                        command 'route -n' to know where is the gateway
  -t 10.20.30.48, --target=10.20.30.48
                        The ip address of the target
  -r 10.20.40.1, --route=10.20.40.1
                        The ip address of the destination target, example: DNS
                        server. Must be on another subnet.
  -s 10.20.40.1, --secondaryroute=10.20.40.1
                        The ip address of the destination target, example:
                        Secondary DNS server. Must be on another subnet.
  -I eth0, --interface=eth0
                        Interface name to use, example: eth0
  -a 10.20.30.40, --alternate=10.20.30.40
                        The alternate gateway, set this option if you wish to
                        redirect the victim traffic to another host than yours
```

***

**responder-MultiRelay**

```
:~# responder-MultiRelay -h
[!]MultiRelay/bin/ folder is empty. You need to run these commands:

apt-get install gcc-mingw-w64-x86-64
x86_64-w64-mingw32-gcc ./MultiRelay/bin/Runas.c -o ./MultiRelay/bin/Runas.exe -municode -lwtsapi32 -luserenv
x86_64-w64-mingw32-gcc ./MultiRelay/bin/Syssvc.c -o ./MultiRelay/bin/Syssvc.exe -municode

Additionally, you can add your custom mimikatz executables (mimikatz.exe and mimikatz_x86.exe)
in the MultiRelay/bin/ folder for the mimi32/mimi command.
```

***

**responder-RunFinger**

```
:~# responder-RunFinger -h
Usage: responder-RunFinger -i 10.10.10.224
or:
responder-RunFinger -i 10.10.10.0/24

Options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  -i 10.10.10.224, --ip=10.10.10.224
                        Target IP address or class C
  -f ips.txt, --filename=ips.txt
                        Target file
  -t 0.9, --timeout=0.9
                        Timeout for all connections. Use this option to fine
                        tune Runfinger.
```

***
