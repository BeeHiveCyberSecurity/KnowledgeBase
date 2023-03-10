---
description: >-
  Wifite automates wireless network security testing and identifying
  vulnerabilities. Fast and intuitive, ideal for network administrators and
  security professionals.
---

# 🎩 wifite

Wifite is a powerful security tool designed to test and secure wireless networks. It is a Python-based wireless auditing tool that enables security professionals and network administrators to automate the process of testing wireless network security, identify vulnerabilities and flaws, and enhance network security.

Wifite is designed to work with a variety of wireless network cards, and it supports both the 2.4GHz and 5GHz frequency bands. This flexibility ensures that network administrators can use the tool to test the security of a wide range of wireless networks, including those using the latest standards.

The tool is designed to make the wireless network auditing process as easy and straightforward as possible. With a simple and intuitive command-line interface, it enables users to configure and customize the testing process based on their specific needs. Wifite also supports a range of attack modes, including WPA, WEP, WPS, and WPA2, giving users the flexibility to test different aspects of wireless network security.

Wifite’s automated process allows it to crack WPA and WPA2 encrypted networks with a high success rate. Its ability to capture and decrypt wireless network traffic is one of its key features, making it an essential tool for detecting security flaws and vulnerabilities in wireless networks.

One of the biggest advantages of Wifite is that it is incredibly fast, thanks to its automated process. This means that network administrators and security professionals can perform thorough wireless network audits in a fraction of the time it would take to do so manually. The tool also allows for easy customization of the testing process, so users can choose which tests they want to perform, and how they want to perform them.

Overall, Wifite is an essential tool for network administrators and security professionals looking to test and secure wireless networks. Its easy-to-use interface, extensive feature set, and lightning-fast performance make it an ideal choice for anyone looking to enhance the security of their wireless networks.

### wifite Usage Example <a href="#wifite-usage-example" id="wifite-usage-example"></a>

Attack access points with over 50 dB of power (`-pow 50`) using the WPS attack (`-wps`):

```
:~# wifite -pow 50 -wps

  .;'                     `;,
 .;'  ,;'             `;,  `;,   WiFite v2 (r85)
.;'  ,;'  ,;'     `;,  `;,  `;,
::   ::   :   ( )   :   ::   ::  automated wireless auditor
':.  ':.  ':. /_\ ,:'  ,:'  ,:'
 ':.  ':.    /___\    ,:'  ,:'   designed for Linux
  ':.       /_____\      ,:'
           /       \

 [+] targeting WPS-enabled networks

 [+] scanning for wireless devices...
 [+] enabling monitor mode on wlan0... done
 [+] initializing scan (mon0), updates at 5 sec intervals, CTRL+C when ready.
```

***

\


### Packages and Binaries:

#### wifite <a href="#wifite" id="wifite"></a>

Wifite is a tool to audit WEP or WPA encrypted wireless networks. It uses aircrack-ng, pyrit, reaver, tshark tools to perform the audit.

This tool is customizable to be automated with only a few arguments and can be trusted to run without supervision.

**Installed size:** `2.34 MB`\
**How to install:** `sudo apt install wifite`

<details>

<summary>Dependencies:</summary>

* aircrack-ng
* ieee-data
* net-tools
* python3
* python3-chardet
* reaver
* tshark

</details>

**wifite**

Python script to automate wireless auditing using aircrack-ng tools

```
:~# wifite -h
   .               .    
 .´  ·  .     .  ·  `.  wifite2 2.6.6
 :  :  :  (¯)  :  :  :  a wireless auditor by derv82
 `.  ·  ` /¯\ ´  ·  .´  maintained by kimocoder
   `     /¯¯¯\     ´    https://github.com/kimocoder/wifite2

options:
  -h, --help                                 show this help message and exit

SETTINGS:
  -v, --verbose                              Shows more options (-h -v). Prints commands and outputs. (default:
                                             quiet)
  -i [interface]                             Wireless interface to use, e.g. wlan0mon (default: ask)
  -c [channel]                               Wireless channel to scan e.g. 1,3-6 (default: all 2Ghz channels)
  -inf, --infinite                           Enable infinite attack mode. Modify scanning time with -p (default:
                                             off)
  -mac, --random-mac                         Randomize wireless card MAC address (default: off)
  -p [scan_time]                             Pillage: Attack all targets after scan_time (seconds)
  --kill                                     Kill processes that conflict with Airmon/Airodump (default: off)
  -pow [min_power], --power [min_power]      Attacks any targets with at least min_power signal strength
  --skip-crack                               Skip cracking captured handshakes/pmkid (default: off)
  -first [attack_max], --first [attack_max]  Attacks the first attack_max targets
  -ic, --ignore-cracked                      Hides previously-cracked targets. (default: off)
  --clients-only                             Only show targets that have associated clients (default: off)
  --nodeauths                                Passive mode: Never deauthenticates clients (default: deauth targets)
  --daemon                                   Puts device back in managed mode after quitting (default: off)

WEP:
  --wep                                      Show only WEP-encrypted networks
  --require-fakeauth                         Fails attacks if fake-auth fails (default: off)
  --keep-ivs                                 Retain .IVS files and reuse when cracking (default: off)

WPA:
  --wpa                                      Show only WPA-encrypted networks (includes WPS)
  --new-hs                                   Captures new handshakes, ignores existing handshakes in hs (default:
                                             off)
  --dict [file]                              File containing passwords for cracking (default: /usr/share/dict/wordlist-
                                             probable.txt)

WPS:
  --wps                                      Show only WPS-enabled networks
  --wps-only                                 Only use WPS PIN & Pixie-Dust attacks (default:
                                             off)
  --bully                                    Use bully program for WPS PIN & Pixie-Dust attacks (default:
                                             reaver)
  --reaver                                   Use reaver program for WPS PIN & Pixie-Dust attacks (default:
                                             reaver)
  --ignore-locks                             Do not stop WPS PIN attack if AP becomes locked (default:
                                             stop)

PMKID:
  --pmkid                                    Only use PMKID capture, avoids other WPS & WPA attacks (default:
                                             off)
  --no-pmkid                                 Don't use PMKID capture (default: off)
  --pmkid-timeout [sec]                      Time to wait for PMKID capture (default: 300 seconds)

COMMANDS:
  --cracked                                  Print previously-cracked access points
  --check [file]                             Check a .cap file (or all hs/*.cap files) for WPA handshakes
  --crack                                    Show commands to crack a captured handshake
```

***

Updated on: 2022-Nov-16\


***
