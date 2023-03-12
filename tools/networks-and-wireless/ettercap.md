---
description: >-
  Ettercap is a network security tool used for sniffing, intercepting, and
  manipulating network traffic, allowing for various types of attacks and
  analysis.
---

# 🌐 ettercap

Ettercap is a powerful and versatile network security tool that is widely used by security professionals and hackers alike for various purposes. It is an open-source and free tool that is available for Windows, Linux, and macOS operating systems.

The tool is primarily used for sniffing, intercepting, and manipulating network traffic. This allows security professionals to perform various types of attacks, including man-in-the-middle (MITM) attacks, password sniffing, and session hijacking. Ettercap can also be used for network mapping, network scanning, and vulnerability analysis.

One of the most significant features of Ettercap is its ability to perform MITM attacks. This allows attackers to intercept and view the communication between two parties on the network, modify the content of the communication, or even inject their own traffic. Ettercap makes it easy to carry out these attacks by providing a user-friendly interface and a wide range of options for customizing the attack.

Another essential feature of Ettercap is its ability to sniff passwords from various protocols, such as HTTP, FTP, Telnet, and SSH. This is particularly useful in situations where security professionals need to test the security of a network by simulating an attack on a user's credentials.

Ettercap also includes a packet filter that can be used to block or redirect specific packets on the network. This can be used to prevent unwanted traffic, such as spam or malware, from entering the network, or to redirect traffic to a different location, such as a honeypot.

In addition to these features, Ettercap also supports plugins that extend its functionality even further. These plugins can be used to add new protocols, filters, or attacks to the tool, making it even more versatile.

Despite its power and usefulness, Ettercap can be a dangerous tool in the hands of malicious actors. It is, therefore, important for security professionals to use it responsibly and only in controlled environments where the potential impact of its use can be minimized.

In conclusion, Ettercap is a highly capable and versatile network security tool that provides security professionals with a wide range of features for testing the security of a network. Its ability to perform MITM attacks, sniff passwords, and filter packets makes it an indispensable tool for security testing and analysis.

### Packages and Binaries:

#### ettercap-common <a href="#ettercap-common" id="ettercap-common"></a>

Ettercap supports active and passive dissection of many protocols (even encrypted ones) and includes many feature for network and host analysis.

Data injection in an established connection and filtering (substitute or drop a packet) on the fly is also possible, keeping the connection synchronized.

Many sniffing modes are implemented, for a powerful and complete sniffing suite. It is possible to sniff in four modes: IP Based, MAC Based, ARP Based (full-duplex) and PublicARP Based (half-duplex).

Ettercap also has the ability to detect a switched LAN, and to use OS fingerprints (active or passive) to find the geometry of the LAN.

This package contains the Common support files, configuration files, plugins, and documentation. You must also install either ettercap-graphical or ettercap-text-only for the actual GUI-enabled or text-only ettercap executable, respectively.

**Installed size:** `2.45 MB`\
**How to install:** `sudo apt install ettercap-common`

<details>

<summary>Dependencies:</summary>

* ethtool
* geoip-database
* libbsd0
* libc6
* libcurl4
* libgeoip1
* libluajit-5.1-2 | libluajit2-5.1-2
* libnet1
* libpcap0.8
* libpcre2-8-0
* libssl3
* zlib1g

</details>

***

#### ettercap-graphical <a href="#ettercap-graphical" id="ettercap-graphical"></a>

Ettercap supports active and passive dissection of many protocols (even encrypted ones) and includes many feature for network and host analysis.

Data injection in an established connection and filtering (substitute or drop a packet) on the fly is also possible, keeping the connection synchronized.

Many sniffing modes are implemented, for a powerful and complete sniffing suite. It is possible to sniff in four modes: IP Based, MAC Based, ARP Based (full-duplex) and PublicARP Based (half-duplex).

Ettercap also has the ability to detect a switched LAN, and to use OS fingerprints (active or passive) to find the geometry of the LAN.

This package contains the ettercap GUI-enabled executable.

**Installed size:** `605 KB`\
**How to install:** `sudo apt install ettercap-graphical`

<details>

<summary>Dependencies:</summary>

* ettercap-common
* libbsd0
* libc6
* libgdk-pixbuf-2.0-0
* libglib2.0-0
* libgtk-3-0
* libncurses6
* libpcre2-8-0
* libtinfo6
* pkexec
* zlib1g

</details>

**ettercap**

Multipurpose sniffer/content filter for man in the middle attacks

```
:~# ettercap -h

ettercap 0.8.3.1 copyright 2001-2020 Ettercap Development Team


Usage: ettercap [OPTIONS] [TARGET1] [TARGET2]

TARGET is in the format MAC/IP/IPv6/PORTs (see the man for further detail)

Sniffing and Attack options:
  -M, --mitm <METHOD:ARGS>    perform a mitm attack
  -o, --only-mitm             don't sniff, only perform the mitm attack
  -b, --broadcast             sniff packets destined to broadcast
  -B, --bridge <IFACE>        use bridged sniff (needs 2 ifaces)
  -p, --nopromisc             do not put the iface in promisc mode
  -S, --nosslmitm             do not forge SSL certificates
  -u, --unoffensive           do not forward packets
  -r, --read <file>           read data from pcapfile <file>
  -f, --pcapfilter <string>   set the pcap filter <string>
  -R, --reversed              use reversed TARGET matching
  -t, --proto <proto>         sniff only this proto (default is all)
      --certificate <file>    certificate file to use for SSL MiTM
      --private-key <file>    private key file to use for SSL MiTM

User Interface Type:
  -T, --text                  use text only GUI
       -q, --quiet                 do not display packet contents
       -s, --script <CMD>          issue these commands to the GUI
  -C, --curses                use curses GUI
  -D, --daemon                daemonize ettercap (no GUI)
  -G, --gtk                   use GTK+ GUI

Logging options:
  -w, --write <file>          write sniffed data to pcapfile <file>
  -L, --log <logfile>         log all the traffic to this <logfile>
  -l, --log-info <logfile>    log only passive infos to this <logfile>
  -m, --log-msg <logfile>     log all the messages to this <logfile>
  -c, --compress              use gzip compression on log files

Visualization options:
  -d, --dns                   resolves ip addresses into hostnames
  -V, --visual <format>       set the visualization format
  -e, --regex <regex>         visualize only packets matching this regex
  -E, --ext-headers           print extended header for every pck
  -Q, --superquiet            do not display user and password

LUA options:
      --lua-script <script1>,[<script2>,...]     comma-separted list of LUA scripts
      --lua-args n1=v1,[n2=v2,...]               comma-separated arguments to LUA script(s)

General options:
  -i, --iface <iface>         use this network interface
  -I, --liface                show all the network interfaces
  -Y, --secondary <ifaces>    list of secondary network interfaces
  -n, --netmask <netmask>     force this <netmask> on iface
  -A, --address <address>     force this local <address> on iface
  -P, --plugin <plugin>       launch this <plugin> - multiple occurance allowed
      --plugin-list <plugin1>,[<plugin2>,...]       comma-separated list of plugins
  -F, --filter <file>         load the filter <file> (content filter)
  -z, --silent                do not perform the initial ARP scan
  -6, --ip6scan               send ICMPv6 probes to discover IPv6 nodes on the link
  -j, --load-hosts <file>     load the hosts list from <file>
  -k, --save-hosts <file>     save the hosts list to <file>
  -W, --wifi-key <wkey>       use this key to decrypt wifi packets (wep or wpa)
  -a, --config <config>       use the alternative config file <config>

Standard options:
  -v, --version               prints the version and exit
  -h, --help                  this help screen


```

***

**ettercap-pkexec**

Graphical pkexec-based launcher for ettercap

***

**etterfilter**

Filter compiler for ettercap content filtering engine

```
:~# man etterfilter
ETTERFILTER(8)              System Manager's Manual             ETTERFILTER(8)

NAME
       etterfilter - Filter compiler for ettercap content filtering engine

SYNOPSIS
       etterfilter [OPTIONS] FILE

DESCRIPTION
       The etterfilter utility is used to compile source filter files into bi-
       nary filter files that can be interpreted by the JIT interpreter in the
       ettercap(8)  filter  engine. You have to compile your filter scripts in
       order to use them in ettercap. All syntax/parse errors will be  checked
       at compile time, so you will be sure to produce a correct binary filter
       for ettercap.

       GENERAL OPTIONS

       -o, --output <FILE>
              you can specify the output file for a source filter file. By de-
              fault the output is filter.ef.

       -t, --test <FILE>
              you  can analyze a compiled filter file with this option. etter-
              filter will print in a human readable form all the  instructions
              contained  in it. It is a sort of "disassembler" for binary fil-
              ter files.

       -d, --debug
              prints some debug messages during the compilation. Use  it  more
              than once to increase the debug level ( etterfilter -ddd ... ).

       -w, --suppress-warnings
              Don't  exit on warnings. With this option the compiler will com-
              pile the script even if it contains warnings.

       STANDARD OPTIONS

       -v, --version
              Print the version and exit.

       -h, --help
              prints the help screen with a short summary of the available op-
              tions.

       SCRIPTS SYNTAX
              A  script  is a compound of instructions. It is executed sequen-
              tially and you can make branches with the 'if' statements.  'if'
              and  'if/else'  statements  are the only supported. No loops are
              implemented. The syntax is almost like C code  except  that  you
              have  to put 'if' blocks into graph parentheses '{' '}', even if
              they contain only one instruction.

              NOTE: you have to put a space between the 'if' and the '('.  You
              must not put the space between the function name and the '('.

              Example:
              if (conditions) { }
              func(args...);

              The  conditions for an 'if' statement can be either functions or
              comparisons.  Two or more conditions can be linked together with
              logical operators like OR '||' and AND '&&'.

              Example:
              if (tcp.src == 21 && search(DATA.data, "ettercap")) {
              }

              Pay attention to the operator precedence.  You cannot use paren-
              theses to group conditions, so be careful with the order. An AND
              at  the  beginning  of  a  conditions block will exclude all the
              other tests if it is evaluated as false. The parsing is left-to-
              right, when an operator is found: if it is an AND and the previ-
              ous condition is false, all the statement is evaluated as false;
              if  it  is  an  OR  the parsing goes on even if the condition is
              false.

              Example:
              if (ip.proto == UDP || ip.proto == TCP && tcp.src == 80) {
              }

              if (ip.proto == TCP && tcp.src == 80 || ip.proto == UDP) {
              }

              the former condition will match all udp  or  http  traffic.  The
              latter  is  wrong,  because  if the packet is not tcp, the whole
              condition block will be evaluated as false.  If you want to make
              complex  conditions,  the  best way is to split them into nested
              'if' blocks.

              Since etterfilter support both IP address families,  you  should
              care  whether  you use 'ip.proto' which is specific for the IPv4
              address family or it's IPv6 couterpart 'ipv6.nh'. Especially for
              the  L4 protocol matching using 'ip.proto' and/or 'ipv6.nh', you
              should be careful if you're really acting on the right protocol.
              This  should  be  enforced  using  the  L3  protocol  identifier
              'eth.proto'.

              Example:
              if (eth.proto == IP && ip.proto ==  TCP  &&  tcp.dst  ==  80  ||
              tcp.src == 80) {
              }

              if  (eth.proto  ==  IP6  &&  ipv6.nh  == TCP && tcp.dst == 80 ||
              tcp.src == 80) {
              }

              if (tcp.dst == 80 || tcp.src == 80) {
              }

              The first example correctly matches http traffic  only  on  IPv4
              while  the  second  would  match  http traffic only on IPv6. The
              thrid example matches http regardless it's IP address familiy.

              Every instruction in a block must end with a semicolon ';'.

              Comparisons are implemented with the '==' operator  and  can  be
              used  to compare numbers, strings or ip addresses. An ip address
              MUST be enclosed within two single quotes (eg. '192.168.0.7'  or
              '2001:db8::2'). You can also use the 'less than' ('<'), 'greater
              than' ('>'), 'less or  equal'  ('<=')  and  'greater  or  equal'
              ('>=')  operators.  The lvalue of a comparison must be an offset
              (see later)

              Example:
              if (DATA.data + 20 == "ettercap" && ip.ttl > 16) {
              }

              Assignments are implemented with the '=' operator and the lvalue
              can be an offset (see later). The rvalue can be a string, an in-
              teger or a hexadecimal value.

              Example:
              ip.ttl = 0xff;
              DATA.data + 7 = "ettercap NG";

              You can also use the 'inc' and 'dec' operations  on  the  packet
              fields.  The operators used are '+=' and '-='. The rvalue can be
              an integer or a hexadecimal value.

              Example:
              ip.ttl += 5;

              More examples can be found in the etter.filter.examples file.

       OFFSET DEFINITION
              An offset is identified by a virtual pointer. In short words, an
              offset is a pointer to the packet buffer. The virtual pointer is
              a tuple <L, O, S>, where L is the iso/osi level, O is the offset
              in that level and S is the size of the virtual pointer.  You can
              make algebraic operations on a virtual pointer and the result is
              still  an  offset. Specifying 'vp + n' will result in a new vir-
              tual pointer <L, O+n, S>.  And this is perfectly legal, we  have
              changed the internal offset of that level.

              Virtual  pointers are in the form 'name.field.subfield'. For ex-
              ample 'ip.ttl' is the virtual pointer for the Time To Live field
              in  the  IP  header  of a packet. It will be translated as <L=3,
              O=9, S=1>. Indeed it is the 9th byte of level 3 and its size  is
              1  byte.  'ip.ttl  + 1' is the same as 'ip.proto' since the 10th
              byte of the IP header is the protocol  encapsulated  in  the  IP
              packet.  Note that since etterfilter also supports processing of
              IPv6, the above mentioned only applies for  IPv4  packets  while
              counterpart in IPv6 would be 'ipv6.nh'.

              The list of all supported virtual pointers is in the file etter-
              filter.tbl. You can add your own virtual pointers  by  adding  a
              new  table or modifying the existing ones. Refer to the comments
              at the beginning of the file for the syntax  of  etterfilter.tbl
              file.

       SCRIPTS FUNCTIONS

       search(where, what)
              this  function searches the string 'what' in the buffer 'where'.
              The buffer can be either DATA.data or DECODED.data.  The  former
              is  the payload at layer DATA (ontop TCP or UDP) as it is trans-
              mitted on the wire, the latter is the payload  decoded/decrypted
              by dissectors.
              So,  if you want to search in an SSH connection, it is better to
              use 'DECODED.data' since 'data' will be encrypted.
              The string 'what' can be binary. You have to escape it.

              example:
              search(DATA.data, "\x41\x42\x43")

       regex(where, regex)
              this function will return true if the 'regex'  has  matched  the
              buffer  'where'.   The  considerations  about 'DECODED.data' and
              'DATA.data' mentioned for the function 'search' are the same for
              the regex function.

              NOTE: regex can be used only against a string buffer.

              example:
              regex(DECODED.data, ".*login.*")

       pcre_regex(where, pcre_regex ... )
              this  function  will  evaluate a perl compatible regular expres-
              sion. You can match against both DATA and DECODED, but  if  your
              expression  modifies  the buffer, it makes sense to operate only
              on DATA. The function accepts 2 or 3 parameters depending on the
              operation you want. The two parameter form is used only to match
              a pattern. The three parameter form means that you want to  make
              a  substitution.  In  both  cases,  the  second parameter is the
              search string.
              You can use $n in the replacement string. These placeholders are
              referred  to  the  groups  created  in  the search string. (e.g.
              pcre_regex(DATA.data,    "^var1=([:digit:]*)&var2=([:digit:]*)",
              "var1=$2&var2=$1") will swap the value of var1 and var2).
              NOTE:  The  pcre support is optional in ettercap and will be en-
              abled only if you have the libpcre installed.  The compiler will
              warn  you  if you try to compile a filter that contains pcre ex-
              pressions but you don't have libpcre. Use the -w option to  sup-
              press the warning.

              example:
              pcre_regex(DATA.data, ".*foo$")
              pcre_regex(DATA.data, "([^ ]*) bar ([^ ]*)", "foo $1 $2")

       replace(what, with)
              this function replaces the string 'what' with the string 'with'.
              They can be binary string and must be escaped.  The  replacement
              is always performed in DATA.data since is the only payload which
              gets forwarded. The 'DECODED.data' buffer is  used  only  inter-
              nally and never reaches the wire.

              example:
              replace("ethercap", "ettercap")

       inject(what)
              this  function  injects the content of the file 'what' after the
              packet being processed. It always injects in DATA.data. You  can
              use  it  to  replace the entire packet with a fake one using the
              drop() function right before the inject() command.  In that case
              the filtering engine will drop the current packet and inject the
              fake one.

              example:
              inject("./fake_packet")

       log(what, where)
              this function dumps in the file 'where' the  buffer  'what'.  No
              information  is  stored  about  the  packet, only the payload is
              dumped. So you will see the stream in the file. If you  want  to
              log  packets in a more enhanced mode, you need to use the etter-
              cap -L option and analyze it with etterlog(8).
              The file 'where' must be writable to the user  EC_UID  (see  et-
              ter.conf(5)).

              example:
              log(DECODED.data, "/tmp/interesting.log")

       msg(message)
              this  function  displays  a message to the user in the User Mes-
              sages window. It is useful to let the user know whether  a  par-
              ticular filter has been successful or not.

              example:
              msg("Packet filtered successfully")

       drop() this  function marks the packet "to be dropped". The packet will
              not be forwarded to the real destination.

              example:
              drop()

       kill() this function kills the connection that owns the matched packet.
              If  it  is  a TCP connection, a RST is sent to both sides of the
              connection. If it is an UDP connection, an ICMP PORT UNREACHABLE
              is sent to the source of the packet.

              example:
              kill()

       exec(command)
              this  function executes a shell command. You have to provide the
              full path to the command since it is executed without any  envi-
              ronment.  There  is  no way to determine if the command was suc-
              cessful or not. Furthermore, it is executed asynchronously since
              it is forked by the main process.

              example:
              exec("/bin/cat /tmp/foo >> /tmp/bar")

       execinject(command)
              this  function  operates  similar  to the inject function except
              that it uses the output of a shell command to inject data rather
              than  the  contents  of a file.  It always injects in DATA.data.
              You can use it to replace the entire packet with a fake one  us-
              ing  the  drop() function right before the execinject() command.
              In that case the filtering engine will drop the  current  packet
              and inject the fake one.

              example:
              execinject("/bin/cat /tmp/foo")

       execreplace(command)
              this  function  operates  similar to the replace function except
              that it uses the output of a shell  command  to  replace  entire
              data  rather  than the contents of a file.  An other difference,
              is that orinal packet content is pass to the  shell  command  in
              stdin.   It  always  injects in DATA.data. You can use it to re-
              place the entire packet with a fake one depending on the  origi-
              nal one.

              example:
              execreplace("tr A-Z a-z")

       exit() this  function  causes  the  filter engine to stop executing the
              code. It is useful to stop the execution of the script  on  some
              circumstance checked by an 'if' statement.

              example:
              exit()

EXAMPLES
       Here are some examples of using etterfilter.

       etterfilter filter.ecf -o filter.ef

              Compiles the source filter.ecf into a binary filter.ef

ORIGINAL AUTHORS
       Alberto Ornaghi (ALoR) <>
       Marco Valleri (NaGA) <>

PROJECT STEWARDS
       Emilio Escobar (exfil)  <>
       Eric Milam (Brav0Hax)  <>

OFFICIAL DEVELOPERS
       Mike Ryan (justfalter)  <>
       Gianfranco Costamagna (LocutusOfBorg)  <>
       Antonio Collarino (sniper)  <>
       Ryan Linn   <>
       Jacob Baines   <>

CONTRIBUTORS
       Dhiru Kholia (kholia)  <>
       Alexander Koeppe (koeppea)  <>
       Martin Bos (PureHate)  <>
       Enrique Sanchez
       Gisle Vanem  <>
       Johannes Bauer  <>
       Daten (Bryan Schneiders)  <>

SEE ALSO
       etter.filter.examples
       ettercap(8) etterlog(8) etter.conf(5) ettercap_curses(8) ettercap_plug-
       ins(8) ettercap-pkexec(8)

ettercap 0.8.3.1                                                ETTERFILTER(8)
```

***

**etterlog**

Log analyzer for ettercap log files

```
:~# man etterlog
ETTERLOG(8)                 System Manager's Manual                ETTERLOG(8)

NAME
       etterlog - Log analyzer for ettercap log files

SYNOPSIS
       etterlog [OPTIONS] FILE

DESCRIPTION
       Etterlog  is  the log analyzer for logfiles created by ettercap. It can
       handle both compressed (created with  -Lc)  or  uncompressed  logfiles.
       With  this tool you can manipulate binary files as you like and you can
       print data in different ways all the times you want (in  contrast  with
       the  previous  logging system which was used to dump in a single static
       manner).
       You will be able to dump traffic  from  only  one  connection  of  your
       choice,  from  only one or more hosts, print data in hex, ascii, binary
       etc...

       TIP: All non-useful messages are printed to stderr, so you can save the
       output from etterlog with the following command:

       etterlog [options] logfile > outfile

              Thus  you can dump for example a binary file from an ftp connec-
              tion if you print the data in binary mode, without  headers  and
              selecting  only  the  ftp server as the source of the communica-
              tion.

       GENERAL OPTIONS

       -a, --analyze
              Analyze a log file and display some interesting statistics.

       -c, --connections
              Parse the log file and print a table of unique connections (port
              to  port).  This option can be used only on LOG_PACKET logfiles.
              On LOG_INFO logfiles it is useless.

              TIP: you can search for a particular host by using the following
              command:

              etterlog -c logfile.ecp | grep 10.0.0.1

       -f, --filter <TARGET>
              Print  only  packets  coming from or going to TARGET. The TARGET
              specification is the same as in ettercap.
              TARGET is in the form MAC/IPs/PORTs. With IPv6 support  enabled,
              TARGET  is  in the form MAC/IPs/IPv6/PORTs. Omitting one or more
              of its parts will be equivalent to set them to ANY. IPs and IPv6
              will be treated as one part so that it's only set to ANY if both
              IPs and IPv6 is omitted. This concludes in a result  most  users
              would expect.

              If  the log type is LOG_INFO the target is used to display hosts
              matching the mac, ip and having the specified port(s) open.  For
              example  the  target  //80  will  display only information about
              hosts with a running web server.

       -r, --reverse
              Reverse the matching in the TARGET selection. It means  not(TAR-
              GET). All but the selected TARGET.

       -t, --proto <PROTO>
              Sniff only PROTO packets (default is TCP + UDP).  This option is
              only useful in "simple" mode. If you start ettercap in  interac-
              tive mode both TCP and UDP are sniffed.
              PROTO can be "tcp", "udp" or "all" for both.

       -F, --filcon <CONNECTION>
              Print packets belonging only to this CONNECTION.
              CONNECTION is in the form PROTO:SOURCE:DEST. SOURCE and DEST are
              in the form IP:PORT.

              example:

              etterlog -F TCP:10.0.0.23:3318:198.182.196.56:80

       -s, --only-source
              Display only packets that are sent by the source of the selected
              CONNECTION.   This  option  makes sense only in conjunction with
              the -F option.

              TIP: if you want to save a file transferred in an  HTTP  or  FTP
              connection, you can use the following command:

              etterlog  -B -s -n -F TCP:10.0.0.1:20:10.0.0.2:35426 logfile.ecp
              > example.tar.gz

       -d, --only-dest
              Same as --only-source but it filters on the destination host.

       -n, --no-headers
              Do not print the header of each packet. This option is useful if
              you  want  to  save a file in binary format (-B option). Without
              the headers you can redirect the output to a file and  you  will
              get the original stream.

              NOTE:  the  time  stamp in the header is in the form: Thu Mar 27
              23:03:31 2003 [169396], the value in the square brackets is  ex-
              pressed in microseconds

       -m, --show-mac
              In  the headers show also the mac addresses corresponding to the
              ip addresses.

       -k, --color
              If used in conjunction with -F it displays the source  and  dest
              of  the  connection  using  different  colors.  If  used  with a
              LOG_INFO file it prints LAN hosts in green, REMOTE hosts in blue
              and GATEWAYS in red.

       -l, --only-local
              Used displaying an INFO file, it displays information only about
              local hosts.

       -L, --only-remote
              Used displaying an INFO file, it displays information only about
              remote hosts.

       SEARCH OPTIONS

       -e, --regex <REGEX>
              Display only packets matching the regex <REGEX>.
              If  this  option is used against a LOG_PACKET logfile, the regex
              is executed on the  payload  of  the  packet.  If  the  type  is
              LOG_INFO,  the  regex  is executed on all the fields of the host
              profile (OS, banners, service and ethernet adapter).
              NOTE: the regex is compiled with the REG_ICASE flag (case insen-
              sitive).

       -u, --user <USER>
              Display  information  about  this  user. The search is performed
              over all the user/pass couples collected across all hosts.

       -p, --passwords
              Print only the collected account information for each host. This
              prevents  the huge profile output. It can be used in conjunction
              with the -u option to filter the users. An asterisk '*' used  in
              front of an account represents a failed login attempt.

       -i, --show-client
              Show  the  client ip address when displaying the collected users
              and passwords. It may be useful when ACLs are in place.

       -I, --client <IP>
              Show passwords only coming from a specific <IP>. This is  useful
              to view all the usernames and passwords of a client.

       EDITING OPTIONS

       -C, --concat
              Use this option to concatenate two (or more) files into one sin-
              gle file. This is useful if  you  have  collected  ettercap  log
              files  from multiple sources and want to have an unified report.
              The output file must be specified with the -o option and the in-
              put files are listed as normal arguments.

              example:
              etterlog -C -o outfile input1 input2 input3

       -o, --outfile <FILE>
              specifies the output file for a concatenation.

       VISUALIZATION METHOD

       -B, --binary
              Print  data  as  they are, in binary form. Useful to dump binary
              data to a file (as described above).

       -X, --hex
              Print the packets in hex format.

              example:

              the string  "HTTP/1.1 304 Not Modified"  becomes:

              0000: 4854 5450 2f31 2e31 2033 3034 204e 6f74  HTTP/1.1 304 Not
              0010: 204d 6f64 6966 6965 64                    Modified

       -A, --ascii
              Print only "printable" characters, the others are  displayed  as
              dots '.'

       -T, --text
              Print only the "printable" characters and skip the others.

       -E, --ebcdic
              Convert an EBCDIC text to ASCII.

       -H, --html
              Strip all html tags from the text. A tag is every string between
              '<' and '>'.

              example:

              <title>This is the title</title>,  but  the  following  <string>
              will not be displayed.

              This is the title, but the following will not be displayed.

       -U, --utf8 <encoding>
              Print  the  packets  in  UTF-8  format. The <encoding> parameter
              specifies the encoding to be used while performing  the  conver-
              sion.  Use  the  `iconv  --list` command to obtain a list of all
              supported encodings.

       -Z, --zero
              Print always the void string. i.e. print only header information
              and no packet content will be printed.

       -x, --xml
              Print the host information in xml form, so you can parse it with
              your favourite program.

              The DTD associated with the xml output is in share/etterlog.dtd

       STANDARD OPTIONS

       -v, --version
              Print the version and exit.

       -h, --help
              Print the help screen with a short summary of the available  op-
              tions.

EXAMPLES
       Here are some examples of using etterlog.

       etterlog -k -l dump.eci

              Displays information about local hosts in different colors.

       etterlog -X dump.ecp

              Prints packets in HEX mode with full headers.

       etterlog -c dump.ecp

              Displays the list of connections logged in the file.

       etterlog -Akn -F TCP:10.0.0.1:13423:213.203.143.52:6666 dump.ecp

              Displays the IRC traffic made by 10.0.0.1 in ASCII mode, without
              headers information and in colored mode.

       etterlog -H -t tcp -f //80 dump.ecp

              Dumps all HTTP traffic and strips html tags.

       etterlog -Z -r -f /10.0.0.2/22 dump.ecp

              Displays only the headers of all connections except ssh on  host
              10.0.0.2

       etterlog -A -e 'user' -f //110 dump.ecp

              Displays only POP packets containing the 'user' regexp (case in-
              sensitive).

       etterlog -u root dump.eci

              Displays information about all the accounts of the user 'root'.

       etterlog -e Apache dump.eci

              Displays information about all the hosts running 'Apache'.

       etterlog -e Linux dump.eci

              Displays information about all the hosts with the 'Linux'  oper-
              ating system.

       etterlog -t tcp -f //110 dump.eci

              Displays  information  about all the hosts with the tcp port 110
              open.

       etterlog -t udp dump.eci

              Displays information about all the hosts with at least  one  UDP
              port open.

       etterlog -B -s -n -F TCP:10.0.0.1:20:10.0.0.2:35426 logfile.ecp > exam-
       ple.tar.gz

              Dumps in binary form the data sent by  10.0.0.1  over  the  data
              port  of  FTP.  Since  the headers are omitted, you will get the
              file as it was.

ORIGINAL AUTHORS
       Alberto Ornaghi (ALoR) <>
       Marco Valleri (NaGA) <>

PROJECT STEWARDS
       Emilio Escobar (exfil)  <>
       Eric Milam (Brav0Hax)  <>

OFFICIAL DEVELOPERS
       Mike Ryan (justfalter)  <>
       Gianfranco Costamagna (LocutusOfBorg)  <>
       Antonio Collarino (sniper)  <>
       Ryan Linn   <>
       Jacob Baines   <>

CONTRIBUTORS
       Dhiru Kholia (kholia)  <>
       Alexander Koeppe (koeppea)  <>
       Martin Bos (PureHate)  <>
       Enrique Sanchez
       Gisle Vanem  <>
       Johannes Bauer  <>
       Daten (Bryan Schneiders)  <>

SEE ALSO
       ettercap(8)  etterfilter(8)  etter.conf(5)  ettercap_curses(8)   etter-
       cap_plugins(8) ettercap-pkexec(8)

ettercap 0.8.3.1                                                   ETTERLOG(8)
```

***

#### ettercap-text-only <a href="#ettercap-text-only" id="ettercap-text-only"></a>

Ettercap supports active and passive dissection of many protocols (even encrypted ones) and includes many feature for network and host analysis.

Data injection in an established connection and filtering (substitute or drop a packet) on the fly is also possible, keeping the connection synchronized.

Many sniffing modes are implemented, for a powerful and complete sniffing suite. It is possible to sniff in four modes: IP Based, MAC Based, ARP Based (full-duplex) and PublicARP Based (half-duplex).

Ettercap also has the ability to detect a switched LAN, and to use OS fingerprints (active or passive) to find the geometry of the LAN.

This package contains the ettercap text-mode-only executable.

**Installed size:** `304 KB`\
**How to install:** `sudo apt install ettercap-text-only`

<details>

<summary>Dependencies:</summary>

* ettercap-common
* libbsd0
* libc6
* libncurses6
* libpcre2-8-0
* libtinfo6
* zlib1g

</details>

**ettercap**

Multipurpose sniffer/content filter for man in the middle attacks

```
:~# ettercap -h

ettercap 0.8.3.1 copyright 2001-2020 Ettercap Development Team


Usage: ettercap [OPTIONS] [TARGET1] [TARGET2]

TARGET is in the format MAC/IP/IPv6/PORTs (see the man for further detail)

Sniffing and Attack options:
  -M, --mitm <METHOD:ARGS>    perform a mitm attack
  -o, --only-mitm             don't sniff, only perform the mitm attack
  -b, --broadcast             sniff packets destined to broadcast
  -B, --bridge <IFACE>        use bridged sniff (needs 2 ifaces)
  -p, --nopromisc             do not put the iface in promisc mode
  -S, --nosslmitm             do not forge SSL certificates
  -u, --unoffensive           do not forward packets
  -r, --read <file>           read data from pcapfile <file>
  -f, --pcapfilter <string>   set the pcap filter <string>
  -R, --reversed              use reversed TARGET matching
  -t, --proto <proto>         sniff only this proto (default is all)
      --certificate <file>    certificate file to use for SSL MiTM
      --private-key <file>    private key file to use for SSL MiTM

User Interface Type:
  -T, --text                  use text only GUI
       -q, --quiet                 do not display packet contents
       -s, --script <CMD>          issue these commands to the GUI
  -C, --curses                use curses GUI
  -D, --daemon                daemonize ettercap (no GUI)
  -G, --gtk                   use GTK+ GUI

Logging options:
  -w, --write <file>          write sniffed data to pcapfile <file>
  -L, --log <logfile>         log all the traffic to this <logfile>
  -l, --log-info <logfile>    log only passive infos to this <logfile>
  -m, --log-msg <logfile>     log all the messages to this <logfile>
  -c, --compress              use gzip compression on log files

Visualization options:
  -d, --dns                   resolves ip addresses into hostnames
  -V, --visual <format>       set the visualization format
  -e, --regex <regex>         visualize only packets matching this regex
  -E, --ext-headers           print extended header for every pck
  -Q, --superquiet            do not display user and password

LUA options:
      --lua-script <script1>,[<script2>,...]     comma-separted list of LUA scripts
      --lua-args n1=v1,[n2=v2,...]               comma-separated arguments to LUA script(s)

General options:
  -i, --iface <iface>         use this network interface
  -I, --liface                show all the network interfaces
  -Y, --secondary <ifaces>    list of secondary network interfaces
  -n, --netmask <netmask>     force this <netmask> on iface
  -A, --address <address>     force this local <address> on iface
  -P, --plugin <plugin>       launch this <plugin> - multiple occurance allowed
      --plugin-list <plugin1>,[<plugin2>,...]       comma-separated list of plugins
  -F, --filter <file>         load the filter <file> (content filter)
  -z, --silent                do not perform the initial ARP scan
  -6, --ip6scan               send ICMPv6 probes to discover IPv6 nodes on the link
  -j, --load-hosts <file>     load the hosts list from <file>
  -k, --save-hosts <file>     save the hosts list to <file>
  -W, --wifi-key <wkey>       use this key to decrypt wifi packets (wep or wpa)
  -a, --config <config>       use the alternative config file <config>

Standard options:
  -v, --version               prints the version and exit
  -h, --help                  this help screen


```

***

**etterfilter**

Filter compiler for ettercap content filtering engine

```
:~# man etterfilter
ETTERFILTER(8)              System Manager's Manual             ETTERFILTER(8)

NAME
       etterfilter - Filter compiler for ettercap content filtering engine

SYNOPSIS
       etterfilter [OPTIONS] FILE

DESCRIPTION
       The etterfilter utility is used to compile source filter files into bi-
       nary filter files that can be interpreted by the JIT interpreter in the
       ettercap(8)  filter  engine. You have to compile your filter scripts in
       order to use them in ettercap. All syntax/parse errors will be  checked
       at compile time, so you will be sure to produce a correct binary filter
       for ettercap.

       GENERAL OPTIONS

       -o, --output <FILE>
              you can specify the output file for a source filter file. By de-
              fault the output is filter.ef.

       -t, --test <FILE>
              you  can analyze a compiled filter file with this option. etter-
              filter will print in a human readable form all the  instructions
              contained  in it. It is a sort of "disassembler" for binary fil-
              ter files.

       -d, --debug
              prints some debug messages during the compilation. Use  it  more
              than once to increase the debug level ( etterfilter -ddd ... ).

       -w, --suppress-warnings
              Don't  exit on warnings. With this option the compiler will com-
              pile the script even if it contains warnings.

       STANDARD OPTIONS

       -v, --version
              Print the version and exit.

       -h, --help
              prints the help screen with a short summary of the available op-
              tions.

       SCRIPTS SYNTAX
              A  script  is a compound of instructions. It is executed sequen-
              tially and you can make branches with the 'if' statements.  'if'
              and  'if/else'  statements  are the only supported. No loops are
              implemented. The syntax is almost like C code  except  that  you
              have  to put 'if' blocks into graph parentheses '{' '}', even if
              they contain only one instruction.

              NOTE: you have to put a space between the 'if' and the '('.  You
              must not put the space between the function name and the '('.

              Example:
              if (conditions) { }
              func(args...);

              The  conditions for an 'if' statement can be either functions or
              comparisons.  Two or more conditions can be linked together with
              logical operators like OR '||' and AND '&&'.

              Example:
              if (tcp.src == 21 && search(DATA.data, "ettercap")) {
              }

              Pay attention to the operator precedence.  You cannot use paren-
              theses to group conditions, so be careful with the order. An AND
              at  the  beginning  of  a  conditions block will exclude all the
              other tests if it is evaluated as false. The parsing is left-to-
              right, when an operator is found: if it is an AND and the previ-
              ous condition is false, all the statement is evaluated as false;
              if  it  is  an  OR  the parsing goes on even if the condition is
              false.

              Example:
              if (ip.proto == UDP || ip.proto == TCP && tcp.src == 80) {
              }

              if (ip.proto == TCP && tcp.src == 80 || ip.proto == UDP) {
              }

              the former condition will match all udp  or  http  traffic.  The
              latter  is  wrong,  because  if the packet is not tcp, the whole
              condition block will be evaluated as false.  If you want to make
              complex  conditions,  the  best way is to split them into nested
              'if' blocks.

              Since etterfilter support both IP address families,  you  should
              care  whether  you use 'ip.proto' which is specific for the IPv4
              address family or it's IPv6 couterpart 'ipv6.nh'. Especially for
              the  L4 protocol matching using 'ip.proto' and/or 'ipv6.nh', you
              should be careful if you're really acting on the right protocol.
              This  should  be  enforced  using  the  L3  protocol  identifier
              'eth.proto'.

              Example:
              if (eth.proto == IP && ip.proto ==  TCP  &&  tcp.dst  ==  80  ||
              tcp.src == 80) {
              }

              if  (eth.proto  ==  IP6  &&  ipv6.nh  == TCP && tcp.dst == 80 ||
              tcp.src == 80) {
              }

              if (tcp.dst == 80 || tcp.src == 80) {
              }

              The first example correctly matches http traffic  only  on  IPv4
              while  the  second  would  match  http traffic only on IPv6. The
              thrid example matches http regardless it's IP address familiy.

              Every instruction in a block must end with a semicolon ';'.

              Comparisons are implemented with the '==' operator  and  can  be
              used  to compare numbers, strings or ip addresses. An ip address
              MUST be enclosed within two single quotes (eg. '192.168.0.7'  or
              '2001:db8::2'). You can also use the 'less than' ('<'), 'greater
              than' ('>'), 'less or  equal'  ('<=')  and  'greater  or  equal'
              ('>=')  operators.  The lvalue of a comparison must be an offset
              (see later)

              Example:
              if (DATA.data + 20 == "ettercap" && ip.ttl > 16) {
              }

              Assignments are implemented with the '=' operator and the lvalue
              can be an offset (see later). The rvalue can be a string, an in-
              teger or a hexadecimal value.

              Example:
              ip.ttl = 0xff;
              DATA.data + 7 = "ettercap NG";

              You can also use the 'inc' and 'dec' operations  on  the  packet
              fields.  The operators used are '+=' and '-='. The rvalue can be
              an integer or a hexadecimal value.

              Example:
              ip.ttl += 5;

              More examples can be found in the etter.filter.examples file.

       OFFSET DEFINITION
              An offset is identified by a virtual pointer. In short words, an
              offset is a pointer to the packet buffer. The virtual pointer is
              a tuple <L, O, S>, where L is the iso/osi level, O is the offset
              in that level and S is the size of the virtual pointer.  You can
              make algebraic operations on a virtual pointer and the result is
              still  an  offset. Specifying 'vp + n' will result in a new vir-
              tual pointer <L, O+n, S>.  And this is perfectly legal, we  have
              changed the internal offset of that level.

              Virtual  pointers are in the form 'name.field.subfield'. For ex-
              ample 'ip.ttl' is the virtual pointer for the Time To Live field
              in  the  IP  header  of a packet. It will be translated as <L=3,
              O=9, S=1>. Indeed it is the 9th byte of level 3 and its size  is
              1  byte.  'ip.ttl  + 1' is the same as 'ip.proto' since the 10th
              byte of the IP header is the protocol  encapsulated  in  the  IP
              packet.  Note that since etterfilter also supports processing of
              IPv6, the above mentioned only applies for  IPv4  packets  while
              counterpart in IPv6 would be 'ipv6.nh'.

              The list of all supported virtual pointers is in the file etter-
              filter.tbl. You can add your own virtual pointers  by  adding  a
              new  table or modifying the existing ones. Refer to the comments
              at the beginning of the file for the syntax  of  etterfilter.tbl
              file.

       SCRIPTS FUNCTIONS

       search(where, what)
              this  function searches the string 'what' in the buffer 'where'.
              The buffer can be either DATA.data or DECODED.data.  The  former
              is  the payload at layer DATA (ontop TCP or UDP) as it is trans-
              mitted on the wire, the latter is the payload  decoded/decrypted
              by dissectors.
              So,  if you want to search in an SSH connection, it is better to
              use 'DECODED.data' since 'data' will be encrypted.
              The string 'what' can be binary. You have to escape it.

              example:
              search(DATA.data, "\x41\x42\x43")

       regex(where, regex)
              this function will return true if the 'regex'  has  matched  the
              buffer  'where'.   The  considerations  about 'DECODED.data' and
              'DATA.data' mentioned for the function 'search' are the same for
              the regex function.

              NOTE: regex can be used only against a string buffer.

              example:
              regex(DECODED.data, ".*login.*")

       pcre_regex(where, pcre_regex ... )
              this  function  will  evaluate a perl compatible regular expres-
              sion. You can match against both DATA and DECODED, but  if  your
              expression  modifies  the buffer, it makes sense to operate only
              on DATA. The function accepts 2 or 3 parameters depending on the
              operation you want. The two parameter form is used only to match
              a pattern. The three parameter form means that you want to  make
              a  substitution.  In  both  cases,  the  second parameter is the
              search string.
              You can use $n in the replacement string. These placeholders are
              referred  to  the  groups  created  in  the search string. (e.g.
              pcre_regex(DATA.data,    "^var1=([:digit:]*)&var2=([:digit:]*)",
              "var1=$2&var2=$1") will swap the value of var1 and var2).
              NOTE:  The  pcre support is optional in ettercap and will be en-
              abled only if you have the libpcre installed.  The compiler will
              warn  you  if you try to compile a filter that contains pcre ex-
              pressions but you don't have libpcre. Use the -w option to  sup-
              press the warning.

              example:
              pcre_regex(DATA.data, ".*foo$")
              pcre_regex(DATA.data, "([^ ]*) bar ([^ ]*)", "foo $1 $2")

       replace(what, with)
              this function replaces the string 'what' with the string 'with'.
              They can be binary string and must be escaped.  The  replacement
              is always performed in DATA.data since is the only payload which
              gets forwarded. The 'DECODED.data' buffer is  used  only  inter-
              nally and never reaches the wire.

              example:
              replace("ethercap", "ettercap")

       inject(what)
              this  function  injects the content of the file 'what' after the
              packet being processed. It always injects in DATA.data. You  can
              use  it  to  replace the entire packet with a fake one using the
              drop() function right before the inject() command.  In that case
              the filtering engine will drop the current packet and inject the
              fake one.

              example:
              inject("./fake_packet")

       log(what, where)
              this function dumps in the file 'where' the  buffer  'what'.  No
              information  is  stored  about  the  packet, only the payload is
              dumped. So you will see the stream in the file. If you  want  to
              log  packets in a more enhanced mode, you need to use the etter-
              cap -L option and analyze it with etterlog(8).
              The file 'where' must be writable to the user  EC_UID  (see  et-
              ter.conf(5)).

              example:
              log(DECODED.data, "/tmp/interesting.log")

       msg(message)
              this  function  displays  a message to the user in the User Mes-
              sages window. It is useful to let the user know whether  a  par-
              ticular filter has been successful or not.

              example:
              msg("Packet filtered successfully")

       drop() this  function marks the packet "to be dropped". The packet will
              not be forwarded to the real destination.

              example:
              drop()

       kill() this function kills the connection that owns the matched packet.
              If  it  is  a TCP connection, a RST is sent to both sides of the
              connection. If it is an UDP connection, an ICMP PORT UNREACHABLE
              is sent to the source of the packet.

              example:
              kill()

       exec(command)
              this  function executes a shell command. You have to provide the
              full path to the command since it is executed without any  envi-
              ronment.  There  is  no way to determine if the command was suc-
              cessful or not. Furthermore, it is executed asynchronously since
              it is forked by the main process.

              example:
              exec("/bin/cat /tmp/foo >> /tmp/bar")

       execinject(command)
              this  function  operates  similar  to the inject function except
              that it uses the output of a shell command to inject data rather
              than  the  contents  of a file.  It always injects in DATA.data.
              You can use it to replace the entire packet with a fake one  us-
              ing  the  drop() function right before the execinject() command.
              In that case the filtering engine will drop the  current  packet
              and inject the fake one.

              example:
              execinject("/bin/cat /tmp/foo")

       execreplace(command)
              this  function  operates  similar to the replace function except
              that it uses the output of a shell  command  to  replace  entire
              data  rather  than the contents of a file.  An other difference,
              is that orinal packet content is pass to the  shell  command  in
              stdin.   It  always  injects in DATA.data. You can use it to re-
              place the entire packet with a fake one depending on the  origi-
              nal one.

              example:
              execreplace("tr A-Z a-z")

       exit() this  function  causes  the  filter engine to stop executing the
              code. It is useful to stop the execution of the script  on  some
              circumstance checked by an 'if' statement.

              example:
              exit()

EXAMPLES
       Here are some examples of using etterfilter.

       etterfilter filter.ecf -o filter.ef

              Compiles the source filter.ecf into a binary filter.ef

ORIGINAL AUTHORS
       Alberto Ornaghi (ALoR) <>
       Marco Valleri (NaGA) <>

PROJECT STEWARDS
       Emilio Escobar (exfil)  <>
       Eric Milam (Brav0Hax)  <>

OFFICIAL DEVELOPERS
       Mike Ryan (justfalter)  <>
       Gianfranco Costamagna (LocutusOfBorg)  <>
       Antonio Collarino (sniper)  <>
       Ryan Linn   <>
       Jacob Baines   <>

CONTRIBUTORS
       Dhiru Kholia (kholia)  <>
       Alexander Koeppe (koeppea)  <>
       Martin Bos (PureHate)  <>
       Enrique Sanchez
       Gisle Vanem  <>
       Johannes Bauer  <>
       Daten (Bryan Schneiders)  <>

SEE ALSO
       etter.filter.examples
       ettercap(8) etterlog(8) etter.conf(5) ettercap_curses(8) ettercap_plug-
       ins(8) ettercap-pkexec(8)

ettercap 0.8.3.1                                                ETTERFILTER(8)
```

***

**etterlog**

Log analyzer for ettercap log files

```
:~# man etterlog
ETTERLOG(8)                 System Manager's Manual                ETTERLOG(8)

NAME
       etterlog - Log analyzer for ettercap log files

SYNOPSIS
       etterlog [OPTIONS] FILE

DESCRIPTION
       Etterlog  is  the log analyzer for logfiles created by ettercap. It can
       handle both compressed (created with  -Lc)  or  uncompressed  logfiles.
       With  this tool you can manipulate binary files as you like and you can
       print data in different ways all the times you want (in  contrast  with
       the  previous  logging system which was used to dump in a single static
       manner).
       You will be able to dump traffic  from  only  one  connection  of  your
       choice,  from  only one or more hosts, print data in hex, ascii, binary
       etc...

       TIP: All non-useful messages are printed to stderr, so you can save the
       output from etterlog with the following command:

       etterlog [options] logfile > outfile

              Thus  you can dump for example a binary file from an ftp connec-
              tion if you print the data in binary mode, without  headers  and
              selecting  only  the  ftp server as the source of the communica-
              tion.

       GENERAL OPTIONS

       -a, --analyze
              Analyze a log file and display some interesting statistics.

       -c, --connections
              Parse the log file and print a table of unique connections (port
              to  port).  This option can be used only on LOG_PACKET logfiles.
              On LOG_INFO logfiles it is useless.

              TIP: you can search for a particular host by using the following
              command:

              etterlog -c logfile.ecp | grep 10.0.0.1

       -f, --filter <TARGET>
              Print  only  packets  coming from or going to TARGET. The TARGET
              specification is the same as in ettercap.
              TARGET is in the form MAC/IPs/PORTs. With IPv6 support  enabled,
              TARGET  is  in the form MAC/IPs/IPv6/PORTs. Omitting one or more
              of its parts will be equivalent to set them to ANY. IPs and IPv6
              will be treated as one part so that it's only set to ANY if both
              IPs and IPv6 is omitted. This concludes in a result  most  users
              would expect.

              If  the log type is LOG_INFO the target is used to display hosts
              matching the mac, ip and having the specified port(s) open.  For
              example  the  target  //80  will  display only information about
              hosts with a running web server.

       -r, --reverse
              Reverse the matching in the TARGET selection. It means  not(TAR-
              GET). All but the selected TARGET.

       -t, --proto <PROTO>
              Sniff only PROTO packets (default is TCP + UDP).  This option is
              only useful in "simple" mode. If you start ettercap in  interac-
              tive mode both TCP and UDP are sniffed.
              PROTO can be "tcp", "udp" or "all" for both.

       -F, --filcon <CONNECTION>
              Print packets belonging only to this CONNECTION.
              CONNECTION is in the form PROTO:SOURCE:DEST. SOURCE and DEST are
              in the form IP:PORT.

              example:

              etterlog -F TCP:10.0.0.23:3318:198.182.196.56:80

       -s, --only-source
              Display only packets that are sent by the source of the selected
              CONNECTION.   This  option  makes sense only in conjunction with
              the -F option.

              TIP: if you want to save a file transferred in an  HTTP  or  FTP
              connection, you can use the following command:

              etterlog  -B -s -n -F TCP:10.0.0.1:20:10.0.0.2:35426 logfile.ecp
              > example.tar.gz

       -d, --only-dest
              Same as --only-source but it filters on the destination host.

       -n, --no-headers
              Do not print the header of each packet. This option is useful if
              you  want  to  save a file in binary format (-B option). Without
              the headers you can redirect the output to a file and  you  will
              get the original stream.

              NOTE:  the  time  stamp in the header is in the form: Thu Mar 27
              23:03:31 2003 [169396], the value in the square brackets is  ex-
              pressed in microseconds

       -m, --show-mac
              In  the headers show also the mac addresses corresponding to the
              ip addresses.

       -k, --color
              If used in conjunction with -F it displays the source  and  dest
              of  the  connection  using  different  colors.  If  used  with a
              LOG_INFO file it prints LAN hosts in green, REMOTE hosts in blue
              and GATEWAYS in red.

       -l, --only-local
              Used displaying an INFO file, it displays information only about
              local hosts.

       -L, --only-remote
              Used displaying an INFO file, it displays information only about
              remote hosts.

       SEARCH OPTIONS

       -e, --regex <REGEX>
              Display only packets matching the regex <REGEX>.
              If  this  option is used against a LOG_PACKET logfile, the regex
              is executed on the  payload  of  the  packet.  If  the  type  is
              LOG_INFO,  the  regex  is executed on all the fields of the host
              profile (OS, banners, service and ethernet adapter).
              NOTE: the regex is compiled with the REG_ICASE flag (case insen-
              sitive).

       -u, --user <USER>
              Display  information  about  this  user. The search is performed
              over all the user/pass couples collected across all hosts.

       -p, --passwords
              Print only the collected account information for each host. This
              prevents  the huge profile output. It can be used in conjunction
              with the -u option to filter the users. An asterisk '*' used  in
              front of an account represents a failed login attempt.

       -i, --show-client
              Show  the  client ip address when displaying the collected users
              and passwords. It may be useful when ACLs are in place.

       -I, --client <IP>
              Show passwords only coming from a specific <IP>. This is  useful
              to view all the usernames and passwords of a client.

       EDITING OPTIONS

       -C, --concat
              Use this option to concatenate two (or more) files into one sin-
              gle file. This is useful if  you  have  collected  ettercap  log
              files  from multiple sources and want to have an unified report.
              The output file must be specified with the -o option and the in-
              put files are listed as normal arguments.

              example:
              etterlog -C -o outfile input1 input2 input3

       -o, --outfile <FILE>
              specifies the output file for a concatenation.

       VISUALIZATION METHOD

       -B, --binary
              Print  data  as  they are, in binary form. Useful to dump binary
              data to a file (as described above).

       -X, --hex
              Print the packets in hex format.

              example:

              the string  "HTTP/1.1 304 Not Modified"  becomes:

              0000: 4854 5450 2f31 2e31 2033 3034 204e 6f74  HTTP/1.1 304 Not
              0010: 204d 6f64 6966 6965 64                    Modified

       -A, --ascii
              Print only "printable" characters, the others are  displayed  as
              dots '.'

       -T, --text
              Print only the "printable" characters and skip the others.

       -E, --ebcdic
              Convert an EBCDIC text to ASCII.

       -H, --html
              Strip all html tags from the text. A tag is every string between
              '<' and '>'.

              example:

              <title>This is the title</title>,  but  the  following  <string>
              will not be displayed.

              This is the title, but the following will not be displayed.

       -U, --utf8 <encoding>
              Print  the  packets  in  UTF-8  format. The <encoding> parameter
              specifies the encoding to be used while performing  the  conver-
              sion.  Use  the  `iconv  --list` command to obtain a list of all
              supported encodings.

       -Z, --zero
              Print always the void string. i.e. print only header information
              and no packet content will be printed.

       -x, --xml
              Print the host information in xml form, so you can parse it with
              your favourite program.

              The DTD associated with the xml output is in share/etterlog.dtd

       STANDARD OPTIONS

       -v, --version
              Print the version and exit.

       -h, --help
              Print the help screen with a short summary of the available  op-
              tions.

EXAMPLES
       Here are some examples of using etterlog.

       etterlog -k -l dump.eci

              Displays information about local hosts in different colors.

       etterlog -X dump.ecp

              Prints packets in HEX mode with full headers.

       etterlog -c dump.ecp

              Displays the list of connections logged in the file.

       etterlog -Akn -F TCP:10.0.0.1:13423:213.203.143.52:6666 dump.ecp

              Displays the IRC traffic made by 10.0.0.1 in ASCII mode, without
              headers information and in colored mode.

       etterlog -H -t tcp -f //80 dump.ecp

              Dumps all HTTP traffic and strips html tags.

       etterlog -Z -r -f /10.0.0.2/22 dump.ecp

              Displays only the headers of all connections except ssh on  host
              10.0.0.2

       etterlog -A -e 'user' -f //110 dump.ecp

              Displays only POP packets containing the 'user' regexp (case in-
              sensitive).

       etterlog -u root dump.eci

              Displays information about all the accounts of the user 'root'.

       etterlog -e Apache dump.eci

              Displays information about all the hosts running 'Apache'.

       etterlog -e Linux dump.eci

              Displays information about all the hosts with the 'Linux'  oper-
              ating system.

       etterlog -t tcp -f //110 dump.eci

              Displays  information  about all the hosts with the tcp port 110
              open.

       etterlog -t udp dump.eci

              Displays information about all the hosts with at least  one  UDP
              port open.

       etterlog -B -s -n -F TCP:10.0.0.1:20:10.0.0.2:35426 logfile.ecp > exam-
       ple.tar.gz

              Dumps in binary form the data sent by  10.0.0.1  over  the  data
              port  of  FTP.  Since  the headers are omitted, you will get the
              file as it was.

ORIGINAL AUTHORS
       Alberto Ornaghi (ALoR) <>
       Marco Valleri (NaGA) <>

PROJECT STEWARDS
       Emilio Escobar (exfil)  <>
       Eric Milam (Brav0Hax)  <>

OFFICIAL DEVELOPERS
       Mike Ryan (justfalter)  <>
       Gianfranco Costamagna (LocutusOfBorg)  <>
       Antonio Collarino (sniper)  <>
       Ryan Linn   <>
       Jacob Baines   <>

CONTRIBUTORS
       Dhiru Kholia (kholia)  <>
       Alexander Koeppe (koeppea)  <>
       Martin Bos (PureHate)  <>
       Enrique Sanchez
       Gisle Vanem  <>
       Johannes Bauer  <>
       Daten (Bryan Schneiders)  <>

SEE ALSO
       ettercap(8)  etterfilter(8)  etter.conf(5)  ettercap_curses(8)   etter-
       cap_plugins(8) ettercap-pkexec(8)

ettercap 0.8.3.1                                                   ETTERLOG(8)
```

***

Updated on: 2023-Mar-08\


***
