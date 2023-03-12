---
description: >-
  Subfinder is a fast, flexible, and customizable security tool that identifies
  subdomains associated with a domain name, enhancing network security.
---

# ℹ subfinder

Subfinder is a powerful security tool designed to help you discover subdomains associated with a given domain name. With its intuitive and user-friendly interface, subfinder is the ideal tool for both novice and experienced security professionals who want to identify potential vulnerabilities in their network infrastructure.

Subdomains are an essential aspect of any domain, and they can be used to provide access to different parts of a website or network. However, subdomains can also be used to bypass security measures and gain unauthorized access to sensitive information. Subfinder allows you to quickly and easily identify all subdomains associated with a particular domain name, allowing you to take the necessary steps to secure your network and protect your valuable data.

Subfinder is a versatile and flexible tool that can be customized to meet your specific needs. Whether you are looking for all subdomains associated with a domain name or just a specific set of subdomains, subfinder can help you get the job done. The tool offers a wide range of customization options, including the ability to specify the number of concurrent threads to use, the timeout for each request, and the ability to exclude specific subdomains from the search.

With its fast and reliable performance, subfinder can quickly scan large sets of domains and subdomains, making it ideal for use in both small and large-scale security operations. The tool's intuitive interface and detailed reporting make it easy to understand the results of your scans, allowing you to quickly identify potential security risks and take the necessary steps to protect your network.

In addition to its powerful scanning capabilities, subfinder also offers a range of advanced features to help you fine-tune your security efforts. The tool includes support for a wide range of DNS resolvers, allowing you to optimize your scans for speed and accuracy. It also includes support for multiple output formats, including CSV, JSON, and XML, making it easy to integrate the tool into your existing security workflows.

Overall, subfinder is an essential tool for any security professional looking to enhance their network security and protect their valuable data. With its powerful scanning capabilities, flexible customization options, and advanced features, subfinder is the ultimate tool for identifying potential security risks and taking proactive measures to keep your network secure.

### Packages and Binaries:

#### subfinder <a href="#subfinder" id="subfinder"></a>

This package contains a subdomain discovery tool that discovers valid subdomains for websites by using passive online sources. It has a simple modular architecture and is optimized for speed. subfinder is built for doing one thing only - passive subdomain enumeration, and it does that very well.

**Installed size:** `9.62 MB`\
**How to install:** `sudo apt install subfinder`

<details>

<summary>Dependencies:</summary>

* libc6

</details>

**subfinder**

```
:~# subfinder -h
Usage of subfinder:
  -cd
    	Upload results to the Chaos API (api-key required)
  -config string
    	Configuration file for API Keys, etc (default "/root/.config/subfinder/config.yaml")
  -d string
    	Domain to find subdomains for
  -dL string
    	File containing list of domains to enumerate
  -exclude-sources string
    	List of sources to exclude from enumeration
  -ls
    	List all available sources
  -max-time int
    	Minutes to wait for enumeration results (default 10)
  -nC
    	Don't Use colors in output
  -nW
    	Remove Wildcard & Dead Subdomains from output
  -o string
    	File to write output to (optional)
  -oD string
    	Directory to write enumeration results to (optional)
  -oI
    	Write output in Host,IP format
  -oJ
    	Write output in JSON lines Format
  -r string
    	Comma-separated list of resolvers to use
  -rL string
    	Text file containing list of resolvers to use
  -silent
    	Show only subdomains in output
  -sources string
    	Comma separated list of sources to use
  -t int
    	Number of concurrent goroutines for resolving (default 10)
  -timeout int
    	Seconds to wait before timing out (default 30)
  -v	Show Verbose output
  -version
    	Show version of subfinder
```

***

Updated on: 2022-Aug-05\


***
