---
description: >-
  Gobuster: open-source security tool for web app testing. Supports HTTP
  methods, directory/file brute-force attacks, custom wordlists, and HTTP
  authentication.
---

# 📈 gobuster

Gobuster is an open-source security tool designed for penetration testers, system administrators, and developers. The tool is widely used for identifying vulnerabilities and performing attacks on web applications. With its powerful features, Gobuster has become a popular tool in the information security industry.

Gobuster offers a simple and intuitive command-line interface that allows users to easily configure and run scans. It supports various HTTP methods, including GET, HEAD, and POST, and allows users to specify the parameters and payloads to use in their attacks. The tool also includes various plugins that can be used to extend its functionality, such as DNS resolution and SSL certificate verification.

One of the key features of Gobuster is its ability to perform directory and file brute-force attacks. This means that it can scan a web server for hidden files and directories that may contain sensitive information. Gobuster can also perform recursive scans, which means that it can follow directories and subdirectories to ensure that no files or directories are missed.

Gobuster also includes support for custom wordlists. This allows users to specify their own list of words to use in their brute-force attacks. The tool also includes a built-in list of common directories and files that can be used to quickly identify vulnerabilities.

In addition to its brute-force capabilities, Gobuster also includes support for HTTP authentication. This means that it can authenticate to a web server using various methods, including basic authentication and NTLM authentication. This feature can be useful for testing the security of web applications that require user authentication.

Overall, Gobuster is a powerful and versatile tool that can be used for a wide range of security testing tasks. Its simple and intuitive interface, combined with its powerful features, make it a popular choice among security professionals. Whether you are a penetration tester, system administrator, or developer, Gobuster is a must-have tool in your arsenal.

### gobuster Usage Examples <a href="#gobuster-usage-examples" id="gobuster-usage-examples"></a>

Scan a website (`-u http://192.168.0.155/`) for directories using a wordlist (`-w /usr/share/wordlists/dirb/common.txt`) and print the full URLs of discovered paths (`-e`):

```
:~# gobuster -e -u http://192.168.0.155/ -w /usr/share/wordlists/dirb/common.txt

Gobuster v1.2                OJ Reeves (@TheColonial)
=====================================================
[+] Mode         : dir
[+] Url/Domain   : http://192.168.0.155/
[+] Threads      : 10
[+] Wordlist     : /usr/share/wordlists/dirb/common.txt
[+] Status codes : 301,302,307,200,204
[+] Expanded     : true
=====================================================
http://192.168.0.155/blog (Status: 301)
http://192.168.0.155/index.html (Status: 200)
http://192.168.0.155/index (Status: 200)
http://192.168.0.155/photo (Status: 301)
http://192.168.0.155/wordpress (Status: 301)
=====================================================
```

***

\


### Packages and Binaries:

#### gobuster <a href="#gobuster" id="gobuster"></a>

Gobuster is a tool used to brute-force URIs including directories and files as well as DNS subdomains.

**Installed size:** `7.51 MB`\
**How to install:** `sudo apt install gobuster`

<details>

<summary>Dependencies:</summary>

* libc6

</details>

**gobuster**

```
:~# gobuster -h
Usage:
  gobuster [command]

Available Commands:
  completion  Generate the autocompletion script for the specified shell
  dir         Uses directory/file enumeration mode
  dns         Uses DNS subdomain enumeration mode
  fuzz        Uses fuzzing mode. Replaces the keyword FUZZ in the URL, Headers and the request body
  gcs         Uses gcs bucket enumeration mode
  help        Help about any command
  s3          Uses aws bucket enumeration mode
  tftp        Uses TFTP enumeration mode
  version     shows the current version
  vhost       Uses VHOST enumeration mode (you most probably want to use the IP address as the URL parameter)

Flags:
      --delay duration    Time each thread waits between requests (e.g. 1500ms)
  -h, --help              help for gobuster
      --no-color          Disable color output
      --no-error          Don't display errors
  -z, --no-progress       Don't display progress
  -o, --output string     Output file to write results to (defaults to stdout)
  -p, --pattern string    File containing replacement patterns
  -q, --quiet             Don't print the banner and other noise
  -t, --threads int       Number of concurrent threads (default 10)
  -v, --verbose           Verbose output (errors)
  -w, --wordlist string   Path to the wordlist

Use "gobuster [command] --help" for more information about a command.
```

***

Updated on: 2023-Mar-08\


***
