---
description: >-
  GetAllUrls is an open-source command-line tool that extracts all URLs
  associated with a target domain. Its customization options and ability to
  detect hidden URLs make it useful for reconnaissance.
---

# 🔗 getallurls

GetAllUrls is a command-line tool that can be used for reconnaissance and information gathering during penetration testing and security assessments. The tool is designed to extract and gather all possible URLs that are associated with a target domain or website.

GetAllUrls uses various techniques to collect the URLs associated with a target domain, including scraping the website's content, analyzing JavaScript files, and brute-forcing directories and files. The tool can also detect subdomains associated with a target domain, which can provide valuable information for reconnaissance.

One of the key benefits of GetAllUrls is its ability to detect hidden or obscure URLs that may not be immediately visible on a website. This can include URLs that are not linked directly, but are embedded within the website's code, or URLs that are hidden behind authentication requirements.

GetAllUrls is also highly customizable, with a range of options for configuring its behavior and output. For example, it can be configured to output results in JSON or CSV format, and can be used in conjunction with other security tools to provide a more complete picture of a target domain.

Another benefit of GetAllUrls is its open-source nature, which means that it is freely available to download and use, and can be customized and modified by users to meet their specific needs. Additionally, the open-source nature of GetAllUrls means that it is continually being updated and improved by a large community of developers and security professionals.

In summary, GetAllUrls is a powerful command-line tool that can be used for reconnaissance and information gathering during penetration testing and security assessments. Its ability to detect hidden or obscure URLs and subdomains associated with a target domain make it a valuable tool for reconnaissance. Its customizability and open-source nature make it a valuable addition to any security toolkit.

### Packages and Binaries:

#### getallurls <a href="#getallurls" id="getallurls"></a>

This package contains getallurls (gau). It fetches known URLs from AlienVault’s Open Threat Exchange ([https://otx.alienvault.com](https://otx.alienvault.com/)), the Wayback Machine, and Common Crawl for any given domain. Inspired by Tomnomnom’s waybackurls.

**Installed size:** `6.42 MB`\
**How to install:** `sudo apt install getallurls`

<details>

<summary>Dependencies:</summary>

* libc6

</details>

**getallurls**

```
:~# getallurls -h
Usage of getallurls:
  -json
    	write output as json
  -o string
    	filename to write results to
  -p string
    	HTTP proxy to use
  -providers string
    	providers to fetch urls for (default "wayback,otx,commoncrawl")
  -random-agent
    	use random user-agent
  -retries uint
    	amount of retries for http client (default 5)
  -subs
    	include subdomains of target domain
  -v	enable verbose mode
  -version
    	show gau version
```

***

Updated on: 2022-Aug-05\


***
