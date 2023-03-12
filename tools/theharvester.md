---
description: >-
  TheHarvester: automated reconnaissance tool for gathering intel on targets via
  public/private data sources. Flexible and user-friendly.
---

# ℹ theharvester

TheHarvester is a powerful security tool designed to help individuals and organizations gather valuable intelligence from a variety of sources. Whether you're a security professional, a researcher, or just someone who wants to keep an eye on potential threats, TheHarvester can help you find the information you need to stay informed and protected.

At its core, TheHarvester is a reconnaissance tool that leverages a variety of public and private data sources to gather information about a specific target. This information can include email addresses, domain names, IP addresses, and other details that can be used to map out a target's online footprint and identify potential vulnerabilities.

One of the key strengths of TheHarvester is its ability to automate much of the data gathering process. Using a combination of search engine queries, DNS lookups, and other techniques, TheHarvester can quickly and efficiently gather a wealth of information about a target with minimal effort on the part of the user.

Another advantage of TheHarvester is its flexibility. The tool is highly customizable, allowing users to fine-tune their searches and select specific data sources to query. This can be particularly useful for researchers or security professionals who need to gather information from niche sources or who want to focus their efforts on specific areas of interest.

Despite its power and flexibility, TheHarvester is also incredibly user-friendly. The tool features a simple and intuitive interface that makes it easy for even novice users to get started. And with detailed documentation and a supportive user community, help is always available for those who need it.

Of course, like any security tool, TheHarvester is only as effective as the user who wields it. But with its powerful features, flexible options, and user-friendly interface, TheHarvester is a valuable addition to any security toolkit. Whether you're looking to gather intelligence on potential threats or simply keep tabs on your own online presence, TheHarvester can help you stay one step ahead of the game.

### theharvester Usage Example <a href="#theharvester-usage-example" id="theharvester-usage-example"></a>

Search from email addresses from a domain (`-d kali.org`), limiting the results to 500 (`-l 500`), using Google (`-b google`):

```
:~# theharvester -d kali.org -l 500 -b google

*******************************************************************
*                                                                 *
* | |_| |__   ___    /\  /\__ _ _ ____   _____  ___| |_ ___ _ __  *
* | __| '_ \ / _ \  / /_/ / _` | '__\ \ / / _ \/ __| __/ _ \ '__| *
* | |_| | | |  __/ / __  / (_| | |   \ V /  __/\__ \ ||  __/ |    *
*  \__|_| |_|\___| \/ /_/ \__,_|_|    \_/ \___||___/\__\___|_|    *
*                                                                 *
* TheHarvester Ver. 3.0.0                                         *
* Coded by Christian Martorella                                   *
* Edge-Security Research                                          *
*                                    *
*******************************************************************


[-] Starting harvesting process for domain: kali.org

[-] Searching in Google:
    Searching 0 results...
    Searching 100 results...
    Searching 200 results...
    Searching 300 results...
    Searching 400 results...
    Searching 500 results...

 Harvesting results
[...]
```

***

\


### Packages and Binaries:

#### theharvester <a href="#theharvester" id="theharvester"></a>

The package contains a tool for gathering subdomain names, e-mail addresses, virtual hosts, open ports/ banners, and employee names from different public sources (search engines, pgp key servers).

**Installed size:** `1.72 MB`\
**How to install:** `sudo apt install theharvester`

<details>

<summary>Dependencies:</summary>

* kali-defaults
* python3
* python3-aiodns
* python3-aiofiles
* python3-aiohttp
* python3-aiomultiprocess
* python3-aiosqlite
* python3-bs4
* python3-censys
* python3-certifi
* python3-dnspython
* python3-fastapi
* python3-lxml
* python3-netaddr
* python3-pyppeteer
* python3-requests
* python3-retrying
* python3-shodan
* python3-slowapi
* python3-starlette
* python3-texttable
* python3-ujson
* python3-uvicorn
* python3-uvloop
* python3-yaml

</details>

**restfulHarvest**

```
:~# restfulHarvest -h
usage: restfulHarvest [-h] [-H HOST] [-p PORT] [-l LOG_LEVEL] [-r]

options:
  -h, --help            show this help message and exit
  -H HOST, --host HOST  IP address to listen on default is 127.0.0.1
  -p PORT, --port PORT  Port to bind the web server to, default is 5000
  -l LOG_LEVEL, --log-level LOG_LEVEL
                        Set logging level, default is info but
                        [critical|error|warning|info|debug|trace] can be set
  -r, --reload          Enable automatic reload used during development of the
                        api
```

***

**theHarvester**

```
:~# theHarvester -h
*******************************************************************
*  _   _                                            _             *
* | |_| |__   ___    /\  /\__ _ _ ____   _____  ___| |_ ___ _ __  *
* | __|  _ \ / _ \  / /_/ / _` | '__\ \ / / _ \/ __| __/ _ \ '__| *
* | |_| | | |  __/ / __  / (_| | |   \ V /  __/\__ \ ||  __/ |    *
*  \__|_| |_|\___| \/ /_/ \__,_|_|    \_/ \___||___/\__\___|_|    *
*                                                                 *
* theHarvester 4.2.0                                              *
* Coded by Christian Martorella                                   *
* Edge-Security Research                                          *
*                                    *
*                                                                 *
*******************************************************************
usage: theHarvester [-h] -d DOMAIN [-l LIMIT] [-S START] [-p] [-s]
                    [--screenshot SCREENSHOT] [-v] [-e DNS_SERVER] [-r] [-n]
                    [-c] [-f FILENAME] [-b SOURCE]

theHarvester is used to gather open source intelligence (OSINT) on a company
or domain.

options:
  -h, --help            show this help message and exit
  -d DOMAIN, --domain DOMAIN
                        Company name or domain to search.
  -l LIMIT, --limit LIMIT
                        Limit the number of search results, default=500.
  -S START, --start START
                        Start with result number X, default=0.
  -p, --proxies         Use proxies for requests, enter proxies in
                        proxies.yaml.
  -s, --shodan          Use Shodan to query discovered hosts.
  --screenshot SCREENSHOT
                        Take screenshots of resolved domains specify output
                        directory: --screenshot output_directory
  -v, --virtual-host    Verify host name via DNS resolution and search for
                        virtual hosts.
  -e DNS_SERVER, --dns-server DNS_SERVER
                        DNS server to use for lookup.
  -r, --take-over       Check for takeovers.
  -n, --dns-lookup      Enable DNS server lookup, default False.
  -c, --dns-brute       Perform a DNS brute force on the domain.
  -f FILENAME, --filename FILENAME
                        Save the results to an XML and JSON file.
  -b SOURCE, --source SOURCE
                        anubis, baidu, bevigil, binaryedge, bing, bingapi,
                        bufferoverun, censys, certspotter, crtsh, dnsdumpster,
                        duckduckgo, fullhunt, github-code, hackertarget,
                        hunter, intelx, omnisint, otx, pentesttools,
                        projectdiscovery, qwant, rapiddns, rocketreach,
                        securityTrails, sublist3r, threatcrowd, threatminer,
                        urlscan, virustotal, yahoo, zoomeye
```

***

**theharvester**

```
:~# theharvester -h
┏━(Message from Kali developers)
┃
┃ The command theharvester is deprecated. Please use theHarvester instead.
┃
┗━
```

***

Updated on: 2022-Nov-16\


***
