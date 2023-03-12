---
description: >-
  Sherlock is a Python-based open-source security tool that automates the
  identification of usernames across websites and social media platforms.
---

# ℹ sherlock

Sherlock is an open-source tool designed for digital forensic investigation and penetration testing. It is used to identify potential security weaknesses and vulnerabilities in web applications, networks, and online accounts. The tool was developed by Rastamouse, a security researcher, and is written in Python.

The primary purpose of Sherlock is to help security analysts automate the process of searching for and identifying usernames and other sensitive information that may be exposed online. It works by using multiple APIs to search various websites and social media platforms for information related to a specific username or email address. Sherlock can be used for both offensive and defensive security purposes, allowing security analysts to identify potential attack vectors and improve the security posture of their organizations.

One of the primary features of Sherlock is its ability to scan multiple websites simultaneously, which can save a considerable amount of time when conducting a comprehensive security assessment. The tool also has the ability to search for and identify usernames across multiple social media platforms, including Twitter, Instagram, and LinkedIn. This information can be invaluable for identifying potential social engineering targets or for building a comprehensive profile of a target during an investigation.

One of the advantages of Sherlock is that it is highly customizable and can be easily modified to suit the specific needs of the user. The tool can be extended with custom modules, allowing security analysts to add new functionality or integrate with other security tools.

Overall, Sherlock is a powerful and versatile security tool that can be used for a wide range of security purposes, from identifying potential attack vectors to conducting comprehensive security assessments. Its open-source nature and customizable design make it a popular choice among security professionals and researchers. However, it should be noted that the use of Sherlock for offensive purposes may be illegal and is not recommended without the proper legal and ethical considerations.

### Packages and Binaries:

#### sherlock <a href="#sherlock" id="sherlock"></a>

This package contains a tool to find usernames across social networks.

**Installed size:** `158 KB`\
**How to install:** `sudo apt install sherlock`

<details>

<summary>Dependencies:</summary>

* python3
* python3-certifi
* python3-colorama
* python3-openpyxl
* python3-pandas
* python3-requests
* python3-requests-futures
* python3-socks
* python3-stem
* python3-torrequest

</details>

**sherlock**

```
:~# sherlock -h
usage: sherlock [-h] [--version] [--verbose] [--folderoutput FOLDEROUTPUT]
                [--output OUTPUT] [--tor] [--unique-tor] [--csv] [--xlsx]
                [--site SITE_NAME] [--proxy PROXY_URL] [--json JSON_FILE]
                [--timeout TIMEOUT] [--print-all] [--print-found] [--no-color]
                [--browse] [--local] [--nsfw]
                USERNAMES [USERNAMES ...]

Sherlock: Find Usernames Across Social Networks (Version 0.14.3)

positional arguments:
  USERNAMES             One or more usernames to check with social networks.
                        Check similar usernames using {%} (replace to '_',
                        '-', '.').

options:
  -h, --help            show this help message and exit
  --version             Display version information and dependencies.
  --verbose, -v, -d, --debug
                        Display extra debugging information and metrics.
  --folderoutput FOLDEROUTPUT, -fo FOLDEROUTPUT
                        If using multiple usernames, the output of the results
                        will be saved to this folder.
  --output OUTPUT, -o OUTPUT
                        If using single username, the output of the result
                        will be saved to this file.
  --tor, -t             Make requests over Tor; increases runtime; requires
                        Tor to be installed and in system path.
  --unique-tor, -u      Make requests over Tor with new Tor circuit after each
                        request; increases runtime; requires Tor to be
                        installed and in system path.
  --csv                 Create Comma-Separated Values (CSV) File.
  --xlsx                Create the standard file for the modern Microsoft
                        Excel spreadsheet (xslx).
  --site SITE_NAME      Limit analysis to just the listed sites. Add multiple
                        options to specify more than one site.
  --proxy PROXY_URL, -p PROXY_URL
                        Make requests over a proxy. e.g.
                        socks5://127.0.0.1:1080
  --json JSON_FILE, -j JSON_FILE
                        Load data from a JSON file or an online, valid, JSON
                        file.
  --timeout TIMEOUT     Time (in seconds) to wait for response to requests
                        (Default: 60)
  --print-all           Output sites where the username was not found.
  --print-found         Output sites where the username was found.
  --no-color            Don't color terminal output
  --browse, -b          Browse to all results on default browser.
  --local, -l           Force the use of the local data.json file.
  --nsfw                Include checking of NSFW sites from default list.
```

***

Updated on: 2023-Mar-08\


***
