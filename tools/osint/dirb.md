---
description: >-
  Dirb is a command-line security tool for finding hidden web pages and
  directories by performing a dictionary-based brute-force attack.
---

# ℹ dirb

Dirb is an open-source web application scanner that is used for testing the security of web applications by identifying hidden web pages and directories. It is a command-line tool that can be used to perform various tests on a web server, such as detecting directories, guessing filenames, and finding sensitive files. The tool is very popular in the cybersecurity community and is widely used by security professionals and penetration testers to find potential vulnerabilities in web applications.

The main purpose of Dirb is to perform a dictionary-based brute-force attack on a web server. It works by sending a request to the server for each item in a given wordlist and analyzing the response. This process helps to identify hidden directories, files, and web pages that are not visible to normal users. The wordlist used by Dirb contains a list of common words and phrases that are typically used in web application URLs. By using this list, Dirb can effectively guess the location of sensitive files and directories.

Dirb has a user-friendly interface that is easy to use, and it supports multiple scanning modes such as recursive and non-recursive scanning. The recursive scanning mode allows Dirb to search for directories and files within subdirectories, while the non-recursive scanning mode only scans the specified directory. This feature is useful for detecting vulnerabilities in large web applications with multiple layers of directories and files.

Dirb also has advanced features like HTTP and HTTPS proxy support, custom headers, and cookies. These features are useful for testing web applications that require authentication or are behind a firewall. Dirb can be used to test for common vulnerabilities such as SQL injection, cross-site scripting (XSS), and file inclusion vulnerabilities.

One of the advantages of Dirb is that it is lightweight and does not require any installation. It is also compatible with multiple operating systems like Linux, Windows, and macOS. Dirb has a high level of accuracy and can quickly detect hidden web pages and directories. This makes it a valuable tool for penetration testers and security professionals who need to identify potential vulnerabilities in web applications.

However, Dirb is not perfect, and it has some limitations. For example, it cannot detect vulnerabilities that require complex input or cannot be guessed by using a wordlist. It is also not effective against web applications that use advanced security measures like CAPTCHA and two-factor authentication.

In conclusion, Dirb is a powerful security tool that can be used to detect hidden web pages and directories in web applications. It is easy to use, lightweight, and has multiple scanning modes and advanced features that make it a valuable tool for security professionals and penetration testers. However, it has some limitations, and it should be used in combination with other security tools for a comprehensive security assessment of web applications.

### dirb Usage Example <a href="#dirb-usage-example" id="dirb-usage-example"></a>

Scan the web server (`http://192.168.1.224/`) for directories using a dictionary file (`/usr/share/wordlists/dirb/common.txt`):

```
:~# dirb http://192.168.1.224/ /usr/share/wordlists/dirb/common.txt

-----------------
DIRB v2.21
By The Dark Raver
-----------------

START_TIME: Fri May 16 13:41:45 2014
URL_BASE: http://192.168.1.224/
WORDLIST_FILES: /usr/share/wordlists/dirb/common.txt

-----------------

GENERATED WORDS: 4592

---- Scanning URL: http://192.168.1.224/ ----
==> DIRECTORY: http://192.168.1.224/.svn/
+ http://192.168.1.224/.svn/entries (CODE:200|SIZE:2726)
+ http://192.168.1.224/cgi-bin/ (CODE:403|SIZE:1122)
==> DIRECTORY: http://192.168.1.224/config/
==> DIRECTORY: http://192.168.1.224/docs/
==> DIRECTORY: http://192.168.1.224/external/
```

***

\


### Packages and Binaries:

#### dirb <a href="#dirb" id="dirb"></a>

DIRB is a Web Content Scanner. It looks for existing (and/or hidden) Web Objects. It basically works by launching a dictionary based attack against a web server and analyzing the responses.

DIRB comes with a set of preconfigured attack wordlists for easy usage but you can use your custom wordlists. Also DIRB sometimes can be used as a classic CGI scanner, but remember that it is a content scanner not a vulnerability scanner.

DIRB’s main purpose is to help in professional web application auditing. Specially in security related testing. It covers some holes not covered by classic web vulnerability scanners. DIRB looks for specific web objects that other generic CGI scanners can’t look for. It doesn’t search vulnerabilities nor does it look for web contents that can be vulnerable.

**Installed size:** `1.43 MB`\
**How to install:** `sudo apt install dirb`

<details>

<summary>Dependencies:</summary>

* libc6
* libcurl4

</details>

**dirb**

Web Content Scanner

```
:~# man dirb
DIRB(1)                     General Commands Manual                    DIRB(1)

NAME
       dirb - Web Content Scanner

SYNOPSIS
       dirb <url_base> <url_base> [<wordlist_file(s)>] [options]

DESCRIPTION
       DIRB  IS  a  Web Content Scanner. It looks for existing (and/or hidden)
       Web Objects. It basically works by launching a dictionary basesd attack
       against a web server and analizing the response.

OPTIONS
       -a <agent_string>
                Specify  your  custom  USER_AGENT.   (Default is: "Mozilla/4.0
              (compatible; MSIE 6.0; Windows NT 5.1)")

       -b      Don't squash or merge sequences of /../ or  /./  in  the  given
              URL.

       -c <cookie_string>
               Set a cookie for the HTTP request.

       -E <certificate>
               Use the specified client certificate file.

       -f      Fine tunning of NOT_FOUND (404) detection.

       -H <header_string>
               Add a custom header to the HTTP request.

       -i      Use case-insensitive Search.

       -l      Print "Location" header when found.

       -N <nf_code>
               Ignore responses with this HTTP code.

       -o <output_file>
               Save output to disk.

       -p <proxy[:port]>
               Use this proxy. (Default port is 1080)

       -P <proxy_username:proxy_password>
               Proxy Authentication.

       -r      Don't Search Recursively.

       -R       Interactive  Recursion.  (Ask in which directories you want to
              scan)

       -S      Silent Mode. Don't show tested words. (For dumb terminals)

       -t      Don't force an ending '/' on URLs.

       -u <username:password>
               Username and password to use.

       -v      Show Also Not Existent Pages.

       -w      Don't Stop on WARNING messages.

       -x <extensions_file>
               Amplify search with the extensions on this file.

       -X <extensions>
               Amplify search with this extensions.

       -z <milisecs>
               Amplify search with this extensions.

SEE ALSO
       brain(x)

The Dark Raver                    27/01/2009                           DIRB(1)
```

***

**dirb-gendict**

Generate dictionary incrementally

```
:~# dirb-gendict -h
Usage: dirb-gendict -type pattern
  type: -n numeric [0-9]
        -c character [a-z]
        -C uppercase character [A-Z]
        -h hexa [0-f]
        -a alfanumeric [0-9a-z]
        -s case sensitive alfanumeric [0-9a-zA-Z]
  pattern: Must be an ascii string in which every 'X' character wildcard
           will be replaced with the incremental value.

Example: dirb-gendict -n thisword_X
  thisword_0
  thisword_1
  [...]
  thisword_9
```

***

**html2dic**

Dump word dictionary from html input file

```
:~# man html2dic
HTML2DIC(1)                 General Commands Manual                HTML2DIC(1)

NAME
       html2dic - Dump word dictionary from html input file

SYNOPSIS
       html2dic <file>

DESCRIPTION
       html2dic  extract  all words from an HTML page, generating a dictionary
       of all word found, one word per line.  Output is printed on stdout.

SEE ALSO
       dirb(1),dirb-gendict(1)

Philippe Thierry                  15/06/2017                       HTML2DIC(1)
```

***

Updated on: 2022-Aug-05\


***
