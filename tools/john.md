---
description: >-
  John the Ripper, often called "john," is a popular password cracking tool that
  uses dictionary attacks and brute-force methods to crack passwords.
---

# 🔐 john

### Mailer <a href="#mailer" id="mailer"></a>

```
:~# mailer
Usage: /usr/sbin/mailer PASSWORD-FILE
```

### Unique <a href="#unique" id="unique"></a>

```
:~# unique
Usage: unique [-v] [-inp=fname] [-cut=len] [-mem=num] OUTPUT-FILE [-ex_file=FNAME2] [-ex_file_only=FNAME2]

       reads from stdin 'normally', but can be overridden by optional -inp=
       If -ex_file=XX is used, then data from file XX is also used to
       unique the data, but nothing is ever written to XX. Thus, any data in
       XX, will NOT output into OUTPUT-FILE (for making iterative dictionaries)
       -ex_file_only=XX assumes the file is 'unique', and only checks against XX
       -cut=len  Will trim each input lines to 'len' bytes long, prior to running
       the unique algorithm. The 'trimming' is done on any -ex_file[_only] file
       -mem=num.  A number that overrides the UNIQUE_HASH_LOG value from within
       params.h.  The default is 21.  This can be raised, up to 25 (memory usage
       doubles each number).  If you go TOO large, unique will swap and thrash and
       work VERY slow

       -v is for 'verbose' mode, outputs line counts during the run
```

### john Usage Example <a href="#john-usage-example" id="john-usage-example"></a>

Using a wordlist (`–wordlist=/usr/share/john/password.lst`), apply mangling rules (`–rules`) and attempt to crack the password hashes in the given file (`unshadowed.txt`):

```
:~# john --wordlist=/usr/share/john/password.lst --rules unshadowed.txt
Warning: detected hash type "sha512crypt", but the string is also recognized as "crypt"
Use the "--format=crypt" option to force loading these as that type instead
Loaded 1 password hash (sha512crypt [64/64])
toor             (root)
guesses: 1  time: 0:00:00:07 DONE (Mon May 19 08:13:05 2014)  c/s: 482  trying: 1701d - andrew
Use the "--show" option to display all of the cracked passwords reliably
```

***

```
:~$ echo -n test2 | md5sum
ad0234829205b9033196ba818f7a872b  -
:~$ echo -n test2 | md5sum | awk '{print $1}'
ad0234829205b9033196ba818f7a872b
:~$ echo -n test2 | md5sum | awk '{print $1}' > hash
:~$ 
:~$ for x in $(seq 0 9); do echo test$x >> wordlists; done
:~$ grep test2 wordlists 
test2
:~$ wc -l wordlists 
10 wordlists
:~$ 
:~$ john --list=formats | grep -i 'md5'
descrypt, bsdicrypt, md5crypt, md5crypt-long, bcrypt, scrypt, LM, AFS, 
aix-ssha512, andOTP, ansible, argon2, as400-des, as400-ssha1, asa-md5, 
dahua, dashlane, diskcryptor, Django, django-scrypt, dmd5, dmg, dominosec, 
mschapv2-naive, krb5pa-md5, mssql, mssql05, mssql12, multibit, mysqlna, 
mysql-sha1, mysql, net-ah, nethalflm, netlm, netlmv2, net-md5, netntlmv2, 
netntlm, netntlm-naive, net-sha1, nk, notes, md5ns, nsec3, NT, o10glogon, 
PBKDF2-HMAC-MD4, PBKDF2-HMAC-MD5, PBKDF2-HMAC-SHA1, PBKDF2-HMAC-SHA256, 
PHPS2, pix-md5, PKZIP, po, postgres, PST, PuTTY, pwsafe, qnx, RACF, 
Raw-Keccak, Raw-Keccak-256, Raw-MD4, Raw-MD5, Raw-MD5u, Raw-SHA1, 
Stribog-256, Stribog-512, STRIP, SunMD5, SybaseASE, Sybase-PROP, tacacs-plus, 
tcp-md5, telegram, tezos, Tiger, tc_aes_xts, tc_ripemd160, tc_ripemd160boot, 
ZipMonster, plaintext, has-160, HMAC-MD5, HMAC-SHA1, HMAC-SHA224, 
:~$ 
:~$ john  --format=raw-md5 --wordlist=wordlists hash
Created directory: /home/g0tmi1k/.john
Using default input encoding: UTF-8
Loaded 1 password hash (Raw-MD5 [MD5 128/128 AVX 4x3])
Warning: no OpenMP support for this hash type, consider --fork=2
Press 'q' or Ctrl-C to abort, almost any other key for status
Warning: Only 10 candidates left, minimum 12 needed for performance.
test2            (?)
1g 0:00:00:00 DONE (2021-11-04 10:30) 100.0g/s 1000p/s 1000c/s 1000C/s test0..test9
Use the "--show --format=Raw-MD5" options to display all of the cracked passwords reliably
Session completed
:~$
```

### unique Usage Example <a href="#unique-usage-example" id="unique-usage-example"></a>

Using verbose mode (`-v`), read a list of passwords (`-inp=allwords.txt`) and save only unique words to a file (`uniques.txt`):

```
:~# unique -v -inp=allwords.txt uniques.txt
Total lines read 6089 Unique lines written 5083
```

***

\


### Packages and Binaries:

#### john <a href="#john" id="john"></a>

John the Ripper is a tool designed to help systems administrators to find weak (easy to guess or crack through brute force) passwords, and even automatically mail users warning them about it, if it is desired.

Besides several crypt(3) password hash types most commonly found on various Unix flavors, supported out of the box are Kerberos AFS and Windows NT/2000/XP/2003 LM hashes, plus several more with contributed patches.

**Installed size:** `77.31 MB`\
**How to install:** `sudo apt install john`

<details>

<summary>Dependencies:</summary>

* john-data
* libc6
* libcrypt1
* libgmp10
* libgomp1
* libpcap0.8
* libssl3
* zlib1g

</details>

**SIPdump**

Part of SIPcrack, A suite of tools to sniff and crack the digest authentications within the SIP protocol.

```
:~# SIPdump -h
Usage: sipdump [OPTIONS] <dump file>                           

       <dump file>    = file where captured logins will be written to

       Options:                                                  
       -i <interface> = interface to listen on                   
       -p <file>      = use pcap data file                       
       -m             = enter login data manually                
       -f "<filter>"  = set libpcap filter                       

* Invalid arguments
```

***

**base64conv**

```
:~# base64conv -h
base64conv: invalid option -- 'h'
Usage: base64conv [-l] [-i intype] [-o outtype] [-q] [-w] [-e] [-f flag] [data[data ...] | < stdin]
 - data must match input_type i.e. if hex, then data should be in hex
 - if data is not present, then base64conv will read data from std input)
 - if data read from stdin, max size of any line is 256k

  -q will only output resultant string. No extra junk text
  -e turns on buffer overwrite error checking logic
  -l performs a 'length' test

  -r ifname  process whole file ifname (this is the input file)
  -w ofname  The output filename for whole file processing
             NOTE, -r and -w have to be used as a pair

Input/Output types:
  raw      raw data byte
  hex      hexadecimal string (for input, case does not matter)
  mime     base64 mime encoding
  crypt    base64 crypt character set encoding
  cryptBS  base64 crypt encoding, byte swapped

Flags (note more than 1 -f command switch can be given at one time):
  HEX_UPCASE         output or length UPCASED (input case auto handled)
  HEX_LOCASE         output or length locased (input case auto handled)
  MIME_TRAIL_EQ      output mime adds = chars (input = auto handled)
  CRYPT_TRAIL_DOTS   output crypt adds . chars (input . auto handled)
  MIME_PLUS_TO_DOT   mime converts + to . (passlib encoding)
  MIME_DASH_UNDER    mime convert +/ into -_ (passlib encoding)
```

***

**bitlocker2john**

```
:~# bitlocker2john -h

Usage: bitlocker2john -i <Image of encrypted memory unit>

Options:

  -h		Show this help
  -i		Image path of encrypted memory unit encrypted with BitLocker
```

***

**calc\_stat**

```
:~# calc_stat -h
Usage: calc_stat [-p] dictionary_file statfile
	-p: include non printable and 8-bit characters
```

***

**cprepair**

```
:~# cprepair -h
Codepage repair (c) magnum 2014-2019

Input can be a mix of codepages, UTF-8 and double-encoded UTF-8, and with
a mix of Windows (CRLF) and Unix (LF) line endings, or missing line endings
on last lines.  If no file name is given, STDIN is used.
Output is UTF-8 with LF line endings and no silly BOM.

Usage: cprepair [options] [file(s)]
Options:
 -i <cp>   Codepage to assume for 8-bit input. Default is CP1252 (MS Latin-1)
 -f <cp>   Alternate codepage when no ASCII letters (a-z, A-Z) seen (default
           is to not treat them differently)
 -n        Do not guess (leave 8-bit as-is)
 -s        Suppress lines that does not need fixing.
 -d        Debug (show conversions).
 -l        List supported encodings.
 -p        Only convert stuff after first ':' (.pot file).
 -P        Suppress output lines with unprintable ASCII and, when used together
           with -n option, also suppress lines with invalid UTF-8
```

***

**dmg2john**

***

**eapmd5tojohn**

```
:~# eapmd5tojohn -h
Usage: eapmd5tojohn -r <pcap file>
```

***

**genmkvpwd**

```
:~# genmkvpwd -h
Usage: genmkvpwd statfile max_lvl [max_len] [start] [end]
```

***

**gpg2john**

***

**hccap2john**

***

**john**

A tool to find weak passwords of your users

```
:~# john -h
John the Ripper 1.9.0-jumbo-1+bleeding-aec1328d6c 2021-11-02 10:45:52 +0100 OMP [linux-gnu 64-bit x86_64 AVX2 AC]
Copyright (c) 1996-2021 by Solar Designer and others
Homepage: https://www.openwall.com/john/

Usage: john [OPTIONS] [PASSWORD-FILES]

--help                     Print usage summary
--single[=SECTION[,..]]    "Single crack" mode, using default or named rules
--single=:rule[,..]        Same, using "immediate" rule(s)
--single-seed=WORD[,WORD]  Add static seed word(s) for all salts in single mode
--single-wordlist=FILE     *Short* wordlist with static seed words/morphemes
--single-user-seed=FILE    Wordlist with seeds per username (user:password[s]
                           format)
--single-pair-max=N        Override max. number of word pairs generated (6)
--no-single-pair           Disable single word pair generation
--[no-]single-retest-guess Override config for SingleRetestGuess
--wordlist[=FILE] --stdin  Wordlist mode, read words from FILE or stdin
                  --pipe   like --stdin, but bulk reads, and allows rules
--rules[=SECTION[,..]]     Enable word mangling rules (for wordlist or PRINCE
                           modes), using default or named rules
--rules=:rule[;..]]        Same, using "immediate" rule(s)
--rules-stack=SECTION[,..] Stacked rules, applied after regular rules or to
                           modes that otherwise don't support rules
--rules-stack=:rule[;..]   Same, using "immediate" rule(s)
--rules-skip-nop           Skip any NOP ":" rules (you already ran w/o rules)
--loopback[=FILE]          Like --wordlist, but extract words from a .pot file
--mem-file-size=SIZE       Size threshold for wordlist preload (default 2048 MB)
--dupe-suppression         Suppress all dupes in wordlist (and force preload)
--incremental[=MODE]       "Incremental" mode [using section MODE]
--incremental-charcount=N  Override CharCount for incremental mode
--external=MODE            External mode or word filter
--mask[=MASK]              Mask mode using MASK (or default from john.conf)
--markov[=OPTIONS]         "Markov" mode (see doc/MARKOV)
--mkv-stats=FILE           "Markov" stats file
--prince[=FILE]            PRINCE mode, read words from FILE
--prince-loopback[=FILE]   Fetch words from a .pot file
--prince-elem-cnt-min=N    Minimum number of elements per chain (1)
--prince-elem-cnt-max=[-]N Maximum number of elements per chain (negative N is
                           relative to word length) (8)
--prince-skip=N            Initial skip
--prince-limit=N           Limit number of candidates generated
--prince-wl-dist-len       Calculate length distribution from wordlist
--prince-wl-max=N          Load only N words from input wordlist
--prince-case-permute      Permute case of first letter
--prince-mmap              Memory-map infile (not available with case permute)
--prince-keyspace          Just show total keyspace that would be produced
                           (disregarding skip and limit)
--subsets[=CHARSET]        "Subsets" mode (see doc/SUBSETS)
--subsets-required=N       The N first characters of "subsets" charset are
                           the "required set"
--subsets-min-diff=N       Minimum unique characters in subset
--subsets-max-diff=[-]N    Maximum unique characters in subset (negative N is
                           relative to word length)
--subsets-prefer-short     Prefer shorter candidates over smaller subsets
--subsets-prefer-small     Prefer smaller subsets over shorter candidates
--make-charset=FILE        Make a charset, FILE will be overwritten
--stdout[=LENGTH]          Just output candidate passwords [cut at LENGTH]
--session=NAME             Give a new session the NAME
--status[=NAME]            Print status of a session [called NAME]
--restore[=NAME]           Restore an interrupted session [called NAME]
--[no-]crack-status        Emit a status line whenever a password is cracked
--progress-every=N         Emit a status line every N seconds
--show[=left]              Show cracked passwords [if =left, then uncracked]
--show=formats             Show information about hashes in a file (JSON)
--show=invalid             Show lines that are not valid for selected format(s)
--test[=TIME]              Run tests and benchmarks for TIME seconds each
                           (if TIME is explicitly 0, test w/o benchmark)
--stress-test[=TIME]       Loop self tests forever
--test-full=LEVEL          Run more thorough self-tests
--no-mask                  Used with --test for alternate benchmark w/o mask
--skip-self-tests          Skip self tests
--users=[-]LOGIN|UID[,..]  [Do not] load this (these) user(s) only
--groups=[-]GID[,..]       Load users [not] of this (these) group(s) only
--shells=[-]SHELL[,..]     Load users with[out] this (these) shell(s) only
--salts=[-]COUNT[:MAX]     Load salts with[out] COUNT [to MAX] hashes, or
--salts=#M[-N]             Load M [to N] most populated salts
--costs=[-]C[:M][,...]     Load salts with[out] cost value Cn [to Mn]. For
                           tunable cost parameters, see doc/OPTIONS
--fork=N                   Fork N processes
--node=MIN[-MAX]/TOTAL     This node's number range out of TOTAL count
--save-memory=LEVEL        Enable memory saving, at LEVEL 1..3
--log-stderr               Log to screen instead of file
--verbosity=N              Change verbosity (1-5 or 6 for debug, default 3)
--no-log                   Disables creation and writing to john.log file
--bare-always-valid=Y      Treat bare hashes as valid (Y/N)
--catch-up=NAME            Catch up with existing (paused) session NAME
--config=FILE              Use FILE instead of john.conf or john.ini
--encoding=NAME            Input encoding (eg. UTF-8, ISO-8859-1). See also
                           doc/ENCODINGS.
--input-encoding=NAME      Input encoding (alias for --encoding)
--internal-codepage=NAME   Codepage used in rules/masks (see doc/ENCODINGS)
--target-encoding=NAME     Output encoding (used by format)
--force-tty                Set up terminal for reading keystrokes even if we're
                           not the foreground process
--field-separator-char=C   Use 'C' instead of the ':' in input and pot files
--[no-]keep-guessing       Try finding plaintext collisions
--list=WHAT                List capabilities, see --list=help or doc/OPTIONS
--length=N                 Shortcut for --min-len=N --max-len=N
--min-length=N             Request a minimum candidate length in bytes
--max-length=N             Request a maximum candidate length in bytes
--max-candidates=[-]N      Gracefully exit after this many candidates tried.
                           (if negative, reset count on each crack)
--max-run-time=[-]N        Gracefully exit after this many seconds (if negative,
                           reset timer on each crack)
--mkpc=N                   Request a lower max. keys per crypt
--no-loader-dupecheck      Disable the dupe checking when loading hashes
--pot=NAME                 Pot file to use
--regen-lost-salts=N       Brute force unknown salts (see doc/OPTIONS)
--reject-printable         Reject printable binaries
--tune=HOW                 Tuning options (auto/report/N)
--subformat=FORMAT         Pick a benchmark format for --format=crypt
--format=[NAME|CLASS][,..] Force hash of type NAME. The supported formats can
                           be seen with --list=formats and --list=subformats.
                           See also doc/OPTIONS for more advanced selection of
                           format(s), including using classes and wildcards.
```

***

**keepass2john**

```
:~# keepass2john -h
keepass2john: invalid option -- 'h'
Usage: keepass2john [-k <keyfile>] <.kdbx database(s)>
```

***

**mailer**

Script to warn users about their weak passwords

```
:~# man mailer
MAILER(8)                   System Manager's Manual                  MAILER(8)

NAME
       mailer - script to warn users about their weak passwords

SYNOPSIS
       mailer password-files

DESCRIPTION
       This manual page documents briefly the mailer command, which is part of
       the john  package.   This  manual  page  was  written  for  the  Debian
       GNU/Linux  distribution  because  the  original program does not have a
       manual page.  john, better known as John the Ripper, is a tool to  find
       weak passwords of users in a server.
       The  mailer  tool is useful to inform users which have been found to be
       using weak passwords by mail.

       You should edit the message mailer will send to the users, but remember
       to copy the script to a safe place before editing it, as it's generally
       a bad idea to modify things living in /usr.

SEE ALSO
       john(8), unafs(8), unique(8), unshadow(8).

       The programs are documented fully by John's documentation, which should
       be  available  in  /usr/share/doc/john  or other location, depending on
       your system.

AUTHOR
       This manual page was written by Jordi Mallach  <>,  for
       the Debian GNU/Linux system (but may be used by others).
       John  the Ripper and mailer were written by Solar Designer <
       wall.com>. The complete list of contributors can be found in the  CRED-
       ITS file in the documentation directory.

john                             June 03, 2004                       MAILER(8)
```

***

***

***

***

**rar2john**

```
:~# rar2john -h
rar2john: invalid option -- 'h'
Usage: rar2john [-v] <rar file(s)>
 -v	Add some verbosity/debug output
```

***

**raw2dyna**

```
:~# raw2dyna -h
usage raw2dyna [options] < input > output
	Options:
		-d=#   dyna number (-d=12 and $dynamic_12$hash$salt is used)
		-a     ALL hashes get $HEX$ and not simply hashes which have problems
		-ls=#  The salt is the leading data, and it is # bytes long
		-ss=b  The salt separator char is b  a blank -ss= means no separator char
		-hl=n  The length of hash.  SHA1 is 40, MD4/5 is 32, SHA256 is 64, etc
		-2h=r  perform a simple convert to hex.  the string r is converted to $HEX$hhhh...
		-2r=h  perform a simple convert out of hex.  the hex string h is converted to raw data
		       if either -2h or -2r are used, then the convert is done and the program exits
	defaults are -d=12 -ss=: -hl=32
```

***

**tgtsnarf**

```
:~# tgtsnarf --help
tgtsnarf: invalid option -- '-'
Usage: tgtsnarf [-A] realm host [users...]
```

***

***

**unafs**

Script to warn users about their weak passwords

```
:~# unafs -h
Usage: unafs DATABASE-FILE CELL-NAME
```

***

***

**unique**

Removes duplicates from a wordlist

***

**unshadow**

Combines passwd and shadow files

```
:~# unshadow -h
Usage: unshadow PASSWORD-FILE SHADOW-FILE
```

***

**vncpcap2john**

***

**wpapcap2john**

```
:~# wpapcap2john -h
Converts PCAP or IVS2 files to JtR format.
Supported encapsulations: 802.11, Prism, Radiotap, PPI and TZSP over UDP.
Usage: wpapcap2john [options] <file[s]>

-c		Show only complete auths (incomplete ones might be wrong passwords
		but we can crack what passwords were tried).
-v		Bump verbosity (can be used several times, try -vv)
-d		Do not suppress dupe hashes (per AP/STA pair)
-r		Ignore replay-count (may output fuzzed-anonce handshakes)
-f <n>		Force anonce fuzzing with +/- <n>
-e <essid:mac>	Manually add Name:MAC pair(s) in case the file lacks beacons.
		eg. -e "Magnum WIFI:6d:61:67:6e:75:6d"
-m <mac>	Ignore any packets not involving this mac address

```

***

**zip2john**

```
:~# zip2john -h
zip2john: invalid option -- 'h'
Usage: zip2john [options] [zip file(s)]
 -s Scan archive from the beginning, looking for local file headers. This
    is less reliable than going by the central index, but might work better
    with corrupted or split archives.
Options for 'old' PKZIP encrypted files only:
 -a <filename>   This is a 'known' ASCII file. This can be faster, IF all
    files are larger, and you KNOW that at least one of them starts out as
    'pure' ASCII data.
 -o <filename>   Only use this file from the .zip file.
 -c This will create a 'checksum only' hash.  If there are many encrypted
    files in the .zip file, then this may be an option, and there will be
    enough data that false positives will not be seen.  Up to 8 files are
    supported. These hashes do not reveal actual file data.
 -m Use "file magic" as known-plain if applicable. This can be faster but
    not 100% safe in all situations.

NOTE: By default it is assumed that all files in each archive have the same
password. If that's not the case, the produced hash may be uncrackable.
To avoid this, use -o option to pick a file at a time.
```

***

#### john-data <a href="#john-data" id="john-data"></a>

John the Ripper is a tool designed to help systems administrators to find weak (easy to guess or crack through brute force) passwords, and even automatically mail users warning them about it, if it is desired.

This package contains architecture-independent character sets usable by john and architecture-independent scripts.

**Installed size:** `61.07 MB`\
**How to install:** `sudo apt install john-data`

<details>

<summary>Dependencies:</summary>

* python3

</details>

**1password2john**

***

**7z2john**

***

**DPAPImk2john**

***

**adxcsouf2john**

***

**aem2john**

***

**aix2john**

```
:~# aix2john -h
usage: aix2john [-h] [-s] [-f FILENAME]

options:
  -h, --help   show this help message and exit
  -s           Use this option if "lpa_options = std_hash=true" is activated
  -f FILENAME  Specify the AIX shadow file filename to read (usually
               /etc/security/passwd)
```

***

**andotp2john**

***

**androidbackup2john**

***

**androidfde2john**

```
:~# androidfde2john -h
Usage: /usr/bin/androidfde2john <data partition / image> <footer partition / image>

```

***

**ansible2john**

***

**apex2john**

***

**applenotes2john**

***

**aruba2john**

***

**atmail2john**

***

**axcrypt2john**

***

**bestcrypt2john**

***

**bitcoin2john**

***

**bitshares2john**

***

**bitwarden2john**

***

**bks2john**

```
:~# bks2john -h
Usage: bks2john [options] <.bks / .uber file(s)>

Options:
  -h, --help            show this help message and exit
  -t TYPE, --type=TYPE  BKS keystore type (bks / uber)
```

***

**blockchain2john**

```
:~# blockchain2john -h
usage: /usr/bin/blockchain2john [blockchain wallet files]

options:
  -h, --help  show this help message and exit
  --json      is the wallet using v2 format?
  --base64    does the wallet contain only a base64 string?
```

***

**ccache2john**

***

**cisco2john**

```
:~# cisco2john -h
Usage:	/usr/bin/cisco2john [cisco config file(s)] >>hashfile 2>>seed.txt
	/usr/bin/cisco2john/john -format:md5 -wordlist:seed.txt -rules hashfile

```

***

**cracf2john**

***

**dashlane2john**

***

**deepsound2john**

```
:~# deepsound2john -h
usage: deepsound2john [-h] [--verbose] file [file ...]

positional arguments:
  file

options:
  -h, --help     show this help message and exit
  --verbose, -v
```

***

**diskcryptor2john**

***

**dmg2john**

***

**ecryptfs2john**

***

**ejabberd2john**

***

**electrum2john**

```
:~# electrum2john -h
Usage: electrum2john [options]

Options:
  -h, --help  show this help message and exit
  -t          force generation of truncated hashes
```

***

**encfs2john**

***

**enpass2john**

***

**enpass5tojohn**

***

**ethereum2john**

***

**filezilla2john**

***

**geli2john**

***

**hccapx2john**

```
:~# hccapx2john -h
usage: hccapx2john [-h] [-nc NC] [--no-mp] hccapx

hccapx2john, process hccapx file into a format suitable for use with JtR

positional arguments:
  hccapx      hccapx file to process

options:
  -h, --help  show this help message and exit
  -nc NC      AP nonce correction to be used, 0 to disable, default 8
  --no-mp     disable message_pair BE/LE/nc detection
```

***

**htdigest2john**

***

**ibmiscanner2john**

***

**ikescan2john**

***

**ios7tojohn**

***

**itunes\_backup2john**

***

**iwork2john**

***

**kdcdump2john**

***

**keychain2john**

***

**keyring2john**

```
:~# keyring2john -h
usage: keyring2john [-h] KEYRING_FILE

keyring2john.py -> convert Gnome Keyring files to john format.

positional arguments:
  KEYRING_FILE  Input Gnome Keyring file

options:
  -h, --help    show this help message and exit
```

***

**keystore2john**

```
:~# keystore2john -h
Traceback (most recent call last):
  File "/usr/bin/keystore2john", line 80, in process_file
    fd = open(filename, "rb")
         ^^^^^^^^^^^^^^^^^^^^
FileNotFoundError: [Errno 2] No such file or directory: '-h'

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/usr/bin/keystore2john", line 187, in <module>
    process_file(sys.argv[i])
  File "/usr/bin/keystore2john", line 83, in process_file
    sys.stderr.write("! %s: %s\n" % filename, str(e))
                     ~~~~~~~~~~~~~^~~~~~~~~~
TypeError: not enough arguments for format string
```

***

**kirbi2john**

```
:~# kirbi2john -h
usage: kirbi2john [-h] [-o [crack_file]] file.kirbi [file.kirbi ...]

Read Mimikatz kerberos ticket then modify it and save it in crack_file

positional arguments:
  file.kirbi       File name to crack. Use asterisk '*' for many files. Files
                   are exported with mimikatz or from extracttgsrepfrompcap.py

options:
  -h, --help       show this help message and exit
  -o [crack_file]  File to save crackable output to (default is stdout
```

***

**known\_hosts2john**

***

**krb2john**

***

**kwallet2john**

***

**lastpass2john**

***

**ldif2john**

***

**libreoffice2john**

***

**lion2john**

***

**lotus2john**

***

**luks2john**

***

**mac2john**

```
:~# mac2john -h
-h : [Errno 2] No such file or directory: '-h'
```

***

**mcafee\_epo2john**

***

**monero2john**

***

**money2john**

***

**mosquitto2john**

```
:~# mosquitto2john -h
usage: mosquitto2john [-h] [-hc] [passwd_file ...]

positional arguments:
  passwd_file     Path to the source mosquitto_passwd file(s).

options:
  -h, --help      show this help message and exit
  -hc, --hashcat  Convert hashes to hashcat friendly formats.

Find more Information:
    See doc/README-mosquitto.md for info/troubleshooting.
```

***

**mozilla2john**

***

**multibit2john**

***

**neo2john**

***

**office2john**

***

**openbsd\_softraid2john**

***

**openssl2john**

```
:~# openssl2john -h
Usage: openssl2john [options]

Options:
  -h, --help    show this help message and exit
  -p PLAINTEXT  
  -a MINASCII   
  -c CIPHER     
  -m MD         
```

***

**padlock2john**

***

**pcap2john**

***

**pdf2john**

```
:~# pdf2john --help
Syntax:  pdf2john.pl <.pdf file(s)>
```

***

**pem2john**

***

**pfx2john**

***

**pgpdisk2john**

***

**pgpsda2john**

***

**pgpwde2john**

***

**prosody2john**

***

**ps\_token2john**

```
:~# ps_token2john -h
Based on tokenchpoken v0.5 beta's parse.py file
Oracle PS_TOKEN cracker. Token parser

Alexey Tyurin - a.tyurin at erpscan.io
ERPScan Research Group - https://www.erpscan.io

usage: ps_token2john [-h] -c COOKIE

options:
  -h, --help  show this help message and exit
  -c COOKIE   Set a victim's PS_TOKEN cookie for parsing
```

***

**pse2john**

***

**pwsafe2john**

***

**radius2john**

***

**restic2john**

***

**sap2john**

***

**sense2john**

***

**signal2john**

***

**sipdump2john**

***

**ssh2john**

```
:~# ssh2john -h
[Errno 2] No such file or directory: '-h'
```

***

**sspr2john**

```
:~# sspr2john -h
usage: sspr2john [-h] -H HOST [-p PORT] -b BASEDN [-s] [-D BINDDN]
                 [-w PASSWORD]

Utility to retrieve NetIQ SSPR hashes from a LDAP server.

options:
  -h, --help            show this help message and exit
  -H HOST, --host HOST  Format like ad.example.net or 192.168.124.10
  -p PORT, --port PORT  Format like 389 or 636
  -b BASEDN, --basedn BASEDN
                        Format like CN=Users,DC=EXAMPLE,DC=NET
  -s, --secure          Use LDAPS (LDAP OVER SSL), recommended
  -D BINDDN, --binddn BINDDN
                        Format like CN=<username>,CN=Users,DC=EXAMPLE,DC=NET
                        or <username>
  -w PASSWORD, --password PASSWORD
                        Password for LDAP bind
```

***

**staroffice2john**

***

**strip2john**

***

**telegram2john**

***

**tezos2john**

```
:~# tezos2john -h
usage: tezos2john [-h] [-i] [-I]

Creates Tezos File For John The Ripper

options:
  -h, --help            show this help message and exit
  -i, --ignoreRules, --ignorerules
                        Ignore All Rules, seed words, checksum, ...
  -I, --ignoreICORules, --ignoreicorules
                        Do Not Check To See If It Is A Valid ICO Format (15
                        seed words)
```

***

**truecrypt2john**

```
:~# truecrypt2john -h
Usage: truecrypt2john [options]

Options:
  -h, --help  show this help message and exit
  -b          
```

***

**vdi2john**

***

**vmx2john**

***

**zed2john**

***

Updated on: 2023-Mar-08\


***
