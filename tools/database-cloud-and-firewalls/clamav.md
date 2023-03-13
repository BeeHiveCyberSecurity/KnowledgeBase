---
description: >-
  ClamAV is a versatile open-source antivirus toolkit for Unix-based systems
  that provides real-time protection against malware threats and supports email
  scanning and Postfix integration.
---

# 🪔 clamav

ClamAV is a free and open-source antivirus software toolkit that provides real-time protection against viruses, Trojans, and other malware. ClamAV is widely used on Unix-based systems such as Linux, and is also available for Windows.

One of the key features of ClamAV is its ability to detect and remove a wide range of malware threats, including viruses, Trojans, spyware, adware, and other forms of malicious software. ClamAV uses a range of detection techniques, including signature-based detection, heuristic analysis, and behavior-based detection, to identify and remove malware threats.

ClamAV can be used in a variety of different configurations, depending on the needs of the user. It can be installed as a standalone antivirus solution, or integrated into a larger security solution. ClamAV can also be used as a command-line tool, or integrated into a variety of different applications.

In addition to its malware detection capabilities, ClamAV provides a range of additional features that make it a powerful tool for security professionals. For example, it includes support for email scanning, allowing it to detect and remove malware threats from incoming and outgoing email messages. ClamAV also includes support for the popular Mail Transfer Agent (MTA) Postfix, which allows it to be integrated into email servers for real-time scanning.

ClamAV is also highly configurable, with a range of options for customizing its behavior and performance. It includes support for multiple scan modes, including on-demand scanning, scheduled scanning, and real-time scanning. ClamAV can also be configured to scan specific files or directories, and to ignore certain types of files or extensions.

One of the key benefits of ClamAV is its open-source nature. As an open-source tool, ClamAV is freely available to download and use, and can be customized and modified by users to meet their specific needs. Additionally, the open-source nature of ClamAV means that it is continually being updated and improved by a large community of developers and security professionals.

In summary, ClamAV is a powerful and versatile antivirus tool that provides real-time protection against a wide range of malware threats. Its support for email scanning, Postfix integration, and customizable scan modes make it a valuable tool for security professionals and administrators. As an open-source tool, it is freely available and highly customizable, making it a valuable addition to any security toolkit.

#### clamav <a href="#clamav" id="clamav"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

This package contains the command line interface. Features:

* built-in support for various archive formats, including Zip, Tar, Gzip, Bzip2, OLE2, Cabinet, CHM, BinHex, SIS and others;
* built-in support for almost all mail file formats;
* built-in support for ELF executables and Portable Executable files compressed with UPX, FSG, Petite, NsPack, wwpack32, MEW, Upack and obfuscated with SUE, Y0da Cryptor and others;
* built-in support for popular document formats including Microsoft Office and Mac Office files, HTML, RTF and PDF.

For scanning to work, a virus database is needed. There are two options for getting it:

* clamav-freshclam: updates the database from Internet. This is recommended with Internet access.
* clamav-data: for users without Internet access. The package is not updated once installed. The clamav-getfiles package allows creating custom packages from an Internet-connected computer.

**Installed size:** `28.32 MB`\
**How to install:** `sudo apt install clamav`

<details>

<summary>Dependencies:</summary>

* clamav-freshclam | clamav-data
* libc6
* libclamav11
* libcurl4
* libgcc-s1
* libjson-c5
* libssl3
* zlib1g

</details>

**clambc**

Bytecode Analysis and Testing Tool

```
:~# clambc -h

                       Clam AntiVirus: Bytecode Testing Tool 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    clambc <file> [function] [param1 ...]

    --help                 -h         Show this help
    --version              -V         Show version
    --debug                           Show debug
    --force-interpreter    -f         Force using the interpreter instead of the JIT
    --trust-bytecode       -t         Trust loaded bytecode (default yes)
    --info                 -i         Print information about bytecode
    --printsrc             -p         Print bytecode source
    --printbcir            -c         Print IR of bytecode signature
    --input                -c         Input file to run the bytecode on
    --trace <level>        -T         Set bytecode trace level 0..7 (default 7)
    --no-trace-showsource  -s         Don't show source line during tracing
    --statistics=bytecode             Collect and print bytecode execution statistics
    file                              File to test

**Caution**: You should NEVER run bytecode signatures from untrusted sources.
Doing so may result in arbitrary code execution.

```

***

**clamscan**

Scan files and directories for viruses

```
:~# clamscan -h

                       Clam AntiVirus: Scanner 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    clamscan [options] [file/directory/-]

    --help                -h             Show this help
    --version             -V             Print version number
    --verbose             -v             Be verbose
    --archive-verbose     -a             Show filenames inside scanned archives
    --debug                              Enable libclamav's debug messages
    --quiet                              Only output error messages
    --stdout                             Write to stdout instead of stderr. Does not affect 'debug' messages.
    --no-summary                         Disable summary at end of scanning
    --infected            -i             Only print infected files
    --suppress-ok-results -o             Skip printing OK files
    --bell                               Sound bell on virus detection

    --tempdir=DIRECTORY                  Create temporary files in DIRECTORY
    --leave-temps[=yes/no(*)]            Do not remove temporary files
    --gen-json[=yes/no(*)]               Generate JSON metadata for the scanned file(s). For testing & development use ONLY.
                                         JSON will be printed if --debug is enabled.
                                         A JSON file will dropped to the temp directory if --leave-temps is enabled.
    --database=FILE/DIR   -d FILE/DIR    Load virus database from FILE or load all supported db files from DIR
    --official-db-only[=yes/no(*)]       Only load official signatures
    --log=FILE            -l FILE        Save scan report to FILE
    --recursive[=yes/no(*)]  -r          Scan subdirectories recursively
    --allmatch[=yes/no(*)]   -z          Continue scanning within file after finding a match
    --cross-fs[=yes(*)/no]               Scan files and directories on other filesystems
    --follow-dir-symlinks[=0/1(*)/2]     Follow directory symlinks (0 = never, 1 = direct, 2 = always)
    --follow-file-symlinks[=0/1(*)/2]    Follow file symlinks (0 = never, 1 = direct, 2 = always)
    --file-list=FILE      -f FILE        Scan files from FILE
    --remove[=yes/no(*)]                 Remove infected files. Be careful!
    --move=DIRECTORY                     Move infected files into DIRECTORY
    --copy=DIRECTORY                     Copy infected files into DIRECTORY
    --exclude=REGEX                      Don't scan file names matching REGEX
    --exclude-dir=REGEX                  Don't scan directories matching REGEX
    --include=REGEX                      Only scan file names matching REGEX
    --include-dir=REGEX                  Only scan directories matching REGEX

    --bytecode[=yes(*)/no]               Load bytecode from the database
    --bytecode-unsigned[=yes/no(*)]      Load unsigned bytecode
                                         **Caution**: You should NEVER run bytecode signatures from untrusted sources.
                                         Doing so may result in arbitrary code execution.
    --bytecode-timeout=N                 Set bytecode timeout (in milliseconds)
    --statistics[=none(*)/bytecode/pcre] Collect and print execution statistics
    --detect-pua[=yes/no(*)]             Detect Possibly Unwanted Applications
    --exclude-pua=CAT                    Skip PUA sigs of category CAT
    --include-pua=CAT                    Load PUA sigs of category CAT
    --detect-structured[=yes/no(*)]      Detect structured data (SSN, Credit Card)
    --structured-ssn-format=X            SSN format (0=normal,1=stripped,2=both)
    --structured-ssn-count=N             Min SSN count to generate a detect
    --structured-cc-count=N              Min CC count to generate a detect
    --structured-cc-mode=X               CC mode (0=credit debit and private label, 1=credit cards only
    --scan-mail[=yes(*)/no]              Scan mail files
    --phishing-sigs[=yes(*)/no]          Enable email signature-based phishing detection
    --phishing-scan-urls[=yes(*)/no]     Enable URL signature-based phishing detection
    --heuristic-alerts[=yes(*)/no]       Heuristic alerts
    --heuristic-scan-precedence[=yes/no(*)] Stop scanning as soon as a heuristic match is found
    --normalize[=yes(*)/no]              Normalize html, script, and text files. Use normalize=no for yara compatibility
    --scan-pe[=yes(*)/no]                Scan PE files
    --scan-elf[=yes(*)/no]               Scan ELF files
    --scan-ole2[=yes(*)/no]              Scan OLE2 containers
    --scan-pdf[=yes(*)/no]               Scan PDF files
    --scan-swf[=yes(*)/no]               Scan SWF files
    --scan-html[=yes(*)/no]              Scan HTML files
    --scan-xmldocs[=yes(*)/no]           Scan xml-based document files
    --scan-hwp3[=yes(*)/no]              Scan HWP3 files
    --scan-archive[=yes(*)/no]           Scan archive files (supported by libclamav)
    --alert-broken[=yes/no(*)]           Alert on broken executable files (PE & ELF)
    --alert-broken-media[=yes/no(*)]     Alert on broken graphics files (JPEG, TIFF, PNG, GIF)
    --alert-encrypted[=yes/no(*)]        Alert on encrypted archives and documents
    --alert-encrypted-archive[=yes/no(*)] Alert on encrypted archives
    --alert-encrypted-doc[=yes/no(*)]    Alert on encrypted documents
    --alert-macros[=yes/no(*)]           Alert on OLE2 files containing VBA macros
    --alert-exceeds-max[=yes/no(*)]      Alert on files that exceed max file size, max scan size, or max recursion limit
    --alert-phishing-ssl[=yes/no(*)]     Alert on emails containing SSL mismatches in URLs
    --alert-phishing-cloak[=yes/no(*)]   Alert on emails containing cloaked URLs
    --alert-partition-intersection[=yes/no(*)] Alert on raw DMG image files containing partition intersections
    --nocerts                            Disable authenticode certificate chain verification in PE files
    --dumpcerts                          Dump authenticode certificate chain in PE files

    --max-scantime=#n                    Scan time longer than this will be skipped and assumed clean (milliseconds)
    --max-filesize=#n                    Files larger than this will be skipped and assumed clean
    --max-scansize=#n                    The maximum amount of data to scan for each container file (**)
    --max-files=#n                       The maximum number of files to scan for each container file (**)
    --max-recursion=#n                   Maximum archive recursion level for container file (**)
    --max-dir-recursion=#n               Maximum directory recursion level
    --max-embeddedpe=#n                  Maximum size file to check for embedded PE
    --max-htmlnormalize=#n               Maximum size of HTML file to normalize
    --max-htmlnotags=#n                  Maximum size of normalized HTML file to scan
    --max-scriptnormalize=#n             Maximum size of script file to normalize
    --max-ziptypercg=#n                  Maximum size zip to type reanalyze
    --max-partitions=#n                  Maximum number of partitions in disk image to be scanned
    --max-iconspe=#n                     Maximum number of icons in PE file to be scanned
    --max-rechwp3=#n                     Maximum recursive calls to HWP3 parsing function
    --pcre-match-limit=#n                Maximum calls to the PCRE match function.
    --pcre-recmatch-limit=#n             Maximum recursive calls to the PCRE match function.
    --pcre-max-filesize=#n               Maximum size file to perform PCRE subsig matching.
    --disable-cache                      Disable caching and cache checks for hash sums of scanned files.

Pass in - as the filename for stdin.

(*) Default scan settings
(**) Certain files (e.g. documents, archives, etc.) may in turn contain other
   files inside. The above options ensure safe processing of this kind of data.

```

***

**clamsubmit**

File submission utility for ClamAV

```
:~# clamsubmit -h

                       Clam AntiVirus: Malware and False Positive Reporting Tool 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    clamsubmit -hHinpVvd?

    -h or -?                  Show this help
    -v                        Show version
    -e [EMAIL]                Your email address (required)
    -n [FILE/-]               Submit a false negative (FN)
    -N [NAME]                 Your name contained in quotation marks (required)
    -p [FILE/-]               Submit a false positive (FP)
    -V [VIRUS]                Detected virus name (required with -p)
    -d                        Enable debug output

You must specify -n or -p. Both are mutually exclusive. Pass in - as the filename for stdin.

```

***

**sigtool**

Signature and database management tool

```
:~# sigtool -h

                      Clam AntiVirus: Signature Tool 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    sigtool [options]

    --help                 -h              Show this help
    --version              -V              Print version number and exit
    --quiet                                Be quiet, output only error messages
    --debug                                Enable debug messages
    --stdout                               Write to stdout instead of stderr. Does not affect 'debug' messages.
    --hex-dump                             Convert data from stdin to a hex
                                           string and print it on stdout
    --md5 [FILES]                          Generate MD5 checksum from stdin
                                           or MD5 sigs for FILES
    --sha1 [FILES]                         Generate SHA1 checksum from stdin
                                           or SHA1 sigs for FILES
    --sha256 [FILES]                       Generate SHA256 checksum from stdin
                                           or SHA256 sigs for FILES
    --mdb [FILES]                          Generate .mdb (section hash) sigs
    --imp [FILES]                          Generate .imp (import table hash) sigs
    --fuzzy-img FILE(S)                    Generate image fuzzy hash for each file
    --html-normalise=FILE                  Create normalised parts of HTML file
    --ascii-normalise=FILE                 Create normalised text file from ascii source
    --utf16-decode=FILE                    Decode UTF16 encoded files
    --info=FILE            -i FILE         Print database information
    --build=NAME [cvd] -b NAME             Build a CVD file
    --max-bad-sigs=NUMBER                  Maximum number of mismatched signatures
                                           When building a CVD. Default: 3000
    --flevel=FLEVEL                        Specify a custom flevel.
                                           Default: 161
    --cvd-version=NUMBER                   Specify the version number to use for
                                           the build. Default is to use the value+1
                                           from the current CVD in --datadir.
                                           If no datafile is found the default
                                           behaviour is to prompt for a version
                                           number, this switch will prevent the
                                           prompt.  NOTE: If a CVD is found in the
                                           --datadir its version+1 is used and
                                           this value is ignored.
    --no-cdiff                             Don't generate .cdiff file
    --unsigned                             Create unsigned database file (.cud)
    --hybrid                               Create a hybrid (standard and bytecode) database file
    --print-certs=FILE                     Print Authenticode details from a PE
    --server=ADDR                          ClamAV Signing Service address
    --datadir=DIR                          Use DIR as default database directory
    --unpack=FILE          -u FILE         Unpack a CVD/CLD file
    --unpack-current=SHORTNAME             Unpack local CVD/CLD into cwd
    --list-sigs[=FILE]     -l[FILE]        List signature names
    --find-sigs=REGEX      -fREGEX         Find signatures matching REGEX
    --decode-sigs                          Decode signatures from stdin
    --test-sigs=DATABASE TARGET_FILE       Test signatures from DATABASE against 
                                           TARGET_FILE
    --vba=FILE                             Extract VBA/Word6 macro code
    --vba-hex=FILE                         Extract Word6 macro code with hex values
    --diff=OLD NEW         -d OLD NEW      Create diff for OLD and NEW CVDs
    --compare=OLD NEW      -c OLD NEW      Show diff between OLD and NEW files in
                                           cdiff format
    --run-cdiff=FILE       -r FILE         Execute update script FILE in cwd
    --verify-cdiff=DIFF CVD/CLD            Verify DIFF against CVD/CLD

```

***

#### clamav-base <a href="#clamav-base" id="clamav-base"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

This package mainly manages the clamav system account. It is not really useful without the clamav or clamav-daemon package.

**Installed size:** `145 KB`\
**How to install:** `sudo apt install clamav-base`

<details>

<summary>Dependencies:</summary>

* adduser
* debconf | debconf-2.0
* logrotate
* ucf

</details>

***

#### clamav-daemon <a href="#clamav-daemon" id="clamav-daemon"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

This package contains the daemon featuring:

* fast, multi-threaded daemon;
* easy integration with MTA’s;
* support for on-access scanning;
* remote scanning;
* able to be run supervised by daemon.

**Installed size:** `1011 KB`\
**How to install:** `sudo apt install clamav-daemon`

<details>

<summary>Dependencies:</summary>

* adduser
* clamav-base
* clamav-freshclam | clamav-data
* debconf | debconf-2.0
* dpkg
* init-system-helpers
* libc6
* libclamav11
* libcurl4
* libncurses6
* libsystemd0
* libtinfo6
* procps
* ucf
* zlib1g

</details>

**clamconf**

Clam AntiVirus configuration utility

```
:~# clamconf -h

                       Clam AntiVirus: Configuration Tool 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    --help                 -h         Show this help
    --version              -V         Show version
    --config-dir=DIR       -c DIR     Read configuration files from DIR
    --non-default          -n         Only display non-default settings
    --generate-config=NAME -g NAME    Generate example config file

```

***

**clamd**

An anti-virus daemon

```
:~# clamd -h

                      Clam AntiVirus: Daemon 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    clamd [options]

    --help                   -h             Show this help
    --version                -V             Show version number
    --foreground             -F             Run in foreground; do not daemonize
    --debug                                 Enable debug mode
    --log=FILE               -l FILE        Log into FILE
    --config-file=FILE       -c FILE        Read configuration from FILE

Pass in - as the filename for stdin.

```

***

**clamdtop**

Monitor the Clam AntiVirus Daemon

```
:~# clamdtop -h

                       Clam AntiVirus: Monitoring Tool 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    clamdtop [-hVc] [host[:port] /path/to/clamd.socket ...]

    --help                 -h         Show this help
    --version              -V         Show version
    --config-file=FILE     -c FILE    Read clamd's configuration files from FILE
    --defaultcolors        -d         Use default terminal colors
    host[:port]                       Connect to clamd on host at port (default 3310)
    /path/to/clamd.socket             Connect to clamd over a local socket

```

***

**clamonacc**

An anti-virus on-access scanning daemon and clamd client

```
:~# clamonacc -h

           ClamAV: On Access Scanning Application and Client 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    clamonacc [options] [file/directory/-]

    --help                 -h          Show this help
    --version              -V          Print version number and exit
    --verbose              -v          Be verbose
    --log=FILE             -l FILE     Save scanning output to FILE
    --foreground           -F          Output to foreground and do not daemonize
    --watch-list=FILE      -W FILE     Watch directories from FILE
    --exclude-list=FILE    -e FILE     Exclude directories from FILE
    --ping                 -p A[:I]    Ping clamd up to [A] times at optional interval [I] until it responds.
    --wait                 -w          Wait up to 30 seconds for clamd to start. Optionally use alongside --ping to set attempts [A] and interval [I] to check clamd.
    --remove                           Remove infected files. Be careful!
    --move=DIRECTORY                   Move infected files into DIRECTORY
    --copy=DIRECTORY                   Copy infected files into DIRECTORY
    --config-file=FILE     -c FILE     Read configuration from FILE
    --allmatch             -z          Continue scanning within file after finding a match.
    --fdpass                           Pass filedescriptor to clamd (useful if clamd is running as a different user)
    --stream                           Force streaming files to clamd (for debugging and unit testing)

```

***

#### clamav-docs <a href="#clamav-docs" id="clamav-docs"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

This package contains the documentation for the ClamAV suite.

**Installed size:** `748 KB`\
**How to install:** `sudo apt install clamav-docs`

***

#### clamav-freshclam <a href="#clamav-freshclam" id="clamav-freshclam"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

This package contains the freshclam program and scripts to automate virus database updating. It relies on an Internet connection, but can be run in a variety of ways to compensate for intermittent connections.

**Installed size:** `363 KB`\
**How to install:** `sudo apt install clamav-freshclam`

<details>

<summary>Dependencies:</summary>

* clamav-base
* debconf | debconf-2.0
* dpkg
* libc6
* libclamav11
* logrotate
* procps
* ucf

</details>

**freshclam**

Update virus databases

```
:~# freshclam -h

                      Clam AntiVirus: Database Updater 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    freshclam [options]

    --help               -h              Show this help
    --version            -V              Print version number and exit
    --verbose            -v              Be verbose
    --debug                              Enable debug messages
    --quiet                              Only output error messages
    --no-warnings                        Don't print and log warnings
    --stdout                             Write to stdout instead of stderr. Does not affect 'debug' messages.
    --show-progress                      Show download progress percentage

    --config-file=FILE                   Read configuration from FILE.
    --log=FILE           -l FILE         Log into FILE
    --daemon             -d              Run in daemon mode
    --pid=FILE           -p FILE         Save daemon's pid in FILE
    --foreground         -F              Don't fork into background (for use in daemon mode).
    --user=USER          -u USER         Run as USER
    --no-dns                             Force old non-DNS verification method
    --checks=#n          -c #n           Number of checks per day, 1 <= n <= 50
    --datadir=DIRECTORY                  Download new databases into DIRECTORY
    --daemon-notify[=/path/clamd.conf]   Send RELOAD command to clamd
    --local-address=IP   -a IP           Bind to IP for HTTP downloads
    --on-update-execute=COMMAND          Execute COMMAND after successful update.
                                         Use EXIT_1 to return 1 after successful database update.
    --on-error-execute=COMMAND           Execute COMMAND if errors occurred
    --on-outdated-execute=COMMAND        Execute COMMAND when software is outdated
    --update-db=DBNAME                   Only update database DBNAME

```

***

#### clamav-milter <a href="#clamav-milter" id="clamav-milter"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

This package contains the ClamAV milter for use with sendmail. It can be configured to be run either standalone, or using clamav-daemon.

**Installed size:** `519 KB`\
**How to install:** `sudo apt install clamav-milter`

<details>

<summary>Dependencies:</summary>

* adduser
* clamav-base
* clamav-freshclam | clamav-data
* debconf | debconf-2.0
* dpkg
* init-system-helpers
* libc6
* libclamav11
* libmilter1.0.1
* logrotate
* procps
* ucf

</details>

**clamav-milter**

Milter compatible mail scanner

```
:~# clamav-milter -h

                       Clam AntiVirus: Milter Mail Scanner 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    clamav-milter [-c <config-file>]


    --help                   -h       Show this help
    --version                -V       Show version
    --config-file <file>     -c       Read configuration from file

```

***

#### clamav-testfiles <a href="#clamav-testfiles" id="clamav-testfiles"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

This package contains files ‘infected’ with a test signature. The test signature (ClamAV-Test-Signature) should be detectable by all anti-virus programs.

**Installed size:** `6.34 MB`\
**How to install:** `sudo apt install clamav-testfiles`

***

#### clamdscan <a href="#clamdscan" id="clamdscan"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

This package contains clamdscan, the command line interface of the clamav daemon.

**Installed size:** `213 KB`\
**How to install:** `sudo apt install clamdscan`

<details>

<summary>Dependencies:</summary>

* clamav-base
* libc6
* libclamav11

</details>

**clamdscan**

Scan files and directories for viruses using Clam AntiVirus Daemon

```
:~# clamdscan -h

                      Clam AntiVirus: Daemon Client 1.0.1
           By The ClamAV Team: https://www.clamav.net/about.html#credits
           (C) 2022 Cisco Systems, Inc.

    clamdscan [options] [file/directory/-]

    --help              -h             Show this help
    --version           -V             Print version number and exit
    --verbose           -v             Be verbose
    --quiet                            Be quiet, only output error messages
    --stdout                           Write to stdout instead of stderr. Does not affect 'debug' messages.
                                       (this help is always written to stdout)
    --log=FILE          -l FILE        Save scan report in FILE
    --file-list=FILE    -f FILE        Scan files from FILE
    --ping              -p A[:I]       Ping clamd up to [A] times at optional interval [I] until it responds.
    --wait              -w             Wait up to 30 seconds for clamd to start. Optionally use alongside --ping to set attempts [A] and interval [I] to check clamd.
    --remove                           Remove infected files. Be careful!
    --move=DIRECTORY                   Move infected files into DIRECTORY
    --copy=DIRECTORY                   Copy infected files into DIRECTORY
    --config-file=FILE                 Read configuration from FILE.
    --allmatch            -z           Continue scanning within file after finding a match.
    --multiscan           -m           Force MULTISCAN mode
    --infected            -i           Only print infected files
    --no-summary                       Disable summary at end of scanning
    --reload                           Request clamd to reload virus database
    --fdpass                           Pass filedescriptor to clamd (useful if clamd is running as a different user)
    --stream                           Force streaming files to clamd (for debugging and unit testing)

```

***

#### libclamav-dev <a href="#libclamav-dev" id="libclamav-dev"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

The package contains the needed headers and libraries for developing software using the libclamav interface.

This library can be used to develop virus scanner applications.

**Installed size:** `142 KB`\
**How to install:** `sudo apt install libclamav-dev`

<details>

<summary>Dependencies:</summary>

* libbz2-dev
* libc6-dev | libc-dev
* libclamav11
* libssl-dev
* libtommath-dev
* zlib1g-dev

</details>

**clamav-config**

Script to get information about libclamav

```
:~# clamav-config -h
Usage: clamav-config [OPTION]

Known values for OPTION are:

  --prefix=DIR		change libclamav prefix [default /usr]
  --libs		print library linking information
  --cflags		print pre-processor and compiler flags
  --help		display this help and exit
  --version		output version information
```

***

#### libclamav11 <a href="#libclamav11" id="libclamav11"></a>

Clam AntiVirus is an anti-virus toolkit for Unix. The main purpose of this software is the integration with mail servers (attachment scanning). The package provides a flexible and scalable multi-threaded daemon in the clamav-daemon package, a command-line scanner in the clamav package, and a tool for automatic updating via the Internet in the clamav-freshclam package. The programs are based on libclamav, which can be used by other software.

For programs written using the libclamav library. Libclamav may be used to add virus protection into software. The library is thread-safe, and automatically recognizes and scans archives. Scanning is very fast and most of the time not noticeable.

**Installed size:** `29.83 MB`\
**How to install:** `sudo apt install libclamav11`

<details>

<summary>Dependencies:</summary>

* libbz2-1.0
* libc6
* libcurl4
* libgcc-s1
* libjson-c5
* libmspack0
* libpcre2-8-0
* libssl3
* libtfm1
* libxml2
* zlib1g

</details>

***
