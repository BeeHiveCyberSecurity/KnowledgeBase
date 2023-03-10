---
description: >-
  SQLMap automates detection and exploitation of SQL injection vulnerabilities
  in web apps. Configurable, customizable, and user-friendly. Essential for web
  security.
---

# 🗃 sqlmap

SQLMap is a powerful security tool designed to automate the process of detecting and exploiting SQL injection vulnerabilities in web applications. Developed by Bernardo Damele and Miroslav Stampar, SQLMap is an open-source tool that has become increasingly popular among penetration testers, security researchers, and web developers who want to secure their web applications against SQL injection attacks.

SQL injection is a type of attack that allows hackers to inject malicious SQL code into a web application's database, giving them access to sensitive information such as usernames, passwords, and credit card numbers. SQLMap automates the process of detecting these vulnerabilities, making it easier for developers to identify and fix them.

One of the key features of SQLMap is its ability to detect a wide range of SQL injection vulnerabilities, including blind SQL injection, error-based SQL injection, and time-based SQL injection. It can also detect and exploit second-order SQL injection vulnerabilities, which are more difficult to detect and exploit than traditional SQL injection vulnerabilities.

SQLMap's user interface is straightforward and easy to use, making it an excellent choice for developers who are new to SQL injection testing. The tool comes with a range of customization options that allow users to tailor their tests to their specific needs. For example, users can specify the type of database they want to test, the type of injection technique they want to use, and the depth of their tests.

SQLMap is also highly configurable, with a wide range of options for customizing the tool's behavior. Users can specify the level of verbosity they want to see in their output, configure their HTTP requests to use specific headers or cookies, and even specify the number of threads they want to use for their tests.

Another important feature of SQLMap is its ability to automate the process of exploiting SQL injection vulnerabilities. Once a vulnerability has been detected, SQLMap can automatically exploit it to retrieve sensitive data from the target database. This makes it an incredibly powerful tool for testing the security of web applications.

Overall, SQLMap is an essential tool for anyone who wants to secure their web applications against SQL injection attacks. With its powerful detection and exploitation capabilities, customizable options, and user-friendly interface, it's an excellent choice for security researchers, penetration testers, and web developers alike.

### sqlmap Usage Example <a href="#sqlmap-usage-example" id="sqlmap-usage-example"></a>

Attack the given URL (`-u “http://192.168.1.250/?p=1&forumaction=search”`) and extract the database names (`–dbs`):

```
:~# sqlmap -u "http://192.168.1.250/?p=1&forumaction=search" --dbs
        ___
       __H__
 ___ ___[)]_____ ___ ___  {1.2.11#stable}
|_ -| . ["]     | .'| . |
|___|_  ["]_|_|_|__,|  _|
      |_|V          |_|   http://sqlmap.org

[!] legal disclaimer: Usage of sqlmap for attacking targets without prior mutual consent is illegal. It is the end user's responsibility to obey all applicable local, state and federal laws. Developers assume no liability and are not responsible for any misuse or damage caused by this program

[*] starting at 13:37:00

[13:37:00] [INFO] testing connection to the target URL
```

***

\


### Packages and Binaries:

#### sqlmap <a href="#sqlmap" id="sqlmap"></a>

sqlmap goal is to detect and take advantage of SQL injection vulnerabilities in web applications. Once it detects one or more SQL injections on the target host, the user can choose among a variety of options to perform an extensive back-end database management system fingerprint, retrieve DBMS session user and database, enumerate users, password hashes, privileges, databases, dump entire or user’s specific DBMS tables/columns, run his own SQL statement, read specific files on the file system and more.

**Installed size:** `10.51 MB`\
**How to install:** `sudo apt install sqlmap`

<details>

<summary>Dependencies:</summary>

* python3
* python3-magic

</details>

**sqlmap**

Automatic SQL injection tool

```
:~# sqlmap -h
        ___
       __H__
 ___ ___[)]_____ ___ ___  {1.7.2#stable}
|_ -| . [(]     | .'| . |
|___|_  [']_|_|_|__,|  _|
      |_|V...       |_|   https://sqlmap.org

Usage: python3 sqlmap [options]

Options:
  -h, --help            Show basic help message and exit
  -hh                   Show advanced help message and exit
  --version             Show program's version number and exit
  -v VERBOSE            Verbosity level: 0-6 (default 1)

  Target:
    At least one of these options has to be provided to define the
    target(s)

    -u URL, --url=URL   Target URL (e.g. "http://www.site.com/vuln.php?id=1")
    -g GOOGLEDORK       Process Google dork results as target URLs

  Request:
    These options can be used to specify how to connect to the target URL

    --data=DATA         Data string to be sent through POST (e.g. "id=1")
    --cookie=COOKIE     HTTP Cookie header value (e.g. "PHPSESSID=a8d127e..")
    --random-agent      Use randomly selected HTTP User-Agent header value
    --proxy=PROXY       Use a proxy to connect to the target URL
    --tor               Use Tor anonymity network
    --check-tor         Check to see if Tor is used properly

  Injection:
    These options can be used to specify which parameters to test for,
    provide custom injection payloads and optional tampering scripts

    -p TESTPARAMETER    Testable parameter(s)
    --dbms=DBMS         Force back-end DBMS to provided value

  Detection:
    These options can be used to customize the detection phase

    --level=LEVEL       Level of tests to perform (1-5, default 1)
    --risk=RISK         Risk of tests to perform (1-3, default 1)

  Techniques:
    These options can be used to tweak testing of specific SQL injection
    techniques

    --technique=TECH..  SQL injection techniques to use (default "BEUSTQ")

  Enumeration:
    These options can be used to enumerate the back-end database
    management system information, structure and data contained in the
    tables

    -a, --all           Retrieve everything
    -b, --banner        Retrieve DBMS banner
    --current-user      Retrieve DBMS current user
    --current-db        Retrieve DBMS current database
    --passwords         Enumerate DBMS users password hashes
    --dbs               Enumerate DBMS databases
    --tables            Enumerate DBMS database tables
    --columns           Enumerate DBMS database table columns
    --schema            Enumerate DBMS schema
    --dump              Dump DBMS database table entries
    --dump-all          Dump all DBMS databases tables entries
    -D DB               DBMS database to enumerate
    -T TBL              DBMS database table(s) to enumerate
    -C COL              DBMS database table column(s) to enumerate

  Operating system access:
    These options can be used to access the back-end database management
    system underlying operating system

    --os-shell          Prompt for an interactive operating system shell
    --os-pwn            Prompt for an OOB shell, Meterpreter or VNC

  General:
    These options can be used to set some general working parameters

    --batch             Never ask for user input, use the default behavior
    --flush-session     Flush session files for current target

  Miscellaneous:
    These options do not fit into any other category

    --wizard            Simple wizard interface for beginner users

[!] to see full list of options run with '-hh'
```

***

**sqlmapapi**

Automatic SQL injection tool, api server

```
:~# sqlmapapi -h
Usage: sqlmapapi [options]

Options:
  -h, --help            show this help message and exit
  -s, --server          Run as a REST-JSON API server
  -c, --client          Run as a REST-JSON API client
  -H HOST, --host=HOST  Host of the REST-JSON API server (default "127.0.0.1")
  -p PORT, --port=PORT  Port of the the REST-JSON API server (default 8775)
  --adapter=ADAPTER     Server (bottle) adapter to use (default "wsgiref")
  --username=USERNAME   Basic authentication username (optional)
  --password=PASSWORD   Basic authentication password (optional)
```

***

Updated on: 2023-Mar-08\


***
