# ℹ subfinder

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
