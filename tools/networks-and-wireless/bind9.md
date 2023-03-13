---
description: >-
  BIND9 is an open-source DNS server software used for secure DNS services. It
  supports DNSSEC, dynamic updates, zone transfers, and load balancing
---

# 🌐 bind9

BIND9, or the Berkeley Internet Name Domain version 9, is a widely used open-source DNS (Domain Name System) server software. It is used by millions of organizations around the world to provide DNS services and is considered to be one of the most stable and secure DNS server software available.

BIND9 was developed by the Internet Systems Consortium (ISC) and is available for free under the ISC license. It runs on most Unix-like operating systems, including Linux, FreeBSD, and macOS, and supports both IPv4 and IPv6 networks.

One of the key features of BIND9 is its ability to provide secure DNS services. It uses a variety of security mechanisms to prevent unauthorized access and ensure the integrity of DNS data. For example, BIND9 supports DNSSEC (DNS Security Extensions), which provides a mechanism for digital signatures to be added to DNS data, allowing clients to verify the authenticity of DNS responses. It also supports TSIG (Transaction Signatures), which provides a mechanism for authenticating DNS messages between servers, preventing unauthorized updates to DNS data.

BIND9 also provides a range of features that can help organizations manage their DNS infrastructure more effectively. For example, it supports dynamic updates, allowing DNS records to be updated automatically when changes occur. It also provides support for zone transfers, allowing DNS data to be replicated between servers, and load balancing, allowing DNS queries to be distributed across multiple servers to improve performance and availability.

In addition to its core features, BIND9 also supports a range of third-party plugins and extensions. These include plugins for logging and monitoring, as well as extensions for implementing custom DNS record types and other advanced functionality.

Despite its many strengths, BIND9 is not without its vulnerabilities. Like all software, it is subject to security vulnerabilities that can be exploited by attackers. As a result, it is important for organizations that use BIND9 to keep their software up-to-date with the latest security patches and to follow best practices for securing their DNS infrastructure.

In summary, BIND9 is a powerful and widely used DNS server software that provides secure, reliable DNS services to organizations around the world. Its support for DNSSEC and other security mechanisms make it an essential tool for organizations that need to protect their DNS infrastructure from attack, while its range of features and extensions provide flexibility and ease of management.

#### bind9 <a href="#bind9" id="bind9"></a>

The Berkeley Internet Name Domain (BIND 9) implements an Internet domain name server. BIND 9 is the most widely-used name server software on the Internet, and is supported by the Internet Software Consortium, [www.isc.org](https://www.isc.org/).

This package provides the server and related configuration files.

**Installed size:** `1.10 MB`\
**How to install:** `sudo apt install bind9`

<details>

<summary>Dependencies:</summary>

* adduser
* bind9-libs
* bind9-utils
* debconf | debconf-2.0
* dns-root-data
* init-system-helpers
* iproute2
* libc6
* libcap2
* libfstrm0
* libjson-c5
* liblmdb0
* libmaxminddb0
* libnghttp2-14
* libprotobuf-c1
* libssl3
* libsystemd0
* libuv1
* libxml2
* lsb-base
* netbase
* zlib1g

</details>

**arpaname**

Translate IP addresses to the corresponding ARPA names

```
:~# man arpaname
ARPANAME(1)                         BIND 9                         ARPANAME(1)

NAME
       arpaname - translate IP addresses to the corresponding ARPA names

SYNOPSIS
       arpaname {ipaddress ...}

DESCRIPTION
       arpaname  translates  IP addresses (IPv4 and IPv6) to the corresponding
       IN-ADDR.ARPA or IP6.ARPA names.

SEE ALSO
       BIND 9 Administrator Reference Manual.

AUTHOR
       Internet Systems Consortium

COPYRIGHT
       2023, Internet Systems Consortium

9.18.12-1-Debian                  2023-02-03                       ARPANAME(1)
```

***

**ddns-confgen**

Ddns key generation tool

```
:~# ddns-confgen -h
Usage:
 ddns-confgen [-a alg] [-k keyname] [-q] [-s name | -z zone]
  -a alg:        algorithm (default hmac-sha256)
  -k keyname:    name of the key as it will be used in named.conf
  -s name:       domain name to be updated using the created key
  -z zone:       name of the zone as it will be used in named.conf
  -q:            quiet mode: print the key, with no explanatory text
```

***

**dnssec-importkey**

Import DNSKEY records from external systems so they can be managed

```
:~# dnssec-importkey --help
dnssec-importkey: invalid argument --
Usage:
    dnssec-importkey options [-K dir] keyfile

    dnssec-importkey options -f file [keyname]

Version: 9.18.12-1-Debian
Options:
    -f file: read key from zone file
    -K <directory>: directory in which to store the key files
    -L ttl:             set default key TTL
    -v <verbose level>
    -V: print version information
    -h: print usage and exit
Timing options:
    -P date/[+-]offset/none: set/unset key publication date
    -P sync date/[+-]offset/none: set/unset CDS and CDNSKEY publication date
    -D date/[+-]offset/none: set/unset key deletion date
    -D sync date/[+-]offset/none: set/unset CDS and CDNSKEY deletion date
```

***

**named**

Internet domain name server

```
:~# named -h
usage: named [-4|-6] [-c conffile] [-d debuglevel] [-D comment] [-E engine]
             [-f|-g] [-L logfile] [-n number_of_cpus] [-p port] [-s]
             [-S sockets] [-t chrootdir] [-u username] [-U listeners]
             [-X lockfile] [-m {usage|trace|record|size|mctx}]
             [-M fill|nofill]
usage: named [-v|-V|-C]
named: unknown option '-h'
```

***

**named-journalprint**

Print zone journal in human-readable form

```
:~# named-journalprint -h
named-journalprint: illegal option -- h
Usage: named-journalprint [-dux] journal
```

***

**named-nzd2nzf**

Convert an NZD database to NZF text format

```
:~# man named-nzd2nzf
NAMED-NZD2NZF(1)                    BIND 9                    NAMED-NZD2NZF(1)

NAME
       named-nzd2nzf - convert an NZD database to NZF text format

SYNOPSIS
       named-nzd2nzf {filename}

DESCRIPTION
       named-nzd2nzf  converts  an NZD database to NZF format and prints it to
       standard output. This can be used to review the configuration of  zones
       that  were  added to named via rndc addzone. It can also be used to re-
       store the old file format when rolling back from  a  newer  version  of
       BIND to an older version.

ARGUMENTS
       filename
              This  is  the  name  of  the  .nzd file whose contents should be
              printed.

SEE ALSO
       BIND 9 Administrator Reference Manual.

AUTHOR
       Internet Systems Consortium

COPYRIGHT
       2023, Internet Systems Consortium

9.18.12-1-Debian                  2023-02-03                  NAMED-NZD2NZF(1)
```

***

**named-rrchecker**

Syntax checker for individual DNS resource records

```
:~# named-rrchecker --help
named-rrchecker: illegal option -- -
usage: named-rrchecker [-o origin] [-hpCPTu]
	-h: print this help message
	-o origin: set origin to be used when interpreting the record
	-p: print the record in canonical format
	-C: list the supported class names
	-P: list the supported private type names
	-T: list the supported standard type names
	-u: print the record in unknown record format
```

***

**nsec3hash**

Generate NSEC3 hash

```
:~# nsec3hash -h
nsec3hash: illegal option -- h
Usage: nsec3hash salt algorithm iterations domain
       nsec3hash -r algorithm flags iterations salt domain
```

***

**tsig-keygen**

TSIG key generation tool

```
:~# tsig-keygen -h
Usage:
 tsig-keygen [-a alg] [keyname]
  -a alg:        algorithm (default hmac-sha256)

```

***

#### bind9-dev <a href="#bind9-dev" id="bind9-dev"></a>

The Berkeley Internet Name Domain (BIND 9) implements an Internet domain name server. BIND 9 is the most widely-used name server software on the Internet, and is supported by the Internet Software Consortium, [www.isc.org](https://www.isc.org/).

This package contains a bundle of static libraries and header files used by BIND 9.

Please be aware that the BIND 9 libraries are considered private by upstream developers and the API and ABI might break at any time.

**Installed size:** `1.76 MB`\
**How to install:** `sudo apt install bind9-dev`

<details>

<summary>Dependencies:</summary>

* bind9-libs

</details>

***

#### bind9-dnsutils <a href="#bind9-dnsutils" id="bind9-dnsutils"></a>

The Berkeley Internet Name Domain (BIND 9) implements an Internet domain name server. BIND 9 is the most widely-used name server software on the Internet, and is supported by the Internet Software Consortium, [www.isc.org](https://www.isc.org/).

This package delivers various client programs related to DNS that are derived from the BIND 9 source tree.

* dig - query the DNS in various ways
* nslookup - the older way to do it
* nsupdate - perform dynamic updates (See RFC2136)

**Installed size:** `721 KB`\
**How to install:** `sudo apt install bind9-dnsutils`

<details>

<summary>Dependencies:</summary>

* bind9-host | host
* bind9-libs
* libc6
* libedit2
* libidn2-0
* libkrb5-3
* libprotobuf-c1

</details>

**delv**

DNS lookup and validation utility

```
:~# delv --help
Invalid option: --help
Usage:  delv [@server] {q-opt} {d-opt} [domain] [q-type] [q-class]
Where:  domain	  is in the Domain Name System
        q-class  is one of (in,hs,ch,...) [default: in]
        q-type   is one of (a,any,mx,ns,soa,hinfo,axfr,txt,...) [default:a]
        q-opt    is one of:
                 -4                  (use IPv4 query transport only)
                 -6                  (use IPv6 query transport only)
                 -a anchor-file      (specify root trust anchor)
                 -b address[#port]   (bind to source address/port)
                 -c class            (option included for compatibility;
                 -d level            (set debugging level)
                 -h                  (print help and exit)
                 -i                  (disable DNSSEC validation)
                 -m                  (enable memory usage debugging)
                 -p port             (specify port number)
                 -q name             (specify query name)
                 -t type             (specify query type)
                                      only IN is supported)
                 -v                  (print version and exit)
                 -x dot-notation     (shortcut for reverse lookups)
        d-opt    is of the form +keyword[=value], where keyword is:
                 +[no]all            (Set or clear all display flags)
                 +[no]class          (Control display of class)
                 +[no]comments       (Control display of comment lines)
                 +[no]crypto         (Control display of cryptographic
                                      fields in records)
                 +[no]dlv            (Obsolete)
                 +[no]dnssec         (Display DNSSEC records)
                 +[no]mtrace         (Trace messages received)
                 +[no]multiline      (Print records in an expanded format)
                 +[no]root           (DNSSEC validation trust anchor)
                 +[no]rrcomments     (Control display of per-record comments)
                 +[no]rtrace         (Trace resolver fetches)
                 +[no]short          (Short form answer)
                 +[no]split=##       (Split hex/base64 fields into chunks)
                 +[no]tcp            (TCP mode)
                 +[no]ttl            (Control display of ttls in records)
                 +[no]trust          (Control display of trust level)
                 +[no]unknownformat  (Print RDATA in RFC 3597 "unknown" format)
                 +[no]vtrace         (Trace validation process)
                 +[no]yaml           (Present the results as YAML)
```

***

**dig**

DNS lookup utility

```
:~# dig -h
Usage:  dig [@global-server] [domain] [q-type] [q-class] {q-opt}
            {global-d-opt} host [@local-server] {local-d-opt}
            [ host [@local-server] {local-d-opt} [...]]
Where:  domain	  is in the Domain Name System
        q-class  is one of (in,hs,ch,...) [default: in]
        q-type   is one of (a,any,mx,ns,soa,hinfo,axfr,txt,...) [default:a]
                 (Use ixfr=version for type ixfr)
        q-opt    is one of:
                 -4                  (use IPv4 query transport only)
                 -6                  (use IPv6 query transport only)
                 -b address[#port]   (bind to source address/port)
                 -c class            (specify query class)
                 -f filename         (batch mode)
                 -k keyfile          (specify tsig key file)
                 -m                  (enable memory usage debugging)
                 -p port             (specify port number)
                 -q name             (specify query name)
                 -r                  (do not read ~/.digrc)
                 -t type             (specify query type)
                 -u                  (display times in usec instead of msec)
                 -x dot-notation     (shortcut for reverse lookups)
                 -y [hmac:]name:key  (specify named base64 tsig key)
        d-opt    is of the form +keyword[=value], where keyword is:
                 +[no]aaflag         (Set AA flag in query (+[no]aaflag))
                 +[no]aaonly         (Set AA flag in query (+[no]aaflag))
                 +[no]additional     (Control display of additional section)
                 +[no]adflag         (Set AD flag in query (default on))
                 +[no]all            (Set or clear all display flags)
                 +[no]answer         (Control display of answer section)
                 +[no]authority      (Control display of authority section)
                 +[no]badcookie      (Retry BADCOOKIE responses)
                 +[no]besteffort     (Try to parse even illegal messages)
                 +bufsize[=###]      (Set EDNS0 Max UDP packet size)
                 +[no]cdflag         (Set checking disabled flag in query)
                 +[no]class          (Control display of class in records)
                 +[no]cmd            (Control display of command line -
                                      global option)
                 +[no]comments       (Control display of packet header
                                      and section name comments)
                 +[no]cookie         (Add a COOKIE option to the request)
                 +[no]crypto         (Control display of cryptographic
                                      fields in records)
                 +[no]defname        (Use search list (+[no]search))
                 +[no]dns64prefix    (Get the DNS64 prefixes from ipv4only.arpa)
                 +[no]dnssec         (Request DNSSEC records)
                 +domain=###         (Set default domainname)
                 +[no]edns[=###]     (Set EDNS version) [0]
                 +ednsflags=###      (Set EDNS flag bits)
                 +[no]ednsnegotiation (Set EDNS version negotiation)
                 +ednsopt=###[:value] (Send specified EDNS option)
                 +noednsopt          (Clear list of +ednsopt options)
                 +[no]expandaaaa     (Expand AAAA records)
                 +[no]expire         (Request time to expire)
                 +[no]fail           (Don't try next server on SERVFAIL)
                 +[no]header-only    (Send query without a question section)
                 +[no]https[=###]    (DNS-over-HTTPS mode) [/]
                 +[no]https-get      (Use GET instead of default POST method while using HTTPS)
                 +[no]http-plain[=###]    (DNS over plain HTTP mode) [/]
                 +[no]https-plain-get      (Use GET instead of default POST method while using plain HTTP)
                 +[no]identify       (ID responders in short answers)
                 +[no]idnin          (Parse IDN names [default=on on tty])
                 +[no]idnout         (Convert IDN response [default=on on tty])
                 +[no]ignore         (Don't revert to TCP for TC responses.)
                 +[no]keepalive      (Request EDNS TCP keepalive)
                 +[no]keepopen       (Keep the TCP socket open between queries)
                 +[no]multiline      (Print records in an expanded format)
                 +ndots=###          (Set search NDOTS value)
                 +[no]nsid           (Request Name Server ID)
                 +[no]nssearch       (Search all authoritative nameservers)
                 +[no]onesoa         (AXFR prints only one soa record)
                 +[no]opcode=###     (Set the opcode of the request)
                 +padding=###        (Set padding block size [0])
                 +qid=###            (Specify the query ID to use when sending queries)
                 +[no]qr             (Print question before sending)
                 +[no]question       (Control display of question section)
                 +[no]raflag         (Set RA flag in query (+[no]raflag))
                 +[no]rdflag         (Recursive mode (+[no]recurse))
                 +[no]recurse        (Recursive mode (+[no]rdflag))
                 +retry=###          (Set number of UDP retries) [2]
                 +[no]rrcomments     (Control display of per-record comments)
                 +[no]search         (Set whether to use searchlist)
                 +[no]short          (Display nothing except short
                                      form of answers - global option)
                 +[no]showbadcookie  (Show BADCOOKIE message)
                 +[no]showsearch     (Search with intermediate results)
                 +[no]split=##       (Split hex/base64 fields into chunks)
                 +[no]stats          (Control display of statistics)
                 +subnet=addr        (Set edns-client-subnet option)
                 +[no]tcflag         (Set TC flag in query (+[no]tcflag))
                 +[no]tcp            (TCP mode (+[no]vc))
                 +timeout=###        (Set query timeout) [5]
                 +[no]tls            (DNS-over-TLS mode)
                 +[no]tls-ca[=file]  (Enable remote server's TLS certificate validation)
                 +[no]tls-hostname=hostname (Explicitly set the expected TLS hostname)
                 +[no]tls-certfile=file (Load client TLS certificate chain from file)
                 +[no]tls-keyfile=file (Load client TLS private key from file)
                 +[no]trace          (Trace delegation down from root [+dnssec])
                 +tries=###          (Set number of UDP attempts) [3]
                 +[no]ttlid          (Control display of ttls in records)
                 +[no]ttlunits       (Display TTLs in human-readable units)
                 +[no]unknownformat  (Print RDATA in RFC 3597 "unknown" format)
                 +[no]vc             (TCP mode (+[no]tcp))
                 +[no]yaml           (Present the results as YAML)
                 +[no]zflag          (Set Z flag in query)
        global d-opts and servers (before host name) affect all queries.
        local d-opts and servers (after host name) affect only that lookup.
        -h                           (print help and exit)
        -v                           (print version and exit)
```

***

**dnstap-read**

Print dnstap data in human-readable form

```
:~# dnstap-read -h
dnstap-read: illegal option -- h
dnstap-read [-mpxy] [filename]
	-m	trace memory allocations
	-p	print the full DNS message
	-x	use hex format to print DNS message
	-y	print YAML format (implies -p)
```

***

**mdig**

DNS pipelined lookup utility

```
:~# mdig -h
Usage: mdig @server {global-opt} host
           {local-opt} [ host {local-opt} [...]]
Where:
 anywhere opt    is one of:
                 -f filename         (batch mode)
                 -h                  (print help and exit)
                 -v                  (print version and exit)
 global opt      is one of:
                 -4                  (use IPv4 query transport only)
                 -6                  (use IPv6 query transport only)
                 -b address[#port]   (bind to source address/port)
                 -p port             (specify port number)
                 -m                  (enable memory usage debugging)
                 +[no]vc             (TCP mode)
                 +[no]tcp            (TCP mode, alternate syntax)
                 +[no]besteffort     (Try to parse even illegal messages)
                 +[no]cl             (Control display of class in records)
                 +[no]comments       (Control display of comment lines)
                 +[no]rrcomments     (Control display of per-record comments)
                 +[no]crypto         (Control display of cryptographic fields in records)
                 +[no]question       (Control display of question)
                 +[no]answer         (Control display of answer)
                 +[no]authority      (Control display of authority)
                 +[no]additional     (Control display of additional)
                 +[no]short          (Disable everything except short
                                      form of answer)
                 +[no]ttlid          (Control display of ttls in records)
                 +[no]ttlunits       (Display TTLs in human-readable units)
                 +[no]unknownformat  (Print RDATA in RFC 3597 "unknown" format)
                 +[no]all            (Set or clear all display flags)
                 +[no]multiline      (Print records in an expanded format)
                 +[no]split=##       (Split hex/base64 fields into chunks)
 local opt       is one of:
                 -c class            (specify query class)
                 -t type             (specify query type)
                 -x dot-notation     (shortcut for reverse lookups)
                 +timeout=###        (Set query timeout) [UDP=5,TCP=10]
                 +udptimeout=###     (Set timeout before UDP retry)
                 +tries=###          (Set number of UDP attempts) [3]
                 +retry=###          (Set number of UDP retries) [2]
                 +bufsize=###        (Set EDNS0 Max UDP packet size)
                 +subnet=addr        (Set edns-client-subnet option)
                 +[no]edns[=###]     (Set EDNS version) [0]
                 +ednsflags=###      (Set EDNS flag bits)
                 +ednsopt=###[:value] (Send specified EDNS option)
                 +noednsopt          (Clear list of +ednsopt options)
                 +[no]recurse        (Recursive mode)
                 +[no]aaonly         (Set AA flag in query (+[no]aaflag))
                 +[no]adflag         (Set AD flag in query)
                 +[no]cdflag         (Set CD flag in query)
                 +[no]zflag          (Set Z flag in query)
                 +[no]dnssec         (Request DNSSEC records)
                 +[no]expire         (Request time to expire)
                 +[no]cookie[=###]   (Send a COOKIE option)
                 +[no]nsid           (Request Name Server ID)
```

***

**nslookup**

Query Internet name servers interactively

```
:~# man nslookup
NSLOOKUP(1)                         BIND 9                         NSLOOKUP(1)

NAME
       nslookup - query Internet name servers interactively

SYNOPSIS
       nslookup [-option] [name | -] [server]

DESCRIPTION
       nslookup  is a program to query Internet domain name servers.  nslookup
       has two modes: interactive and non-interactive. Interactive mode allows
       the  user to query name servers for information about various hosts and
       domains or to print a list of hosts in a domain.  Non-interactive  mode
       prints just the name and requested information for a host or domain.

ARGUMENTS
       Interactive mode is entered in the following cases:

       a. when no arguments are given (the default name server is used);

       b. when  the  first argument is a hyphen (-) and the second argument is
          the host name or Internet address of a name server.

       Non-interactive mode is used when the name or Internet address  of  the
       host  to be looked up is given as the first argument. The optional sec-
       ond argument specifies the host name or address of a name server.

       Options can also be specified on the command line if they  precede  the
       arguments  and  are  prefixed with a hyphen. For example, to change the
       default query type to host information, with an initial timeout  of  10
       seconds, type:

          nslookup -query=hinfo  -timeout=10

       The -version option causes nslookup to print the version number and im-
       mediately exit.

INTERACTIVE COMMANDS
       host [server]
              This command looks up information for host using the current de-
              fault server or using server, if specified. If host is an Inter-
              net address and the query type is A or PTR, the name of the host
              is  returned. If host is a name and does not have a trailing pe-
              riod (.), the search list is used to qualify the name.

              To look up a host not in the current domain, append a period  to
              the name.

       server domain | lserver domain
              These commands change the default server to domain; lserver uses
              the initial server to look up information  about  domain,  while
              server  uses the current default server. If an authoritative an-
              swer cannot be found, the names of servers that might  have  the
              answer are returned.

       root   This command is not implemented.

       finger This command is not implemented.

       ls     This command is not implemented.

       view   This command is not implemented.

       help   This command is not implemented.

       ?      This command is not implemented.

       exit   This command exits the program.

       set keyword[=value]
              This  command  is  used to change state information that affects
              the lookups. Valid keywords are:

              all    This keyword prints the current values of the  frequently
                     used  options  to  set. Information about the current de-
                     fault server and host is also printed.

              class=value
                     This keyword changes the query class to one of:

                     IN     the Internet class

                     CH     the Chaos class

                     HS     the Hesiod class

                     ANY    wildcard

                     The class specifies the protocol group  of  the  informa-
                     tion.  The  default is IN; the abbreviation for this key-
                     word is cl.

              nodebug
                     This keyword turns on or off the display of the full  re-
                     sponse  packet,  and  any  intermediate response packets,
                     when searching. The default for this keyword is  nodebug;
                     the abbreviation for this keyword is [no]deb.

              nod2   This  keyword  turns  debugging mode on or off. This dis-
                     plays more about what nslookup is doing. The  default  is
                     nod2.

              domain=name
                     This keyword sets the search list to name.

              nosearch
                     If  the  lookup request contains at least one period, but
                     does not end with a trailing period, this keyword appends
                     the domain names in the domain search list to the request
                     until an answer is received. The default is search.

              port=value
                     This keyword changes the default TCP/UDP name server port
                     to  value from its default, port 53. The abbreviation for
                     this keyword is po.

              querytype=value | type=value
                     This keyword changes the type of the information query to
                     value.  The  defaults  are A and then AAAA; the abbrevia-
                     tions for these keywords are q and ty.

                     Please note that it is only possible to specify one query
                     type. Only the default behavior looks up both when an al-
                     ternative is not specified.

              norecurse
                     This keyword tells the name server to query other servers
                     if  it  does not have the information. The default is re-
                     curse; the abbreviation for this keyword is [no]rec.

              ndots=number
                     This keyword sets the number of dots  (label  separators)
                     in  a  domain that disables searching. Absolute names al-
                     ways stop searching.

              retry=number
                     This keyword sets the number of retries to number.

              timeout=number
                     This keyword changes the initial timeout interval to wait
                     for a reply to number, in seconds.

              novc   This  keyword indicates that a virtual circuit should al-
                     ways be used when sending requests to the  server.   novc
                     is the default.

              nofail This  keyword  tries  the next nameserver if a nameserver
                     responds with SERVFAIL or a referral (nofail), or  termi-
                     nates the query (fail) on such a response. The default is
                     nofail.

RETURN VALUES
       nslookup returns with an exit status of 1 if any query  failed,  and  0
       otherwise.

IDN SUPPORT
       If  nslookup  has  been  built with IDN (internationalized domain name)
       support, it can accept and display non-ASCII domain names. nslookup ap-
       propriately converts character encoding of a domain name before sending
       a request to a DNS server or displaying a reply from  the  server.   To
       turn  off IDN support, define the IDN_DISABLE environment variable. IDN
       support is disabled if the variable is set when nslookup runs, or  when
       the standard output is not a tty.

FILES
       /etc/resolv.conf

SEE ALSO
       dig(1), host(1), named(8).

AUTHOR
       Internet Systems Consortium

COPYRIGHT
       2023, Internet Systems Consortium

9.18.12-1-Debian                  2023-02-03                       NSLOOKUP(1)
```

***

**nsupdate**

Dynamic DNS update utility

```
:~# nsupdate --help
nsupdate: illegal option -- -
nsupdate: invalid argument --
usage: nsupdate [-CdDi] [-L level] [-l] [-g | -o | -y keyname:secret | -k keyfile] [-p port] [-v] [-V] [-P] [-T] [-4 | -6] [filename]
```

***

#### bind9-doc <a href="#bind9-doc" id="bind9-doc"></a>

This package provides various documents that are useful for maintaining a working BIND 9 installation.

**Installed size:** `7.30 MB`\
**How to install:** `sudo apt install bind9-doc`

***

#### bind9-host <a href="#bind9-host" id="bind9-host"></a>

This package provides the ‘host’ DNS lookup utility in the form that is bundled with the BIND 9 sources.

**Installed size:** `381 KB`\
**How to install:** `sudo apt install bind9-host`

<details>

<summary>Dependencies:</summary>

* bind9-libs
* libc6
* libidn2-0

</details>

**host**

DNS lookup utility

```
:~# host -h
host: illegal option -- h
Usage: host [-aCdilrTvVw] [-c class] [-N ndots] [-t type] [-W time]
            [-R number] [-m flag] [-p port] hostname [server]
       -a is equivalent to -v -t ANY
       -A is like -a but omits RRSIG, NSEC, NSEC3
       -c specifies query class for non-IN data
       -C compares SOA records on authoritative nameservers
       -d is equivalent to -v
       -l lists all hosts in a domain, using AXFR
       -m set memory debugging flag (trace|record|usage)
       -N changes the number of dots allowed before root lookup is done
       -p specifies the port on the server to query
       -r disables recursive processing
       -R specifies number of retries for UDP packets
       -s a SERVFAIL response should stop query
       -t specifies the query type
       -T enables TCP/IP mode
       -U enables UDP mode
       -v enables verbose output
       -V print version number and exit
       -w specifies to wait forever for a reply
       -W specifies how long to wait for a reply
       -4 use IPv4 query transport only
       -6 use IPv6 query transport only
```

***

#### bind9-libs <a href="#bind9-libs" id="bind9-libs"></a>

The Berkeley Internet Name Domain (BIND 9) implements an Internet domain name server. BIND 9 is the most widely-used name server software on the Internet, and is supported by the Internet Software Consortium, [www.isc.org](https://www.isc.org/).

This package contains a bundle of shared libraries used by BIND 9.

**Installed size:** `8.58 MB`\
**How to install:** `sudo apt install bind9-libs`

<details>

<summary>Dependencies:</summary>

* libc6
* libfstrm0
* libgssapi-krb5-2
* libjemalloc2
* libjson-c5
* libkrb5-3
* liblmdb0
* libmaxminddb0
* libnghttp2-14
* libprotobuf-c1
* libssl3
* libuv1
* libxml2
* zlib1g

</details>

***

#### bind9-utils <a href="#bind9-utils" id="bind9-utils"></a>

This package provides various utilities that are useful for maintaining a working BIND 9 installation.

**Installed size:** `840 KB`\
**How to install:** `sudo apt install bind9-utils`

<details>

<summary>Dependencies:</summary>

* bind9-libs
* libc6

</details>

**dnssec-cds**

Change DS records for a child zone based on CDS/CDNSKEY

```
:~# dnssec-cds -h
Usage:
    dnssec-cds options [options] -f <file> -d <path> <domain>
Version: 9.18.12-1-Debian
Options:
    -a <algorithm>     digest algorithm (SHA-1 / SHA-256 / SHA-384)
    -c <class>         of domain (default IN)
    -D                 prefer CDNSKEY records instead of CDS
    -d <file|dir>      where to find parent dsset- file
    -f <file>          child DNSKEY+CDNSKEY+CDS+RRSIG records
    -i[extension]      update dsset- file in place
    -s <start-time>    oldest permitted child signatures
    -u                 emit nsupdate script
    -T <ttl>           TTL of DS records
    -V                 print version
    -v <verbosity>
```

***

**dnssec-dsfromkey**

DNSSEC DS RR generation tool

```
:~# dnssec-dsfromkey --help
dnssec-dsfromkey: invalid argument --
Usage:
    dnssec-dsfromkey [options] keyfile

    dnssec-dsfromkey [options] -f zonefile [zonename]

    dnssec-dsfromkey [options] -s dnsname

    dnssec-dsfromkey [-h|-V]

Version: 9.18.12-1-Debian
Options:
    -1: digest algorithm SHA-1
    -2: digest algorithm SHA-256
    -a algorithm: digest algorithm (SHA-1, SHA-256 or SHA-384)
    -A: include all keys in DS set, not just KSKs (-f only)
    -c class: rdata class for DS set (default IN) (-f or -s only)
    -C: print CDS records
    -f zonefile: read keys from a zone file
    -h: print help information
    -K directory: where to find key or keyset files
    -s: read keys from keyset-<dnsname> file
    -T: TTL of output records (omitted by default)
    -v level: verbosity
    -V: print version information
Output: DS or CDS RRs
```

***

**dnssec-keyfromlabel**

DNSSEC key generation tool

```
:~# dnssec-keyfromlabel --help
dnssec-keyfromlabel: invalid argument --
Usage:
    dnssec-keyfromlabel -l label [options] name

Version: 9.18.12-1-Debian
Required options:
    -l label: label of the key pair
    name: owner of the key
Other options:
    -a algorithm: 
        DH | RSASHA1 |
        NSEC3RSASHA1 |
        RSASHA256 | RSASHA512 |
        ECDSAP256SHA256 | ECDSAP384SHA384 |
        ED25519 | ED448
    -3: use NSEC3-capable algorithm
    -c class (default: IN)
    -E <engine>:
        name of an OpenSSL engine to use
    -f keyflag: KSK | REVOKE
    -K directory: directory in which to place key files
    -k: generate a TYPE=KEY key
    -L ttl: default key TTL
    -n nametype: ZONE | HOST | ENTITY | USER | OTHER
        (DNSKEY generation defaults to ZONE
    -p protocol: default: 3 [dnssec]
    -t type: AUTHCONF | NOAUTHCONF | NOAUTH | NOCONF (default: AUTHCONF)
    -y: permit keys that might collide
    -v verbose level
    -V: print version information
Date options:
    -P date/[+-]offset: set key publication date
    -P sync date/[+-]offset: set CDS and CDNSKEY publication date
    -A date/[+-]offset: set key activation date
    -R date/[+-]offset: set key revocation date
    -I date/[+-]offset: set key inactivation date
    -D date/[+-]offset: set key deletion date
    -D sync date/[+-]offset: set CDS and CDNSKEY deletion date
    -G: generate key only; do not set -P or -A
    -C: generate a backward-compatible key, omitting all dates
    -S <key>: generate a successor to an existing key
    -i <interval>: prepublication interval for successor key (default: 30 days)
Output:
     K<name>+<alg>+<id>.key, K<name>+<alg>+<id>.private
```

***

**dnssec-keygen**

DNSSEC key generation tool

```
:~# dnssec-keygen --help
dnssec-keygen: invalid argument --
Usage:
    dnssec-keygen [options] name

Version: 9.18.12-1-Debian
    name: owner of the key
Options:
    -K <directory>: write keys into directory
    -k <policy>: generate keys for dnssec-policy
    -l <file>: configuration file with dnssec-policy statement
    -a <algorithm>:
        RSASHA1 | NSEC3RSASHA1 |
        RSASHA256 | RSASHA512 |
        ECDSAP256SHA256 | ECDSAP384SHA384 |
        ED25519 | ED448 | DH
    -3: use NSEC3-capable algorithm
    -b <key size in bits>:
        RSASHA1:	[1024..4096]
        NSEC3RSASHA1:	[1024..4096]
        RSASHA256:	[1024..4096]
        RSASHA512:	[1024..4096]
        DH:		[128..4096]
        ECDSAP256SHA256:	ignored
        ECDSAP384SHA384:	ignored
        ED25519:	ignored
        ED448:	ignored
        (key size defaults are set according to
        algorithm and usage (ZSK or KSK)
    -n <nametype>: ZONE | HOST | ENTITY | USER | OTHER
        (DNSKEY generation defaults to ZONE)
    -c <class>: (default: IN)
    -d <digest bits> (0 => max, default)
    -E <engine>:
        name of an OpenSSL engine to use
    -f <keyflag>: KSK | REVOKE
    -g <generator>: use specified generator (DH only)
    -L <ttl>: default key TTL
    -p <protocol>: (default: 3 [dnssec])
    -s <strength>: strength value this key signs DNS records with (default: 0)
    -T <rrtype>: DNSKEY | KEY (default: DNSKEY; use KEY for SIG(0))
    -t <type>: AUTHCONF | NOAUTHCONF | NOAUTH | NOCONF (default: AUTHCONF)
    -h: print usage and exit
    -m <memory debugging mode>:
       usage | trace | record | size | mctx
    -v <level>: set verbosity level (0 - 10)
    -V: print version information
Timing options:
    -P date/[+-]offset/none: set key publication date (default: now)
    -P sync date/[+-]offset/none: set CDS and CDNSKEY publication date
    -A date/[+-]offset/none: set key activation date (default: now)
    -R date/[+-]offset/none: set key revocation date
    -I date/[+-]offset/none: set key inactivation date
    -D date/[+-]offset/none: set key deletion date
    -D sync date/[+-]offset/none: set CDS and CDNSKEY deletion date
    -G: generate key only; do not set -P or -A
    -C: generate a backward-compatible key, omitting all dates
    -S <key>: generate a successor to an existing key
    -i <interval>: prepublication interval for successor key (default: 30 days)
Output:
     K<name>+<alg>+<id>.key, K<name>+<alg>+<id>.private
```

***

**dnssec-revoke**

Set the REVOKED bit on a DNSSEC key

```
:~# dnssec-revoke --help
dnssec-revoke: invalid argument --
Usage:
    dnssec-revoke [options] keyfile

Version: 9.18.12-1-Debian
    -E engine:    specify OpenSSL engine
    -f:           force overwrite
    -h:           help
    -K directory: use directory for key files
    -r:           remove old keyfiles after creating revoked version
    -v level:     set level of verbosity
    -V:           print version information
Output:
     K<name>+<alg>+<new id>.key, K<name>+<alg>+<new id>.private
```

***

**dnssec-settime**

Set the key timing metadata for a DNSSEC key

```
:~# dnssec-settime --help
dnssec-settime: invalid argument --
Usage:
    dnssec-settime [options] keyfile

Version: 9.18.12-1-Debian
General options:
    -E engine:          specify OpenSSL engine
    -f:                 force update of old-style keys
    -K directory:       set key file location
    -L ttl:             set default key TTL
    -v level:           set level of verbosity
    -V:                 print version information
    -h:                 help
Timing options:
    -P date/[+-]offset/none: set/unset key publication date
    -P ds date/[+-]offset/none: set/unset DS publication date
    -P sync date/[+-]offset/none: set/unset CDS and CDNSKEY publication date
    -A date/[+-]offset/none: set/unset key activation date
    -R date/[+-]offset/none: set/unset key revocation date
    -I date/[+-]offset/none: set/unset key inactivation date
    -D date/[+-]offset/none: set/unset key deletion date
    -D ds date/[+-]offset/none: set/unset DS deletion date
    -D sync date/[+-]offset/none: set/unset CDS and CDNSKEY deletion date
    -S <key>: generate a successor to an existing key
    -i <interval>: prepublication interval for successor key (default: 30 days)
Key state options:
    -s: update key state file (default no)
    -g state: set the goal state for this key
    -d state date/[+-]offset: set the DS state
    -k state date/[+-]offset: set the DNSKEY state
    -r state date/[+-]offset: set the RRSIG (KSK) state
    -z state date/[+-]offset: set the RRSIG (ZSK) state
Printing options:
    -p C/P/Psync/A/R/I/D/Dsync/all: print a particular time value or values
    -u:                 print times in unix epoch format
Output:
     K<name>+<alg>+<new id>.key, K<name>+<alg>+<new id>.private
```

***

**dnssec-signzone**

DNSSEC zone signing tool

```
:~# dnssec-signzone --help
dnssec-signzone: illegal option -- -
dnssec-signzone: invalid argument --
Usage:
	dnssec-signzone [options] zonefile [keys]

Version: 9.18.12-1-Debian
Options: (default value in parenthesis) 
	-S:	smart signing: automatically finds key files
		for the zone and determines how they are to be used
	-K directory:
		directory to find key files (.)
	-d directory:
		directory to find dsset-* files (.)
	-g:	update DS records based on child zones' dsset-* files
	-s [YYYYMMDDHHMMSS|+offset]:
		RRSIG start time - absolute|offset (now - 1 hour)
	-e [YYYYMMDDHHMMSS|+offset|"now"+offset]:
		RRSIG end time - absolute|from start|from now (now + 30 days)
	-X [YYYYMMDDHHMMSS|+offset|"now"+offset]:
		DNSKEY RRSIG end - absolute|from start|from now (matches -e)
	-i interval:
		cycle interval - resign if < interval from end ( (end-start)/4 )
	-j jitter:
		randomize signature end time up to jitter seconds
	-v debuglevel (0)
	-q quiet
	-V:	print version information
	-o origin:
		zone origin (name of zonefile)
	-f outfile:
		file the signed zone is written in (zonefile + .signed)
	-I format:
		file format of input zonefile (text)
	-O format:
		file format of signed zone file (text)
	-N format:
		soa serial format of signed zone file (keep)
	-D:
		output only DNSSEC-related records
	-a:	verify generated signatures
	-c class (IN)
	-E engine:
		name of an OpenSSL engine to use
	-P:	disable post-sign verification
	-Q:	remove signatures from keys that are no longer active
	-R:	remove signatures from keys that no longer exist
	-T TTL:	TTL for newly added DNSKEYs
	-t:	print statistics
	-u:	update or replace an existing NSEC/NSEC3 chain
	-x:	sign DNSKEY record with KSKs only, not ZSKs
	-z:	sign all records with KSKs
	-C:	generate a keyset file, for compatibility
		with older versions of dnssec-signzone -g
	-n ncpus (number of cpus present)
	-k key_signing_key
	-3 NSEC3 salt
	-H NSEC3 iterations (10)
	-A NSEC3 optout

Signing Keys: (default: all zone keys that have private keys)
	keyfile (Kname+alg+tag)
```

***

**dnssec-verify**

DNSSEC zone verification tool

```
:~# dnssec-verify --help
dnssec-verify: illegal option -- -
dnssec-verify: illegal option -- e
dnssec-verify: illegal option -- l
dnssec-verify: illegal option -- p
dnssec-verify: invalid argument --
Usage:
	dnssec-verify [options] zonefile [keys]

Version: 9.18.12-1-Debian
Options: (default value in parenthesis) 
	-v debuglevel (0)
	-q quiet
	-V:	print version information
	-o origin:
		zone origin (name of zonefile)
	-I format:
		file format of input zonefile (text)
	-c class (IN)
	-E engine:
		name of an OpenSSL engine to use
	-x:	DNSKEY record signed with KSKs only, not ZSKs
	-z:	All records signed with KSKs
```

***

**named-checkconf**

Named configuration file syntax checking tool

```
:~# named-checkconf --help
named-checkconf: invalid argument --
usage: named-checkconf [-chijlvz] [-p [-x]] [-t directory] [named.conf]
```

***

**named-checkzone**

Zone file validity checking or converting tool

```
:~# named-checkzone --help
named-checkzone: invalid argument --
usage: named-checkzone [-djqvD] [-c class] [-f inputformat] [-F outputformat] [-J filename] [-s (full|relative)] [-t directory] [-w directory] [-k (ignore|warn|fail)] [-m (ignore|warn|fail)] [-n (ignore|warn|fail)] [-r (ignore|warn|fail)] [-i (full|full-sibling|local|local-sibling|none)] [-M (ignore|warn|fail)] [-S (ignore|warn|fail)] [-W (ignore|warn)] [-o filename] zonename [ (filename|-) ]
```

***

**named-compilezone**

Zone file validity checking or converting tool

```
:~# named-compilezone --help
named-compilezone: invalid argument --
usage: named-compilezone [-djqvD] [-c class] [-f inputformat] [-F outputformat] [-J filename] [-s (full|relative)] [-t directory] [-w directory] [-k (ignore|warn|fail)] [-m (ignore|warn|fail)] [-n (ignore|warn|fail)] [-r (ignore|warn|fail)] [-i (full|full-sibling|local|local-sibling|none)] [-M (ignore|warn|fail)] [-S (ignore|warn|fail)] [-W (ignore|warn)] -o filename zonename [ (filename|-) ]
```

***

**rndc**

Name server control utility

```
:~# rndc -h
Usage: rndc [-b address] [-c config] [-s server] [-p port]
	[-k key-file ] [-y key] [-r] [-V] [-4 | -6] command

command is one of the following:

  addzone zone [class [view]] { zone-options }
		Add zone to given view. Requires allow-new-zones option.
  delzone [-clean] zone [class [view]]
		Removes zone from given view.
  dnssec -checkds [-key id [-alg algorithm]] [-when time] (published|withdrawn) zone [class [view]]
		Mark the DS record for the KSK of the given zone as seen
		in the parent.  If the zone has multiple KSKs, select a
		specific key by providing the keytag with -key id and
		optionally the key's algorithm with -alg algorithm.
		Requires the zone to have a dnssec-policy.
  dnssec -rollover -key id [-alg algorithm] [-when time] zone [class [view]]
		Rollover key with id of the given zone. Requires the zone
		to have a dnssec-policy.
  dnssec -status zone [class [view]]
		Show the DNSSEC signing state for the specified zone.
		Requires the zone to have a dnssec-policy.
  dnstap -reopen
		Close, truncate and re-open the DNSTAP output file.
  dnstap -roll count
		Close, rename and re-open the DNSTAP output file(s).
  dumpdb [-all|-cache|-zones|-adb|-bad|-expired|-fail] [view ...]
		Dump cache(s) to the dump file (named_dump.db).
  flush         Flushes all of the server's caches.
  flush [view]	Flushes the server's cache for a view.
  flushname name [view]
		Flush the given name from the server's cache(s)
  flushtree name [view]
		Flush all names under the given name from the server's cache(s)
  freeze	Suspend updates to all dynamic zones.
  freeze zone [class [view]]
		Suspend updates to a dynamic zone.
  halt		Stop the server without saving pending updates.
  halt -p	Stop the server without saving pending updates reporting
		process id.
  loadkeys zone [class [view]]
		Update keys without signing immediately.
  managed-keys refresh [class [view]]
		Check trust anchor for RFC 5011 key changes
  managed-keys status [class [view]]
		Display RFC 5011 managed keys information
  managed-keys sync [class [view]]
		Write RFC 5011 managed keys to disk
  modzone zone [class [view]] { zone-options }
		Modify a zone's configuration.
		Requires allow-new-zones option.
  notify zone [class [view]]
		Resend NOTIFY messages for the zone.
  notrace	Set debugging level to 0.
  nta -dump
		List all negative trust anchors.
  nta [-lifetime duration] [-force] domain [view]
		Set a negative trust anchor, disabling DNSSEC validation
		for the given domain.
		Using -lifetime specifies the duration of the NTA, up
		to one week.
		Using -force prevents the NTA from expiring before its
		full lifetime, even if the domain can validate sooner.
  nta -remove domain [view]
		Remove a negative trust anchor, re-enabling validation
		for the given domain.
  querylog [ on | off ]
		Enable / disable query logging.
  reconfig	Reload configuration file and new zones only.
  recursing	Dump the queries that are currently recursing (named.recursing)
  refresh zone [class [view]]
		Schedule immediate maintenance for a zone.
  reload	Reload configuration file and zones.
  reload zone [class [view]]
		Reload a single zone.
  retransfer zone [class [view]]
		Retransfer a single zone without checking serial number.
  scan		Scan available network interfaces for changes.
  secroots [view ...]
		Write security roots to the secroots file.
  serve-stale [ on | off | reset | status ] [class [view]]
		Control whether stale answers are returned
  showzone zone [class [view]]
		Print a zone's configuration.
  sign zone [class [view]]
		Update zone keys, and sign as needed.
  signing -clear all zone [class [view]]
		Remove the private records for all keys that have
		finished signing the given zone.
  signing -clear <keyid>/<algorithm> zone [class [view]]
		Remove the private record that indicating the given key
		has finished signing the given zone.
  signing -list zone [class [view]]
		List the private records showing the state of DNSSEC
		signing in the given zone.
  signing -nsec3param hash flags iterations salt zone [class [view]]
		Add NSEC3 chain to zone if already signed.
		Prime zone with NSEC3 chain if not yet signed.
  signing -nsec3param none zone [class [view]]
		Remove NSEC3 chains from zone.
  signing -serial <value> zone [class [view]]
		Set the zones's serial to <value>.
  stats		Write server statistics to the statistics file.
  status	Display status of the server.
  stop		Save pending updates to master files and stop the server.
  stop -p	Save pending updates to master files and stop the server
		reporting process id.
  sync [-clean]	Dump changes to all dynamic zones to disk, and optionally
		remove their journal files.
  sync [-clean] zone [class [view]]
		Dump a single zone's changes to disk, and optionally
		remove its journal file.
  tcp-timeouts	Display the tcp-*-timeout option values
  tcp-timeouts initial idle keepalive advertised
		Update the tcp-*-timeout option values
  thaw		Enable updates to all dynamic zones and reload them.
  thaw zone [class [view]]
		Enable updates to a frozen dynamic zone and reload it.
  trace		Increment debugging level by one.
  trace level	Change the debugging level.
  tsig-delete keyname [view]
		Delete a TKEY-negotiated TSIG key.
  tsig-list	List all currently active TSIG keys, including both statically
		configured and TKEY-negotiated keys.
  validation [ on | off | status ] [view]
		Enable / disable DNSSEC validation.
  zonestatus zone [class [view]]
		Display the current status of a zone.

Version: 9.18.12-1-Debian
```

***

**rndc-confgen**

Rndc key generation tool

```
:~# rndc-confgen -h
Usage:
 rndc-confgen [-a] [-b bits] [-c keyfile] [-k keyname] [-p port] [-s addr] [-t chrootdir] [-u user]
  -a:		 generate just the key clause and write it to keyfile (/etc/bind/rndc.key)
  -A alg:	 algorithm (default hmac-sha256)
  -b bits:	 from 1 through 512, default 256; total length of the secret
  -c keyfile:	 specify an alternate key file (requires -a)
  -k keyname:	 the name as it will be used  in named.conf and rndc.conf
  -p port:	 the port named will listen on and rndc will connect to
  -q:		 suppress printing written key path
  -s addr:	 the address to which rndc should connect
  -t chrootdir:	 write a keyfile in chrootdir as well (requires -a)
  -u user:	 set the keyfile owner to "user" (requires -a)
```

***

#### bind9utils <a href="#bind9utils" id="bind9utils"></a>

This is a transitional package. It can safely be removed.

**Installed size:** `260 KB`\
**How to install:** `sudo apt install bind9utils`

<details>

<summary>Dependencies:</summary>

* bind9-utils

</details>

***

#### dnsutils <a href="#dnsutils" id="dnsutils"></a>

This is a transitional package. It can safely be removed.

**Installed size:** `260 KB`\
**How to install:** `sudo apt install dnsutils`

<details>

<summary>Dependencies:</summary>

* bind9-dnsutils

</details>

***
