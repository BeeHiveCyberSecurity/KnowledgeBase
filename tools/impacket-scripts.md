---
description: >-
  Impacket is a Python library for working with network protocols and packets.
  It provides a set of Python classes for crafting and decoding network packets
  and provides access to a variety of protocols
---

# 🌐 impacket-scripts

### Packages and Binaries:

#### impacket-scripts <a href="#impacket-scripts" id="impacket-scripts"></a>

This package contains links to useful impacket scripts. It’s a separate package to keep impacket package from Debian and have the useful scripts in the path for Kali.

**Installed size:** `60 KB`\
**How to install:** `sudo apt install impacket-scripts`

<details>

<summary>Dependencies:</summary>

* python3-dsinternals
* python3-impacket
* python3-ldap3
* python3-ldapdomaindump
* python3-pcapy

</details>

**impacket-Get-GPPPassword**

```
:~# impacket-Get-GPPPassword -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: Get-GPPPassword.py [-h] [-xmlfile XMLFILE] [-share SHARE]
                          [-base-dir BASE_DIR] [-ts] [-debug]
                          [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                          [-aesKey hex key] [-dc-ip ip address]
                          [-target-ip ip address] [-port [destination port]]
                          target

Group Policy Preferences passwords finder and decryptor

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>
                        or LOCAL (if you want to parse local files)

options:
  -h, --help            show this help message and exit
  -xmlfile XMLFILE      Group Policy Preferences XML files to parse
  -share SHARE          SMB Share
  -base-dir BASE_DIR    Directory to search in (Default: /)
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)

connection:
  -dc-ip ip address     IP Address of the domain controller. If omitted it
                        will use the domain part (FQDN) specified in the
                        target parameter
  -target-ip ip address
                        IP Address of the target machine. If omitted it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server
```

***

**impacket-GetADUsers**

```
:~# impacket-GetADUsers -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: GetADUsers.py [-h] [-user username] [-all] [-ts] [-debug]
                     [-hashes LMHASH:NTHASH] [-no-pass] [-k] [-aesKey hex key]
                     [-dc-ip ip address]
                     target

Queries target domain for users data

positional arguments:
  target                domain/username[:password]

options:
  -h, --help            show this help message and exit
  -user username        Requests data for specific user
  -all                  Return all users, including those with no email
                        addresses and disabled accounts. When used with -user
                        it will return user's info even if the account is
                        disabled
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
```

***

**impacket-GetNPUsers**

```
:~# impacket-GetNPUsers -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: GetNPUsers.py [-h] [-request] [-outputfile OUTPUTFILE]
                     [-format {hashcat,john}] [-usersfile USERSFILE] [-ts]
                     [-debug] [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                     [-aesKey hex key] [-dc-ip ip address]
                     target

Queries target domain for users with 'Do not require Kerberos
preauthentication' set and export their TGTs for cracking

positional arguments:
  target                domain/username[:password]

options:
  -h, --help            show this help message and exit
  -request              Requests TGT for users and output them in JtR/hashcat
                        format (default False)
  -outputfile OUTPUTFILE
                        Output filename to write ciphers in JtR/hashcat format
  -format {hashcat,john}
                        format to save the AS_REQ of users without pre-
                        authentication. Default is hashcat
  -usersfile USERSFILE  File with user per line to test
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
```

***

**impacket-GetUserSPNs**

```
:~# impacket-GetUserSPNs -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: GetUserSPNs.py [-h] [-target-domain TARGET_DOMAIN]
                      [-usersfile USERSFILE] [-request]
                      [-request-user username] [-save]
                      [-outputfile OUTPUTFILE] [-debug]
                      [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                      [-aesKey hex key] [-dc-ip ip address]
                      target

Queries target domain for SPNs that are running under a user account

positional arguments:
  target                domain/username[:password]

options:
  -h, --help            show this help message and exit
  -target-domain TARGET_DOMAIN
                        Domain to query/request if different than the domain
                        of the user. Allows for Kerberoasting across trusts.
  -usersfile USERSFILE  File with user per line to test
  -request              Requests TGS for users and output them in JtR/hashcat
                        format (default False)
  -request-user username
                        Requests TGS for the SPN associated to the user
                        specified (just the username, no domain needed)
  -save                 Saves TGS requested to disk. Format is
                        <username>.ccache. Auto selects -request
  -outputfile OUTPUTFILE
                        Output filename to write ciphers in JtR/hashcat format
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter. Ignoredif -target-domain is specified.
```

***

**impacket-addcomputer**

```
:~# impacket-addcomputer -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: addcomputer.py [-h] [-domain-netbios NETBIOSNAME]
                      [-computer-name COMPUTER-NAME$]
                      [-computer-pass password] [-no-add] [-delete] [-debug]
                      [-method {SAMR,LDAPS}] [-port {139,445,636}]
                      [-baseDN DC=test,DC=local]
                      [-computer-group CN=Computers,DC=test,DC=local]
                      [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                      [-aesKey hex key] [-dc-host hostname] [-dc-ip ip]
                      [domain/]username[:password]

Adds a computer account to domain

positional arguments:
  [domain/]username[:password]
                        Account used to authenticate to DC.

options:
  -h, --help            show this help message and exit
  -domain-netbios NETBIOSNAME
                        Domain NetBIOS name. Required if the DC has multiple
                        domains.
  -computer-name COMPUTER-NAME$
                        Name of computer to add.If omitted, a random
                        DESKTOP-[A-Z0-9]{8} will be used.
  -computer-pass password
                        Password to set to computerIf omitted, a random
                        [A-Za-z0-9]{32} will be used.
  -no-add               Don't add a computer, only set password on existing
                        one.
  -delete               Delete an existing computer.
  -debug                Turn DEBUG output ON
  -method {SAMR,LDAPS}  Method of adding the computer.SAMR works over
                        SMB.LDAPS has some certificate requirementsand isn't
                        always available.
  -port {139,445,636}   Destination port to connect to. SAMR defaults to 445,
                        LDAPS to 636.

LDAP:
  -baseDN DC=test,DC=local
                        Set baseDN for LDAP.If ommited, the domain part (FQDN)
                        specified in the account parameter will be used.
  -computer-group CN=Computers,DC=test,DC=local
                        Group to which the account will be added.If omitted,
                        CN=Computers will be used,

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on account parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-host hostname     Hostname of the domain controller to use. If ommited,
                        the domain part (FQDN) specified in the account
                        parameter will be used
  -dc-ip ip             IP of the domain controller to use. Useful if you
                        can't translate the FQDN.specified in the account
                        parameter will be used
```

***

**impacket-atexec**

```
:~# impacket-atexec -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: atexec.py [-h] [-session-id SESSION_ID] [-ts] [-silentcommand] [-debug]
                 [-codec CODEC] [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                 [-aesKey hex key] [-dc-ip ip address] [-keytab KEYTAB]
                 target [command ...]

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>
  command               command to execute at the target

options:
  -h, --help            show this help message and exit
  -session-id SESSION_ID
                        an existed logon session to use (no output, no
                        cmd.exe)
  -ts                   adds timestamp to every logging output
  -silentcommand        does not execute cmd.exe to run given command (no
                        output)
  -debug                Turn DEBUG output ON
  -codec CODEC          Sets encoding used (codec) from the target's output
                        (default "utf-8"). If errors are detected, run
                        chcp.com at the target, map the result with https://do
                        cs.python.org/3/library/codecs.html#standard-encodings
                        and then execute wmiexec.py again with -codec and the
                        corresponding codec

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If omitted it
                        will use the domain part (FQDN) specified in the
                        target parameter
  -keytab KEYTAB        Read keys for SPN from keytab file
```

***

**impacket-dcomexec**

```
:~# impacket-dcomexec -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: dcomexec.py [-h] [-share SHARE] [-nooutput] [-ts] [-debug]
                   [-codec CODEC]
                   [-object [{ShellWindows,ShellBrowserWindow,MMC20}]]
                   [-com-version MAJOR_VERSION:MINOR_VERSION]
                   [-shell-type {cmd,powershell}] [-silentcommand]
                   [-hashes LMHASH:NTHASH] [-no-pass] [-k] [-aesKey hex key]
                   [-dc-ip ip address] [-A authfile] [-keytab KEYTAB]
                   target [command ...]

Executes a semi-interactive shell using the ShellBrowserWindow DCOM object.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>
  command               command to execute at the target. If empty it will
                        launch a semi-interactive shell

options:
  -h, --help            show this help message and exit
  -share SHARE          share where the output will be grabbed from (default
                        ADMIN$)
  -nooutput             whether or not to print the output (no SMB connection
                        created)
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON
  -codec CODEC          Sets encoding used (codec) from the target's output
                        (default "utf-8"). If errors are detected, run
                        chcp.com at the target, map the result with https://do
                        cs.python.org/3/library/codecs.html#standard-encodings
                        and then execute wmiexec.py again with -codec and the
                        corresponding codec
  -object [{ShellWindows,ShellBrowserWindow,MMC20}]
                        DCOM object to be used to execute the shell command
                        (default=ShellWindows)
  -com-version MAJOR_VERSION:MINOR_VERSION
                        DCOM version, format is MAJOR_VERSION:MINOR_VERSION
                        e.g. 5.7
  -shell-type {cmd,powershell}
                        choose a command processor for the semi-interactive
                        shell
  -silentcommand        does not execute cmd.exe to run given command (no
                        output, cannot run dir/cd/etc.)

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
  -A authfile           smbclient/mount.cifs-style authentication file. See
                        smbclient man page's -A option.
  -keytab KEYTAB        Read keys for SPN from keytab file
```

***

**impacket-dpapi**

```
:~# impacket-dpapi -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: dpapi.py [-h] [-debug]
                {backupkeys,masterkey,credential,vault,unprotect} ...

Example for using the DPAPI/Vault structures to unlock Windows Secrets.

positional arguments:
  {backupkeys,masterkey,credential,vault,unprotect}
                        actions
    backupkeys          domain backup key related functions
    masterkey           masterkey related functions
    credential          credential related functions
    vault               vault credential related functions
    unprotect           Provides CryptUnprotectData functionality

options:
  -h, --help            show this help message and exit
  -debug                Turn DEBUG output ON
```

***

**impacket-esentutl**

```
:~# impacket-esentutl -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: esentutl.py [-h] [-debug] [-page PAGE]
                   databaseFile {dump,info,export} ...

Extensive Storage Engine utility. Allows dumping catalog, pages and tables.

positional arguments:
  databaseFile        ESE to open
  {dump,info,export}  actions
    dump              dumps an specific page
    info              dumps the catalog info for the DB
    export            dumps the catalog info for the DB

options:
  -h, --help          show this help message and exit
  -debug              Turn DEBUG output ON
  -page PAGE          page to open
```

***

**impacket-exchanger**

```
:~# impacket-exchanger -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: exchanger.py [-h] [-debug] [-rpc-hostname RPC_HOSTNAME]
                    [-hashes LMHASH:NTHASH]
                    target {nspi} ...

A tool to abuse Exchange services

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>
  {nspi}                A module name
    nspi                Attack NSPI interface

options:
  -h, --help            show this help message and exit
  -debug                Turn DEBUG and EXTENDED output ON
  -rpc-hostname RPC_HOSTNAME
                        A name of the server in GUID (preferred) or NetBIOS
                        name format (see description in the beggining of this
                        file)

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
```

***

**impacket-findDelegation**

```
:~# impacket-findDelegation -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: findDelegation.py [-h] [-target-domain TARGET_DOMAIN] [-debug]
                         [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                         [-aesKey hex key] [-dc-ip ip address]
                         target

Queries target domain for delegation relationships

positional arguments:
  target                domain/username[:password]

options:
  -h, --help            show this help message and exit
  -target-domain TARGET_DOMAIN
                        Domain to query/request if different than the domain
                        of the user. Allows for retrieving delegation info
                        across trusts.
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter. Ignoredif -target-domain is specified.
```

***

**impacket-getArch**

```
:~# impacket-getArch -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: getArch.py [-h] [-target TARGET] [-targets TARGETS] [-timeout TIMEOUT]
                  [-debug]

Gets the target system's OS architecture version

options:
  -h, --help        show this help message and exit
  -target TARGET    <targetName or address>
  -targets TARGETS  input file with targets system to query Arch from (one per
                    line).
  -timeout TIMEOUT  socket timeout out when connecting to the target (default
                    2 sec)
  -debug            Turn DEBUG output ON
```

***

**impacket-getPac**

```
:~# impacket-getPac -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: getPac.py [-h] -targetUser TARGETUSER [-debug] [-hashes LMHASH:NTHASH]
                 credentials

positional arguments:
  credentials           domain/username[:password]. Valid domain credentials
                        to use for grabbing targetUser's PAC

options:
  -h, --help            show this help message and exit
  -targetUser TARGETUSER
                        the target user to retrieve the PAC of
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
```

***

**impacket-getST**

```
:~# impacket-getST -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: getST.py [-h] -spn SPN [-impersonate IMPERSONATE]
                [-additional-ticket ticket.ccache] [-ts] [-debug]
                [-force-forwardable] [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                [-aesKey hex key] [-dc-ip ip address]
                identity

Given a password, hash or aesKey, it will request a Service Ticket and save it
as ccache

positional arguments:
  identity              [domain/]username[:password]

options:
  -h, --help            show this help message and exit
  -spn SPN              SPN (service/server) of the target service the service
                        ticket will be generated for
  -impersonate IMPERSONATE
                        target username that will be impersonated (thru
                        S4U2Self) for quering the ST. Keep in mind this will
                        only work if the identity provided in this scripts is
                        allowed for delegation to the SPN specified
  -additional-ticket ticket.ccache
                        include a forwardable service ticket in a S4U2Proxy
                        request for RBCD + KCD Kerberos only
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON
  -force-forwardable    Force the service ticket obtained through S4U2Self to
                        be forwardable. For best results, the -hashes and
                        -aesKey values for the specified -identity should be
                        provided. This allows impresonation of protected users
                        and bypass of "Kerberos-only" constrained delegation
                        restrictions. See CVE-2020-17049

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
```

***

**impacket-getTGT**

```
:~# impacket-getTGT -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: getTGT.py [-h] [-ts] [-debug] [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                 [-aesKey hex key] [-dc-ip ip address]
                 identity

Given a password, hash or aesKey, it will request a TGT and save it as ccache

positional arguments:
  identity              [domain/]username[:password]

options:
  -h, --help            show this help message and exit
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
```

***

**impacket-goldenPac**

```
:~# impacket-goldenPac -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: goldenPac.py [-h] [-ts] [-debug] [-c pathname] [-w pathname]
                    [-dc-ip ip address] [-target-ip ip address]
                    [-hashes LMHASH:NTHASH]
                    target [command ...]

MS14-068 Exploit. It establishes a SMBConnection and PSEXEcs the target or
saves the TGT for later use.

positional arguments:
  target                [[domain/]username[:password]@]<targetName>
  command               command (or arguments if -c is used) to execute at the
                        target (w/o path). Defaults to cmd.exe. 'None' will
                        not execute PSEXEC (handy if you just want to save the
                        ticket)

options:
  -h, --help            show this help message and exit
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON
  -c pathname           uploads the filename for later execution, arguments
                        are passed in the command option
  -w pathname           writes the golden ticket in CCache format into the
                        <pathname> file
  -dc-ip ip address     IP Address of the domain controller (needed to get the
                        users SID). If omitted it will use the domain part
                        (FQDN) specified in the target parameter
  -target-ip ip address
                        IP Address of the target host you want to attack. If
                        omitted it will use the targetName parameter

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
```

***

**impacket-karmaSMB**

```
:~# impacket-karmaSMB --help
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: karmaSMB.py [--help] [-config pathname] [-smb2support] pathname

For every file request received, this module will return the pathname contents

positional arguments:
  pathname          Pathname's contents to deliver to SMB clients

options:
  --help            show this help message and exit
  -config pathname  config file name to map extensions to files to deliver.
                    For those extensions not present, pathname will be
                    delivered
  -smb2support      SMB2 Support (experimental!)
```

***

**impacket-keylistattack**

```
:~# impacket-keylistattack -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: keylistattack.py [-h] [-rodcNo RODCNO] [-rodcKey RODCKEY] [-full]
                        [-debug] [-domain DOMAIN] [-kdc KDC] [-t T] [-tf TF]
                        [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                        [-aesKey hex key] [-dc-ip ip address]
                        [-target-ip ip address]
                        target

Performs the KERB-KEY-LIST-REQ attack to dump secrets from the remote machine
without executing any agent there.

positional arguments:
  target                [[domain/]username[:password]@]<KDC HostName or IP
                        address> (Use this credential to authenticate to SMB
                        and list domain users (low-privilege account) or LIST
                        (if you want to parse a target file)

options:
  -h, --help            show this help message and exit
  -rodcNo RODCNO        Number of the RODC krbtgt account
  -rodcKey RODCKEY      AES key of the Read Only Domain Controller
  -full                 Run the attack against all domain users. Noisy! It
                        could lead to more TGS requests being rejected
  -debug                Turn DEBUG output ON

LIST option:
  -domain DOMAIN        The fully qualified domain name (only works with LIST)
  -kdc KDC              KDC HostName or FQDN (only works with LIST)
  -t T                  Attack only the username specified (only works with
                        LIST)
  -tf TF                File that contains a list of target usernames (only
                        works with LIST)

authentication:
  -hashes LMHASH:NTHASH
                        Use NTLM hashes to authenticate to SMB and list domain
                        users.
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos to authenticate to SMB and list domain
                        users. Grabs credentials from ccache file (KRB5CCNAME)
                        based on target parameters. If valid credentials
                        cannot be found, it will use the ones specified in the
                        command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)

connection:
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
  -target-ip ip address
                        IP Address of the target machine. If omitted it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
```

***

**impacket-kintercept**

```
:~# impacket-kintercept -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: kintercept.py [-h] [--server-port SERVER_PORT]
                     [--listen-port LISTEN_PORT] [--listen-addr LISTEN_ADDR]
                     [--request-handler HANDLER:ARG]
                     [--reply-handler HANDLER:ARG]
                     server

Intercept TCP streams

positional arguments:
  server                Target server address

options:
  -h, --help            show this help message and exit
  --server-port SERVER_PORT
                        Target server port
  --listen-port LISTEN_PORT
                        Port to listen on
  --listen-addr LISTEN_ADDR
                        Address to listen on
  --request-handler HANDLER:ARG
                        Example: s4u2else:user
  --reply-handler HANDLER:ARG
                        Example: tgs-rep-user:user
```

***

**impacket-lookupsid**

```
:~# impacket-lookupsid -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: lookupsid.py [-h] [-ts] [-target-ip ip address]
                    [-port [destination port]] [-domain-sids]
                    [-hashes LMHASH:NTHASH] [-no-pass]
                    target [maxRid]

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>
  maxRid                max Rid to check (default 4000)

options:
  -h, --help            show this help message and exit
  -ts                   Adds timestamp to every logging output

connection:
  -target-ip ip address
                        IP Address of the target machine. If omitted it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server
  -domain-sids          Enumerate Domain SIDs (will likely forward requests to
                        the DC)

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful when proxying through
                        smbrelayx)
```

***

**impacket-machine\_role**

```
:~# impacket-machine_role -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: machine_role.py [-h] [-ts] [-debug] [-dc-ip ip address]
                       [-target-ip ip address] [-port [destination port]]
                       [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                       [-aesKey hex key]
                       target

Retrieve a host's role along with its primary domain details.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>

options:
  -h, --help            show this help message and exit
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON

connection:
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
  -target-ip ip address
                        IP Address of the target machine. If ommited it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
```

***

**impacket-mimikatz**

```
:~# impacket-mimikatz -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: mimikatz.py [-h] [-file FILE] [-debug] [-hashes LMHASH:NTHASH]
                   [-no-pass] [-k] [-aesKey hex key] [-dc-ip ip address]
                   [-target-ip ip address]
                   target

SMB client implementation.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>

options:
  -h, --help            show this help message and exit
  -file FILE            input file with commands to execute in the mini shell
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)

connection:
  -dc-ip ip address     IP Address of the domain controller. If omitted it
                        will use the domain part (FQDN) specified in the
                        target parameter
  -target-ip ip address
                        IP Address of the target machine. If omitted it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
```

***

**impacket-mqtt\_check**

```
:~# impacket-mqtt_check --help
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: mqtt_check.py [--help] [-client-id CLIENT_ID] [-ssl] [-port PORT]
                     [-debug]
                     target

MQTT login check

positional arguments:
  target                [[domain/]username[:password]@]<targetName>

options:
  --help                show this help message and exit
  -client-id CLIENT_ID  Client ID used when authenticating (default random)
  -ssl                  turn SSL on
  -port PORT            port to connect to (default 1883)
  -debug                Turn DEBUG output ON
```

***

**impacket-mssqlclient**

```
:~# impacket-mssqlclient -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: mssqlclient.py [-h] [-port PORT] [-db DB] [-windows-auth] [-debug]
                      [-file FILE] [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                      [-aesKey hex key] [-dc-ip ip address]
                      target

TDS client implementation (SSL supported).

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>

options:
  -h, --help            show this help message and exit
  -port PORT            target MSSQL port (default 1433)
  -db DB                MSSQL database instance (default None)
  -windows-auth         whether or not to use Windows Authentication (default
                        False)
  -debug                Turn DEBUG output ON
  -file FILE            input file with commands to execute in the SQL shell

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
```

***

**impacket-mssqlinstance**

```
:~# impacket-mssqlinstance -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: mssqlinstance.py [-h] [-timeout TIMEOUT] host

Asks the remote host for its running MSSQL Instances.

positional arguments:
  host              target host

options:
  -h, --help        show this help message and exit
  -timeout TIMEOUT  timeout to wait for an answer
```

***

**impacket-nmapAnswerMachine**

```
:~# impacket-nmapAnswerMachine -h
Traceback (most recent call last):
  File "/usr/share/doc/python3-impacket/examples/nmapAnswerMachine.py", line 11, in <module>
    import uncrc32
ModuleNotFoundError: No module named 'uncrc32'
```

***

**impacket-ntfs-read**

```
:~# impacket-ntfs-read -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: ntfs-read.py [-h] [-extract EXTRACT] [-debug] volume

NTFS explorer (read-only)

positional arguments:
  volume            NTFS volume to open (e.g. \\.\C: or /dev/disk1s1)

options:
  -h, --help        show this help message and exit
  -extract EXTRACT  extracts pathname (e.g. \windows\system32\config\sam)
  -debug            Turn DEBUG output ON
```

***

**impacket-ntlmrelayx**

```
:~# impacket-ntlmrelayx -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: ntlmrelayx.py [-h] [-ts] [-debug] [-t TARGET] [-tf TARGETSFILE] [-w]
                     [-i] [-ip INTERFACE_IP] [--no-smb-server]
                     [--no-http-server] [--no-wcf-server] [--no-raw-server]
                     [--smb-port SMB_PORT] [--http-port HTTP_PORT]
                     [--wcf-port WCF_PORT] [--raw-port RAW_PORT]
                     [--no-multirelay] [-ra] [-r SMBSERVER] [-l LOOTDIR]
                     [-of OUTPUT_FILE] [-codec CODEC] [-smb2support]
                     [-ntlmchallenge NTLMCHALLENGE] [-socks] [-wh WPAD_HOST]
                     [-wa WPAD_AUTH_NUM] [-6] [--remove-mic]
                     [--serve-image SERVE_IMAGE] [-c COMMAND] [-e FILE]
                     [--enum-local-admins] [-rpc-mode {TSCH}] [-rpc-use-smb]
                     [-auth-smb [domain/]username[:password]]
                     [-hashes-smb LMHASH:NTHASH] [-rpc-smb-port {139,445}]
                     [-q QUERY] [-machine-account MACHINE_ACCOUNT]
                     [-machine-hashes LMHASH:NTHASH] [-domain DOMAIN]
                     [-remove-target] [--no-dump] [--no-da] [--no-acl]
                     [--no-validate-privs] [--escalate-user ESCALATE_USER]
                     [--add-computer [COMPUTERNAME [PASSWORD ...]]]
                     [--delegate-access] [--sid] [--dump-laps] [--dump-gmsa]
                     [--dump-adcs] [-k KEYWORD] [-m MAILBOX] [-a]
                     [-im IMAP_MAX] [--adcs] [--template TEMPLATE]
                     [--altname ALTNAME] [--shadow-credentials]
                     [--shadow-target SHADOW_TARGET]
                     [--pfx-password PFX_PASSWORD] [--export-type {PEM, PFX}]
                     [--cert-outfile-path CERT_OUTFILE_PATH]

For every connection received, this module will try to relay that connection
to specified target(s) system or the original client

Main options:
  -h, --help            show this help message and exit
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON
  -t TARGET, --target TARGET
                        Target to relay the credentials to, can be an IP,
                        hostname or URL like domain\:port
                        (domain\username and port are optional, and don't
                        forget to escape the '\'). If unspecified, it will
                        relay back to the client')
  -tf TARGETSFILE       File that contains targets by hostname or full URL,
                        one per line
  -w                    Watch the target file for changes and update target
                        list automatically (only valid with -tf)
  -i, --interactive     Launch an smbclient or LDAP console insteadof
                        executing a command after a successful relay. This
                        console will listen locally on a tcp port and can be
                        reached with for example netcat.
  -ip INTERFACE_IP, --interface-ip INTERFACE_IP
                        IP address of interface to bind SMB and HTTP servers
  --smb-port SMB_PORT   Port to listen on smb server
  --http-port HTTP_PORT
                        Port(s) to listen on HTTP server. Can specify multiple
                        ports by separating them with `,`, and ranges with
                        `-`. Ex: `80,8000-8010`
  --wcf-port WCF_PORT   Port to listen on wcf server
  --raw-port RAW_PORT   Port to listen on raw server
  --no-multirelay       If set, disable multi-host relay (SMB and HTTP
                        servers)
  -ra, --random         Randomize target selection
  -r SMBSERVER          Redirect HTTP requests to a file:// path on SMBSERVER
  -l LOOTDIR, --lootdir LOOTDIR
                        Loot directory in which gathered loot such as SAM
                        dumps will be stored (default: current directory).
  -of OUTPUT_FILE, --output-file OUTPUT_FILE
                        base output filename for encrypted hashes. Suffixes
                        will be added for ntlm and ntlmv2
  -codec CODEC          Sets encoding used (codec) from the target's output
                        (default "utf-8"). If errors are detected, run
                        chcp.com at the target, map the result with https://do
                        cs.python.org/3/library/codecs.html#standard-encodings
                        and then execute ntlmrelayx.py again with -codec and
                        the corresponding codec
  -smb2support          SMB2 Support
  -ntlmchallenge NTLMCHALLENGE
                        Specifies the NTLM server challenge used by the SMB
                        Server (16 hex bytes long. eg: 1122334455667788)
  -socks                Launch a SOCKS proxy for the connection relayed
  -wh WPAD_HOST, --wpad-host WPAD_HOST
                        Enable serving a WPAD file for Proxy Authentication
                        attack, setting the proxy host to the one supplied.
  -wa WPAD_AUTH_NUM, --wpad-auth-num WPAD_AUTH_NUM
                        Prompt for authentication N times for clients without
                        MS16-077 installed before serving a WPAD file.
                        (default=1)
  -6, --ipv6            Listen on both IPv6 and IPv4
  --remove-mic          Remove MIC (exploit CVE-2019-1040)
  --serve-image SERVE_IMAGE
                        local path of the image that will we returned to
                        clients
  -c COMMAND            Command to execute on target system (for SMB and RPC).
                        If not specified for SMB, hashes will be dumped
                        (secretsdump.py must be in the same directory). For
                        RPC no output will be provided.

  --no-smb-server       Disables the SMB server
  --no-http-server      Disables the HTTP server
  --no-wcf-server       Disables the WCF server
  --no-raw-server       Disables the RAW server

SMB client options:
  -e FILE               File to execute on the target system. If not
                        specified, hashes will be dumped (secretsdump.py must
                        be in the same directory)
  --enum-local-admins   If relayed user is not admin, attempt SAMR lookup to
                        see who is (only works pre Win 10 Anniversary)

RPC client options:
  -rpc-mode {TSCH}      Protocol to attack, only TSCH supported
  -rpc-use-smb          Relay DCE/RPC to SMB pipes
  -auth-smb [domain/]username[:password]
                        Use this credential to authenticate to SMB (low-
                        privilege account)
  -hashes-smb LMHASH:NTHASH
  -rpc-smb-port {139,445}
                        Destination port to connect to SMB

MSSQL client options:
  -q QUERY, --query QUERY
                        MSSQL query to execute(can specify multiple)

HTTP options:
  -machine-account MACHINE_ACCOUNT
                        Domain machine account to use when interacting with
                        the domain to grab a session key for signing, format
                        is domain/machine_name
  -machine-hashes LMHASH:NTHASH
                        Domain machine hashes, format is LMHASH:NTHASH
  -domain DOMAIN        Domain FQDN or IP to connect using NETLOGON
  -remove-target        Try to remove the target in the challenge message (in
                        case CVE-2019-1019 patch is not installed)

LDAP client options:
  --no-dump             Do not attempt to dump LDAP information
  --no-da               Do not attempt to add a Domain Admin
  --no-acl              Disable ACL attacks
  --no-validate-privs   Do not attempt to enumerate privileges, assume
                        permissions are granted to escalate a user via ACL
                        attacks
  --escalate-user ESCALATE_USER
                        Escalate privileges of this user instead of creating a
                        new one
  --add-computer [COMPUTERNAME [PASSWORD ...]]
                        Attempt to add a new computer account
  --delegate-access     Delegate access on relayed computer account to the
                        specified account
  --sid                 Use a SID to delegate access rather than an account
                        name
  --dump-laps           Attempt to dump any LAPS passwords readable by the
                        user
  --dump-gmsa           Attempt to dump any gMSA passwords readable by the
                        user
  --dump-adcs           Attempt to dump ADCS enrollment services and
                        certificate templates info

IMAP client options:
  -k KEYWORD, --keyword KEYWORD
                        IMAP keyword to search for. If not specified, will
                        search for mails containing "password"
  -m MAILBOX, --mailbox MAILBOX
                        Mailbox name to dump. Default: INBOX
  -a, --all             Instead of searching for keywords, dump all emails
  -im IMAP_MAX, --imap-max IMAP_MAX
                        Max number of emails to dump (0 = unlimited, default:
                        no limit)

AD CS attack options:
  --adcs                Enable AD CS relay attack
  --template TEMPLATE   AD CS template. Defaults to Machine or User whether
                        relayed account name ends with `$`. Relaying a DC
                        should require specifying `DomainController`
  --altname ALTNAME     Subject Alternative Name to use when performing ESC1
                        or ESC6 attacks.

Shadow Credentials attack options:
  --shadow-credentials  Enable Shadow Credentials relay attack (msDS-
                        KeyCredentialLink manipulation for PKINIT pre-
                        authentication)
  --shadow-target SHADOW_TARGET
                        target account (user or computer$) to populate msDS-
                        KeyCredentialLink from
  --pfx-password PFX_PASSWORD
                        password for the PFX stored self-signed certificate
                        (will be random if not set, not needed when exporting
                        to PEM)
  --export-type {PEM, PFX}
                        choose to export cert+private key in PEM or PFX (i.e.
                        #PKCS12) (default: PFX))
  --cert-outfile-path CERT_OUTFILE_PATH
                        filename to store the generated self-signed PEM or PFX
                        certificate and key
```

***

**impacket-ping**

```
:~# impacket-ping -h
Use: /usr/share/doc/python3-impacket/examples/ping.py <src ip> <dst ip>
```

***

**impacket-ping6**

```
:~# impacket-ping6 -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

Use: /usr/share/doc/python3-impacket/examples/ping6.py <src ip> <dst ip>
```

***

**impacket-psexec**

```
:~# impacket-psexec -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: psexec.py [-h] [-c pathname] [-path PATH] [-file FILE] [-ts] [-debug]
                 [-codec CODEC] [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                 [-aesKey hex key] [-keytab KEYTAB] [-dc-ip ip address]
                 [-target-ip ip address] [-port [destination port]]
                 [-service-name service_name]
                 [-remote-binary-name remote_binary_name]
                 target [command ...]

PSEXEC like functionality example using RemComSvc.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>
  command               command (or arguments if -c is used) to execute at the
                        target (w/o path) - (default:cmd.exe)

options:
  -h, --help            show this help message and exit
  -c pathname           copy the filename for later execution, arguments are
                        passed in the command option
  -path PATH            path of the command to execute
  -file FILE            alternative RemCom binary (be sure it doesn't require
                        CRT)
  -ts                   adds timestamp to every logging output
  -debug                Turn DEBUG output ON
  -codec CODEC          Sets encoding used (codec) from the target's output
                        (default "utf-8"). If errors are detected, run
                        chcp.com at the target, map the result with https://do
                        cs.python.org/3/library/codecs.html#standard-encodings
                        and then execute smbexec.py again with -codec and the
                        corresponding codec

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -keytab KEYTAB        Read keys for SPN from keytab file

connection:
  -dc-ip ip address     IP Address of the domain controller. If omitted it
                        will use the domain part (FQDN) specified in the
                        target parameter
  -target-ip ip address
                        IP Address of the target machine. If omitted it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server
  -service-name service_name
                        The name of the service used to trigger the payload
  -remote-binary-name remote_binary_name
                        This will be the name of the executable uploaded on
                        the target
```

***

**impacket-raiseChild**

```
:~# impacket-raiseChild -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: raiseChild.py [-h] [-ts] [-debug] [-w pathname]
                     [-target-exec target address] [-targetRID RID]
                     [-hashes LMHASH:NTHASH] [-no-pass] [-k] [-aesKey hex key]
                     target

Privilege Escalation from a child domain up to its forest

positional arguments:
  target                domain/username[:password]

options:
  -h, --help            show this help message and exit
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON
  -w pathname           writes the golden ticket in CCache format into the
                        <pathname> file
  -target-exec target address
                        Target host you want to PSEXEC against once the main
                        attack finished
  -targetRID RID        Target user RID you want to dump credentials.
                        Administrator (500) by default.

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
```

***

**impacket-rbcd**

```
:~# impacket-rbcd -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: rbcd.py [-h] -delegate-to DELEGATE_TO [-delegate-from DELEGATE_FROM]
               [-action [{read,write,remove,flush}]] [-use-ldaps] [-ts]
               [-debug] [-hashes LMHASH:NTHASH] [-no-pass] [-k]
               [-aesKey hex key] [-dc-ip ip address]
               identity

Python (re)setter for property msDS-AllowedToActOnBehalfOfOtherIdentity for
Kerberos RBCD attacks.

positional arguments:
  identity              domain.local/username[:password]

options:
  -h, --help            show this help message and exit
  -delegate-to DELEGATE_TO
                        Target computer account the attacker has at least
                        WriteProperty to
  -delegate-from DELEGATE_FROM
                        Attacker controlled machine account to write on the
                        msDS-Allo[...] property (only when using `-action
                        write`)
  -action [{read,write,remove,flush}]
                        Action to operate on msDS-
                        AllowedToActOnBehalfOfOtherIdentity
  -use-ldaps            Use LDAPS instead of LDAP
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)

connection:
  -dc-ip ip address     IP Address of the domain controller or KDC (Key
                        Distribution Center) for Kerberos. If omitted it will
                        use the domain part (FQDN) specified in the identity
                        parameter
```

***

**impacket-rdp\_check**

```
:~# impacket-rdp_check -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: rdp_check.py [-h] [-hashes LMHASH:NTHASH] target

Test whether an account is valid on the target host using the RDP protocol.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>

options:
  -h, --help            show this help message and exit

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
```

***

**impacket-reg**

```
:~# impacket-reg -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: reg.py [-h] [-debug] [-hashes LMHASH:NTHASH] [-no-pass] [-k]
              [-aesKey hex key] [-dc-ip ip address] [-target-ip ip address]
              [-port [destination port]]
              target {query,add,delete,save,backup} ...

Windows Register manipulation script.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>
  {query,add,delete,save,backup}
                        actions
    query               Returns a list of the next tier of subkeys and entries
                        that are located under a specified subkey in the
                        registry.
    add                 Adds a new subkey or entry to the registry
    delete              Deletes a subkey or entries from the registry
    save                Saves a copy of specified subkeys, entries, and values
                        of the registry in a specified file.
    backup              (special command) Backs up HKLM\SAM, HKLM\SYSTEM and
                        HKLM\SECURITY to a specified file.

options:
  -h, --help            show this help message and exit
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)

connection:
  -dc-ip ip address     IP Address of the domain controller. If omitted it
                        will use the domain part (FQDN) specified in the
                        target parameter
  -target-ip ip address
                        IP Address of the target machine. If omitted it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server
```

***

**impacket-registry-read**

```
:~# impacket-registry-read -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: registry-read.py [-h]
                        hive {enum_key,enum_values,get_value,get_class,walk}
                        ...

Reads data from registry hives.

positional arguments:
  hive                  registry hive to open
  {enum_key,enum_values,get_value,get_class,walk}
                        actions
    enum_key            enumerates the subkeys of the specified open registry
                        key
    enum_values         enumerates the values for the specified open registry
                        key
    get_value           retrieves the data for the specified registry value
    get_class           retrieves the data for the specified registry class
    walk                walks the registry from the name node down

options:
  -h, --help            show this help message and exit
```

***

**impacket-rpcmap**

```
:~# impacket-rpcmap -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: rpcmap.py [-h] [-brute-uuids] [-brute-opnums] [-brute-versions]
                 [-opnum-max OPNUM_MAX] [-version-max VERSION_MAX]
                 [-auth-level AUTH_LEVEL] [-uuid UUID] [-debug]
                 [-target-ip ip address] [-port [destination port]]
                 [-auth-rpc AUTH_RPC] [-auth-transport AUTH_TRANSPORT]
                 [-hashes-rpc LMHASH:NTHASH] [-hashes-transport LMHASH:NTHASH]
                 [-no-pass]
                 stringbinding

Lookups listening MSRPC interfaces.

positional arguments:
  stringbinding         String binding to connect to MSRPC interface, for example:
                        ncacn_ip_tcp:192.168.0.1[135]
                        ncacn_np:192.168.0.1[\pipe\spoolss]
                        ncacn_http:192.168.0.1[593]
                        ncacn_http:[6001,RpcProxy=exchange.contoso.com:443]
                        ncacn_http:localhost[3388,RpcProxy=rds.contoso:443]

options:
  -h, --help            show this help message and exit
  -brute-uuids          Bruteforce UUIDs even if MGMT interface is available
  -brute-opnums         Bruteforce opnums for found UUIDs
  -brute-versions       Bruteforce major versions of found UUIDs
  -opnum-max OPNUM_MAX  Bruteforce opnums from 0 to N, default 64
  -version-max VERSION_MAX
                        Bruteforce versions from 0 to N, default 64
  -auth-level AUTH_LEVEL
                        MS-RPCE auth level, from 1 to 6, default 6
                        (RPC_C_AUTHN_LEVEL_PKT_PRIVACY)
  -uuid UUID            Test only this UUID
  -debug                Turn DEBUG output ON

ncacn-np-details:
  -target-ip ip address
                        IP Address of the target machine. If omitted it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server

authentication:
  -auth-rpc AUTH_RPC    [domain/]username[:password]
  -auth-transport AUTH_TRANSPORT
                        [domain/]username[:password]
  -hashes-rpc LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -hashes-transport LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for passwords
```

***

**impacket-sambaPipe**

```
:~# impacket-sambaPipe -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: sambaPipe.py [-h] -so SO [-debug] [-hashes LMHASH:NTHASH] [-no-pass]
                    [-k] [-aesKey hex key] [-dc-ip ip address]
                    [-target-ip ip address] [-port [destination port]]
                    target

Samba Pipe exploit

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>

options:
  -h, --help            show this help message and exit
  -so SO                so filename to upload and load
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)

connection:
  -dc-ip ip address     IP Address of the domain controller. If omitted it
                        will use the domain part (FQDN) specified in the
                        target parameter
  -target-ip ip address
                        IP Address of the target machine. If omitted it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server
```

***

**impacket-services**

```
:~# impacket-services -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: services.py [-h] [-debug] [-hashes LMHASH:NTHASH] [-no-pass] [-k]
                   [-aesKey hex key] [-dc-ip ip address]
                   [-target-ip ip address] [-port [destination port]]
                   target {start,stop,delete,status,config,list,create,change}
                   ...

Windows Service manipulation script.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>
  {start,stop,delete,status,config,list,create,change}
                        actions
    start               starts the service
    stop                stops the service
    delete              deletes the service
    status              returns service status
    config              returns service configuration
    list                list available services
    create              create a service
    change              change a service configuration

options:
  -h, --help            show this help message and exit
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)

connection:
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
  -target-ip ip address
                        IP Address of the target machine. If ommited it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server
```

***

**impacket-smbclient**

```
:~# impacket-smbclient -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: smbclient.py [-h] [-file FILE] [-debug] [-hashes LMHASH:NTHASH]
                    [-no-pass] [-k] [-aesKey hex key] [-dc-ip ip address]
                    [-target-ip ip address] [-port [destination port]]
                    target

SMB client implementation.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>

options:
  -h, --help            show this help message and exit
  -file FILE            input file with commands to execute in the mini shell
  -debug                Turn DEBUG output ON

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)

connection:
  -dc-ip ip address     IP Address of the domain controller. If omitted it
                        will use the domain part (FQDN) specified in the
                        target parameter
  -target-ip ip address
                        IP Address of the target machine. If omitted it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server
```

***

**impacket-smbexec**

```
:~# impacket-smbexec -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: smbexec.py [-h] [-share SHARE] [-mode {SERVER,SHARE}] [-ts] [-debug]
                  [-codec CODEC] [-shell-type {cmd,powershell}]
                  [-dc-ip ip address] [-target-ip ip address]
                  [-port [destination port]] [-service-name service_name]
                  [-hashes LMHASH:NTHASH] [-no-pass] [-k] [-aesKey hex key]
                  [-keytab KEYTAB]
                  target

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>

options:
  -h, --help            show this help message and exit
  -share SHARE          share where the output will be grabbed from (default
                        C$)
  -mode {SERVER,SHARE}  mode to use (default SHARE, SERVER needs root!)
  -ts                   adds timestamp to every logging output
  -debug                Turn DEBUG output ON
  -codec CODEC          Sets encoding used (codec) from the target's output
                        (default "utf-8"). If errors are detected, run
                        chcp.com at the target, map the result with https://do
                        cs.python.org/3/library/codecs.html#standard-encodings
                        and then execute smbexec.py again with -codec and the
                        corresponding codec
  -shell-type {cmd,powershell}
                        choose a command processor for the semi-interactive
                        shell

connection:
  -dc-ip ip address     IP Address of the domain controller. If omitted it
                        will use the domain part (FQDN) specified in the
                        target parameter
  -target-ip ip address
                        IP Address of the target machine. If ommited it will
                        use whatever was specified as target. This is useful
                        when target is the NetBIOS name and you cannot resolve
                        it
  -port [destination port]
                        Destination port to connect to SMB Server
  -service-name service_name
                        The name of theservice used to trigger the payload

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -keytab KEYTAB        Read keys for SPN from keytab file
```

***

**impacket-smbpasswd**

```
:~# impacket-smbpasswd -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: smbpasswd.py [-h] [-ts] [-debug]
                    [-newpass NEWPASS | -newhashes LMHASH:NTHASH]
                    [-hashes LMHASH:NTHASH] [-altuser ALTUSER]
                    [-altpass ALTPASS] [-althash ALTHASH] [-admin]
                    target

Change password over SMB.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>

options:
  -h, --help            show this help message and exit
  -ts                   adds timestamp to every logging output
  -debug                turn DEBUG output ON
  -newpass NEWPASS      new SMB password
  -newhashes LMHASH:NTHASH
                        new NTLM hashes, format is LMHASH:NTHASH (the user
                        will be asked to change their password at next logon)

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH

RPC authentication:
  -altuser ALTUSER      alternative username
  -altpass ALTPASS      alternative password
  -althash ALTHASH      alternative NT hash

set credentials method:
  -admin                injects credentials into SAM (requires admin's
                        priveleges on a machine, but can bypass password
                        history policy)
```

***

**impacket-smbrelayx**

```
:~# impacket-smbrelayx --help
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: smbrelayx.py [--help] [-ts] [-debug] [-h HOST]
                    [-s {logon_failure,denied,success}] [-e FILE] [-c COMMAND]
                    [-socks] [-one-shot] [-codec CODEC]
                    [-outputfile OUTPUTFILE]
                    [-machine-account MACHINE_ACCOUNT]
                    [-machine-hashes LMHASH:NTHASH] [-domain DOMAIN]

For every connection received, this module will try to SMB relay that
connection to the target system or the original client

options:
  --help                show this help message and exit
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON
  -h HOST               Host to relay the credentials to, if not it will relay
                        it back to the client
  -s {logon_failure,denied,success}
                        Status to return after client performed
                        authentication. Default: "success".
  -e FILE               File to execute on the target system. If not
                        specified, hashes will be dumped (secretsdump.py must
                        be in the same directory)
  -c COMMAND            Command to execute on target system. If not specified,
                        hashes will be dumped (secretsdump.py must be in the
                        same directory)
  -socks                Launch a SOCKS proxy for the connection relayed
  -one-shot             After successful authentication, only execute the
                        attack once for each target
  -codec CODEC          Sets encoding used (codec) from the target's output
                        (default "utf-8"). If errors are detected, run
                        chcp.com at the target, map the result with https://do
                        cs.python.org/3/library/codecs.html#standard-encodings
                        and then execute smbrelayx.py again with -codec and
                        the corresponding codec
  -outputfile OUTPUTFILE
                        base output filename for encrypted hashes. Suffixes
                        will be added for ntlm and ntlmv2
  -machine-account MACHINE_ACCOUNT
                        Domain machine account to use when interacting with
                        the domain to grab a session key for signing, format
                        is domain/machine_name
  -machine-hashes LMHASH:NTHASH
                        Domain machine hashes, format is LMHASH:NTHASH
  -domain DOMAIN        Domain FQDN or IP to connect using NETLOGON
```

***

**impacket-smbserver**

```
:~# impacket-smbserver -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: smbserver.py [-h] [-comment COMMENT] [-username USERNAME]
                    [-password PASSWORD] [-hashes LMHASH:NTHASH] [-ts]
                    [-debug] [-ip INTERFACE_ADDRESS] [-port PORT]
                    [-smb2support]
                    shareName sharePath

This script will launch a SMB Server and add a share specified as an argument.
You need to be root in order to bind to port 445. For optional authentication,
it is possible to specify username and password or the NTLM hash. Example:
smbserver.py -comment 'My share' TMP /tmp

positional arguments:
  shareName             name of the share to add
  sharePath             path of the share to add

options:
  -h, --help            show this help message and exit
  -comment COMMENT      share's comment to display when asked for shares
  -username USERNAME    Username to authenticate clients
  -password PASSWORD    Password for the Username
  -hashes LMHASH:NTHASH
                        NTLM hashes for the Username, format is LMHASH:NTHASH
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON
  -ip INTERFACE_ADDRESS, --interface-address INTERFACE_ADDRESS
                        ip address of listening interface
  -port PORT            TCP port for listening incoming connections (default
                        445)
  -smb2support          SMB2 Support (experimental!)
```

***

**impacket-sniff**

```
:~# impacket-sniff -h
0 - eth0
1 - any
2 - lo
3 - bluetooth-monitor
4 - nflog
5 - nfqueue
6 - dbus-system
7 - dbus-session
Please select an interface: 
```

***

**impacket-sniffer**

```
:~# impacket-sniffer -h
Ignoring unknown protocol: -h
There are no protocols available.
```

***

**impacket-split**

```
:~# impacket-split -h
Traceback (most recent call last):
  File "/usr/share/doc/python3-impacket/examples/split.py", line 145, in <module>
    main(sys.argv[1])
  File "/usr/share/doc/python3-impacket/examples/split.py", line 128, in main
    p = open_offline(filename)
        ^^^^^^^^^^^^^^^^^^^^^^
pcapy.PcapError: -h: No such file or directory
```

***

**impacket-ticketConverter**

```
:~# impacket-ticketConverter -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: ticketConverter.py [-h] input_file output_file

positional arguments:
  input_file   File in kirbi (KRB-CRED) or ccache format
  output_file  Output file

options:
  -h, --help   show this help message and exit
```

***

**impacket-ticketer**

```
:~# impacket-ticketer -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: ticketer.py [-h] [-spn SPN] [-request] -domain DOMAIN -domain-sid
                   DOMAIN_SID [-aesKey hex key] [-nthash NTHASH]
                   [-keytab KEYTAB] [-groups GROUPS] [-user-id USER_ID]
                   [-extra-sid EXTRA_SID] [-duration DURATION] [-ts] [-debug]
                   [-user USER] [-password PASSWORD] [-hashes LMHASH:NTHASH]
                   [-dc-ip ip address]
                   target

Creates a Kerberos golden/silver tickets based on user options

positional arguments:
  target                username for the newly created ticket

options:
  -h, --help            show this help message and exit
  -spn SPN              SPN (service/server) of the target service the silver
                        ticket will be generated for. if omitted, golden
                        ticket will be created
  -request              Requests ticket to domain and clones it changing only
                        the supplied information. It requires specifying -user
  -domain DOMAIN        the fully qualified domain name (e.g. contoso.com)
  -domain-sid DOMAIN_SID
                        Domain SID of the target domain the ticker will be
                        generated for
  -aesKey hex key       AES key used for signing the ticket (128 or 256 bits)
  -nthash NTHASH        NT hash used for signing the ticket
  -keytab KEYTAB        Read keys for SPN from keytab file (silver ticket
                        only)
  -groups GROUPS        comma separated list of groups user will belong to
                        (default = 513, 512, 520, 518, 519)
  -user-id USER_ID      user id for the user the ticket will be created for
                        (default = 500)
  -extra-sid EXTRA_SID  Comma separated list of ExtraSids to be included
                        inside the ticket's PAC
  -duration DURATION    Amount of days till the ticket expires (default =
                        365*10)
  -ts                   Adds timestamp to every logging output
  -debug                Turn DEBUG output ON

authentication:
  -user USER            domain/username to be used if -request is chosen (it
                        can be different from domain/username
  -password PASSWORD    password for domain/username
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
```

***

**impacket-wmipersist**

```
:~# impacket-wmipersist -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: wmipersist.py [-h] [-debug] [-com-version MAJOR_VERSION:MINOR_VERSION]
                     [-hashes LMHASH:NTHASH] [-no-pass] [-k] [-aesKey hex key]
                     [-dc-ip ip address]
                     target {install,remove} ...

Creates/Removes a WMI Event Consumer/Filter and link between both to execute
Visual Basic based on the WQL filter or timer specified.

positional arguments:
  target                [domain/][username[:password]@]<address>
  {install,remove}      actions
    install             installs the wmi event consumer/filter
    remove              removes the wmi event consumer/filter

options:
  -h, --help            show this help message and exit
  -debug                Turn DEBUG output ON
  -com-version MAJOR_VERSION:MINOR_VERSION
                        DCOM version, format is MAJOR_VERSION:MINOR_VERSION
                        e.g. 5.7

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
```

***

**impacket-wmiquery**

```
:~# impacket-wmiquery -h
Impacket v0.10.0 - Copyright 2022 SecureAuth Corporation

usage: wmiquery.py [-h] [-namespace NAMESPACE] [-file FILE] [-debug]
                   [-com-version MAJOR_VERSION:MINOR_VERSION]
                   [-hashes LMHASH:NTHASH] [-no-pass] [-k] [-aesKey hex key]
                   [-dc-ip ip address]
                   [-rpc-auth-level [{integrity,privacy,default}]]
                   target

Executes WQL queries and gets object descriptions using Windows Management
Instrumentation.

positional arguments:
  target                [[domain/]username[:password]@]<targetName or address>

options:
  -h, --help            show this help message and exit
  -namespace NAMESPACE  namespace name (default //./root/cimv2)
  -file FILE            input file with commands to execute in the WQL shell
  -debug                Turn DEBUG output ON
  -com-version MAJOR_VERSION:MINOR_VERSION
                        DCOM version, format is MAJOR_VERSION:MINOR_VERSION
                        e.g. 5.7

authentication:
  -hashes LMHASH:NTHASH
                        NTLM hashes, format is LMHASH:NTHASH
  -no-pass              don't ask for password (useful for -k)
  -k                    Use Kerberos authentication. Grabs credentials from
                        ccache file (KRB5CCNAME) based on target parameters.
                        If valid credentials cannot be found, it will use the
                        ones specified in the command line
  -aesKey hex key       AES key to use for Kerberos Authentication (128 or 256
                        bits)
  -dc-ip ip address     IP Address of the domain controller. If ommited it use
                        the domain part (FQDN) specified in the target
                        parameter
  -rpc-auth-level [{integrity,privacy,default}]
                        default, integrity (RPC_C_AUTHN_LEVEL_PKT_INTEGRITY)
                        or privacy (RPC_C_AUTHN_LEVEL_PKT_PRIVACY). For
                        example CIM path "root/MSCluster" would require
                        privacy level by default)
```

***

Updated on: 2023-Mar-08\


***
