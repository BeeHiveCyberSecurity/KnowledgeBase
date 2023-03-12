---
description: >-
  DNSRecon is a command-line tool for DNS reconnaissance, identifying DNS
  misconfigurations, vulnerabilities, zone transfers, and cache poisoning
  attempts.
---

# ℹ dnsrecon

DNSRecon is a powerful security tool that allows system administrators, network engineers, and security professionals to perform comprehensive reconnaissance of the Domain Name System (DNS). DNSRecon is a command-line tool that is designed to identify common DNS misconfigurations, vulnerabilities, and weaknesses that could be exploited by attackers to gain unauthorized access to a network.

DNSRecon is an open-source tool that is written in Python and is available for Linux and Windows platforms. It is a flexible tool that can be customized to suit the specific needs of the user. It is ideal for performing reconnaissance tasks such as enumerating DNS records, subdomains, and network hosts, as well as identifying DNS zone transfers and potential DNS cache poisoning attacks.

One of the key features of DNSRecon is its ability to perform DNS zone transfers. DNS zone transfers are a commonly used technique for gathering information about a target network. DNSRecon can perform zone transfers on all DNS servers that are authoritative for a domain, allowing it to build a comprehensive list of DNS records, subdomains, and network hosts.

Another important feature of DNSRecon is its ability to identify potential DNS cache poisoning attacks. DNS cache poisoning attacks are a serious threat to network security, as they can allow attackers to redirect users to malicious websites or steal sensitive information. DNSRecon can identify vulnerable DNS servers that are susceptible to cache poisoning attacks, allowing system administrators to take remedial action before an attack occurs.

DNSRecon also includes features for performing brute-force attacks against DNS servers to identify valid hostnames and subdomains. This can be useful for discovering hidden network resources that may not be listed in the public DNS records.

In addition to its reconnaissance capabilities, DNSRecon also includes a number of other features that can be used to enhance network security. These include the ability to perform DNS queries using specific DNS server addresses, the ability to perform reverse DNS lookups, and the ability to generate reports in various formats.

In conclusion, DNSRecon is a powerful and flexible security tool that can be used to perform comprehensive reconnaissance of the DNS. Its ability to identify common DNS misconfigurations, vulnerabilities, and weaknesses makes it an essential tool for any network security professional. Whether you are a system administrator, network engineer, or security professional, DNSRecon can help you to secure your network and protect against potential attacks.

### dnsrecon Usage Example <a href="#dnsrecon-usage-example" id="dnsrecon-usage-example"></a>

Scan a domain (`-d example.com`), use a dictionary to brute force hostnames (`-D /usr/share/wordlists/dnsmap.txt)`, do a standard scan (`-t std`), and save the output to a file (`–xml dnsrecon.xml`):

```
:~# dnsrecon -d example.com -D /usr/share/wordlists/dnsmap.txt -t std --xml dnsrecon.xml
[*] Performing General Enumeration of Domain:example.com
[*] DNSSEC is configured for example.com
[*] DNSKEYs:
```

***

\


### Packages and Binaries:

#### dnsrecon <a href="#dnsrecon" id="dnsrecon"></a>

DNSRecon is a Python script that provides the ability to perform:

* Check all NS Records for Zone Transfers.
* Enumerate General DNS Records for a given Domain (MX, SOA, NS, A, AAAA, SPF and TXT).
* Perform common SRV Record Enumeration.
* Top Level Domain (TLD) Expansion.
* Check for Wildcard Resolution.
* Brute Force subdomain and host A and AAAA records given a domain and a wordlist.
* Perform a PTR Record lookup for a given IP Range or CIDR.
* Check a DNS Server Cached records for A, AAAA and CNAME
* Records provided a list of host records in a text file to check.
* Enumerate Hosts and Subdomains using Google

**Installed size:** `1.40 MB`\
**How to install:** `sudo apt install dnsrecon`

<details>

<summary>Dependencies:</summary>

* python3
* python3-dnspython
* python3-lxml
* python3-netaddr

</details>

**dnsrecon**

DNS Enumeration and Scanning Tool

```
:~# dnsrecon -h
usage: dnsrecon [-h] [-d DOMAIN] [-n NS_SERVER] [-r RANGE] [-D DICTIONARY]
                [-f] [-a] [-s] [-b] [-y] [-k] [-w] [-z] [--threads THREADS]
                [--lifetime LIFETIME] [--tcp] [--db DB] [-x XML] [-c CSV]
                [-j JSON] [--iw] [--disable_check_recursion]
                [--disable_check_bindversion] [-V] [-v] [-t TYPE]

options:
  -h, --help            show this help message and exit
  -d DOMAIN, --domain DOMAIN
                        Target domain.
  -n NS_SERVER, --name_server NS_SERVER
                        Domain server to use. If none is given, the SOA of the target will be used. Multiple servers can be specified using a comma separated list.
  -r RANGE, --range RANGE
                        IP range for reverse lookup brute force in formats   (first-last) or in (range/bitmask).
  -D DICTIONARY, --dictionary DICTIONARY
                        Dictionary file of subdomain and hostnames to use for brute force.
  -f                    Filter out of brute force domain lookup, records that resolve to the wildcard defined IP address when saving records.
  -a                    Perform AXFR with standard enumeration.
  -s                    Perform a reverse lookup of IPv4 ranges in the SPF record with standard enumeration.
  -b                    Perform Bing enumeration with standard enumeration.
  -y                    Perform Yandex enumeration with standard enumeration.
  -k                    Perform crt.sh enumeration with standard enumeration.
  -w                    Perform deep whois record analysis and reverse lookup of IP ranges found through Whois when doing a standard enumeration.
  -z                    Performs a DNSSEC zone walk with standard enumeration.
  --threads THREADS     Number of threads to use in reverse lookups, forward lookups, brute force and SRV record enumeration.
  --lifetime LIFETIME   Time to wait for a server to respond to a query. default is 3.0
  --tcp                 Use TCP protocol to make queries.
  --db DB               SQLite 3 file to save found records.
  -x XML, --xml XML     XML file to save found records.
  -c CSV, --csv CSV     Save output to a comma separated value file.
  -j JSON, --json JSON  save output to a JSON file.
  --iw                  Continue brute forcing a domain even if a wildcard record is discovered.
  --disable_check_recursion
                        Disables check for recursion on name servers
  --disable_check_bindversion
                        Disables check for BIND version on name servers
  -V, --version         Show DNSrecon version
  -v, --verbose         Enable verbose
  -t TYPE, --type TYPE  Type of enumeration to perform.
                        Possible types:
                            std:      SOA, NS, A, AAAA, MX and SRV.
                            rvl:      Reverse lookup of a given CIDR or IP range.
                            brt:      Brute force domains and hosts using a given dictionary.
                            srv:      SRV records.
                            axfr:     Test all NS servers for a zone transfer.
                            bing:     Perform Bing search for subdomains and hosts.
                            yand:     Perform Yandex search for subdomains and hosts.
                            crt:      Perform crt.sh search for subdomains and hosts.
                            snoop:    Perform cache snooping against all NS servers for a given domain, testing
                                      all with file containing the domains, file given with -D option.
                        
                            tld:      Remove the TLD of given domain and test against all TLDs registered in IANA.
                            zonewalk: Perform a DNSSEC zone walk using NSEC records.
```

***

Updated on: 2022-Nov-16\


***
