# ⏭ freerdp2

### Packages and Binaries:

#### freerdp2-dev <a href="#freerdp2-dev" id="freerdp2-dev"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

This package contains the FreeRDP development files.

**Installed size:** `935 KB`\
**How to install:** `sudo apt install freerdp2-dev`

<details>

<summary>Dependencies:</summary>

* libfreerdp-client2-2
* libfreerdp-server2-2
* libfreerdp-shadow-subsystem2-2
* libfreerdp-shadow2-2
* libfreerdp2-2
* libwinpr2-dev
* winpr-utils

</details>

***

#### freerdp2-shadow-x11 <a href="#freerdp2-shadow-x11" id="freerdp2-shadow-x11"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

This package contains a “shadowing” server that can be used to share an already started X11 DISPLAY.

**Installed size:** `153 KB`\
**How to install:** `sudo apt install freerdp2-shadow-x11`

<details>

<summary>Dependencies:</summary>

* libc6
* libfreerdp-shadow-subsystem2-2
* libfreerdp-shadow2-2
* libwinpr2-2

</details>

**freerdp-shadow-cli**

A utility for sharing a X display via RDP.

```
:~# freerdp-shadow-cli -h
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - Usage: freerdp-shadow-cli [options]
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - Syntax:
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /flag (enables flag)
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /option:<value> (specifies option with value)
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     +toggle -toggle (enables or disables toggle, where '/' is a synonym of '+')
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - port:<number>       
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Server port
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - ipc-socket:<ipc-socket>
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Server IPC socket
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - bind-address:<bind-address>[,<another address>, ...]
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	An address to bind to. Use '[<ipv6>]' for IPv6 addresses, e.g. '[::1]' for localhost
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - monitors:<0,1,2...> 
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Select or list monitors
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - rect:<x,y,w,h>      
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Select rectangle within monitor to share
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     +
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - auth (default:off)  
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Clients must authenticate
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     -
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - may-view (default:on)
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Clients may view without prompt
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     -
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - may-interact (default:on)
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Clients may interact without prompt
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - sec:<rdp|tls|nla|ext>
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	force specific protocol security
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     -
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - sec-rdp (default:on)
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	rdp protocol security
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     -
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - sec-tls (default:on)
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	tls protocol security
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     -
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - sec-nla (default:on)
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	nla protocol security
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     +
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - sec-ext (default:off)
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	nla extended protocol security
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - sam-file:<file>     
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	NTLM SAM file for NLA authentication
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - version             
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Print version
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - buildconfig         
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Print the build configuration
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] -     /
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - help                
[09:06:01:958] [170567:170567] [INFO][com.freerdp.server.shadow] - 	Print help
```

***

#### freerdp2-wayland <a href="#freerdp2-wayland" id="freerdp2-wayland"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

Currently, the FreeRDP clients supports the following Windows Versions:

* Windows NT Server
* Windows 2000 Terminal Server
* Windows XP
* Windows 2003 Server
* Windows Vista
* Windows 2008/2008r2/2011SBS Server
* Windows 7
* Windows 2012/2012r2 Server
* Windows 8
* Windows 10

This package contains the wayland based client.

**Installed size:** `180 KB`\
**How to install:** `sudo apt install freerdp2-wayland`

<details>

<summary>Dependencies:</summary>

* libc6
* libfreerdp-client2-2
* libfreerdp2-2
* libuwac0-0
* libwinpr2-2

</details>

**wlfreerdp**

FreeRDP wayland client

```
:~# man wlfreerdp
wlfreerdp(1)                        FreeRDP                       wlfreerdp(1)

NAME
       wlfreerdp - FreeRDP wayland client

SYNOPSIS
       wlfreerdp  [file]  [default_client_options] [/v:<server>[:port]] [/ver-
       sion] [/help]

DESCRIPTION
       wlfreerdp is a wayland Remote Desktop Protocol (RDP)  client  which  is
       part  of the FreeRDP project. A RDP server is built-in to many editions
       of Windows. Alternative servers included xrdp and VRDP (VirtualBox).

OPTIONS
       The wayland client also supports a lot of the  default  client  options
       which  are not described here. For details on those see the xfreerdp(1)
       man page.

       /v:<server>[:port]
              The server hostname or IP, and optionally the port,  to  connect
              to.

       /version
              Print the version and exit.

       /help  Print the help and exit.

EXIT STATUS
       0      Successful program execution.

       not 0  On failure.

SEE ALSO
       xfreerdp(1) wlog(7)

AUTHOR
       FreeRDP <>

2.9.0                             2017-01-12                      wlfreerdp(1)
```

***

#### freerdp2-x11 <a href="#freerdp2-x11" id="freerdp2-x11"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

Currently, the FreeRDP client supports the following Windows Versions:

* Windows NT Server
* Windows 2000 Terminal Server
* Windows XP
* Windows 2003 Server
* Windows Vista
* Windows 2008/2008r2/2011SBS Server
* Windows 7
* Windows 2012/2012r2 Server
* Windows 8
* Windows 10

This package contains the X11 based client.

**Installed size:** `818 KB`\
**How to install:** `sudo apt install freerdp2-x11`

<details>

<summary>Dependencies:</summary>

* libc6
* libfreerdp-client2-2
* libfreerdp2-2
* libwinpr2-2
* libx11-6
* libxcursor1
* libxext6
* libxfixes3
* libxi6
* libxinerama1
* libxrandr2
* libxrender1

</details>

**xfreerdp**

FreeRDP X11 client

```
:~# man xfreerdp
XFREERDP(1)                        xfreerdp                        XFREERDP(1)

NAME
       xfreerdp - FreeRDP X11 client

SYNOPSIS
       xfreerdp [file] [options] [/v:server[:port]]

DESCRIPTION
       xfreerdp is an X11 Remote Desktop Protocol (RDP) client which is part
       of the FreeRDP project. An RDP server is built-in to many editions of
       Windows. Alternative servers included xrdp and VRDP (VirtualBox).

OPTIONS
       /a:addin[,options], /addin:addin[,options]
           Addin

       /action-script:file-name
           Action script (default:~/.config/freerdp/action.sh)

       /admin, /console
           Admin (or console) session

       +aero
           desktop composition (default:off)

       /app:path or ||alias
           Remote application program

       /app-cmd:parameters
           Remote application command-line parameters

       /app-file:file-name
           File to open with remote application

       /app-guid:app-guid
           Remote application GUID

       /app-icon:icon-path
           Remote application icon for user interface

       /app-name:app-name
           Remote application name for user interface

       /app-workdir:workspace path
           Remote application workspace path

       /assistance:password
           Remote assistance password

       /auto-request-control:
           Automatically request remote assistance input control

       +async-channels
           Asynchronous channels (experimental) (default:off)

       +async-input
           Asynchronous input (default:off)

       +async-update
           Asynchronous update (default:off)

       /audio-mode:mode
           Audio output mode

       +auth-only
           Authenticate only (default:off)

       -authentication
           Authentication (experimental) (default:on)

       +auto-reconnect
           Automatic reconnection (default:off)

       /auto-reconnect-max-retries:retries
           Automatic reconnection maximum retries, 0 for unlimited [0,1000]

       +bitmap-cache
           bitmap cache (default:off)

       /bpp:depth
           Session bpp (color depth) (default:16)

       /buildconfig
           Print the build configuration

       /cert:[deny,ignore,name:name,tofu,fingerprint:hash:hash as
       hex[,fingerprint:hash:another hash]]
           Certificate accept options. Use with care! * deny ... Automatically
           abort connection if the certificate does not match, no user
           interaction. * ignore ... Ignore the certificate checks altogether
           (overrules all other options) * name ... Use the alternate <name>
           instead of the certificate subject to match locally stored
           certificates * tofu ... Accept certificate unconditionally on first
           connect and deny on subsequent connections if the certificate does
           not match * fingerprints ... A list of certificate hashes that are
           accepted unconditionally for a connection

       /cert-deny
           [deprecated, use /cert:deny] Automatically abort connection for any
           certificate that can not be validated.

       /cert-ignore
           [deprecated, use /cert:ignore] Ignore certificate

       /cert-name:name
           [deprecated, use /cert:name:<name>] Certificate name

       /cert-tofu
           [deprecated, use /cert:tofu] Automatically accept certificate on
           first connect

       /client-build-number:number
           Client Build Number sent to server (influences smartcard behaviour,
           see [MS-RDPESC])

       /client-hostname:name
           Client Hostname to send to server

       /clipboard:[use-selection:atom]
           Redirect clipboard. * use-selection:<atom> ... (X11) Specify which
           X selection to access. Default is CLIPBOARD. PRIMARY is the X-style
           middle-click selection. (default:on)

       /codec-cache:[rfx|nsc|jpeg]
           Bitmap codec cache

       -compression, -z
           compression (default:on)

       /compression-level:level
           Compression level (0,1,2)

       +credentials-delegation
           credentials delegation (default:off)

       /d:domain
           Domain

       -decorations
           Window decorations (default:on)

       /disp
           Display control

       /drive:name,path
           Redirect directory <path> as named share <name>. Hotplug support is
           enabled with /drive:hotplug,*. This argument provides the same
           function as "Drives that I plug in later" option in MSTSC.

       +drives
           Redirect all mount points as shares (default:off)

       /dvc:channel[,options]
           Dynamic virtual channel

       /dynamic-resolution
           Send resolution updates when the window is resized

       /echo, /echo
           Echo channel

       -encryption
           Encryption (experimental) (default:on)

       /encryption-methods:[40,][56,][128,][FIPS]
           RDP standard security encryption methods

       /f
           Fullscreen mode (<Ctrl>+<Alt>+<Enter> toggles fullscreen)

       -fast-path
           fast-path input/output (default:on)

       +fipsmode
           FIPS mode (default:off)

       /floatbar[:sticky:[on|off],default:[visible|hidden],show:[always|fullscreen||window]]
           floatbar is disabled by default (when enabled defaults to sticky in
           fullscreen mode)

       -fonts
           smooth fonts (ClearType) (default:on)

       /frame-ack:number
           Number of frame acknowledgement

       /from-stdin[:force]
           Read credentials from stdin. With <force> the prompt is done before
           connection, otherwise on server request.

       /g:gateway[:port]
           Gateway Hostname

       /gateway-usage-method:[direct|detect], /gum:[direct|detect]
           Gateway usage method

       /gd:domain
           Gateway domain

       /gdi:sw|hw
           GDI rendering

       /geometry
           Geometry tracking channel

       +gestures
           Consume multitouch input locally (default:off)

       /gfx[:RFX]
           RDP8 graphics pipeline

       +gfx-progressive
           RDP8 graphics pipeline using progressive codec (default:off)

       +gfx-small-cache
           RDP8 graphics pipeline using small cache mode (default:off)

       +gfx-thin-client
           RDP8 graphics pipeline using thin client mode (default:off)

       +glyph-cache
           Glyph cache (experimental) (default:off)

       /gp:password
           Gateway password

       -grab-keyboard
           Grab keyboard (default:on)

       /gt:[rpc|http[,no-websockets]|auto[,no-websockets]]
           Gateway transport type

       /gu:[[domain\]user|user[@domain]]
           Gateway username

       /gat:access token
           Gateway Access Token

       /h:height
           Height (default:768)

       -heartbeat
           Support heartbeat PDUs (default:on)

       /help, /?
           Print help

       +home-drive
           Redirect user home as share (default:off)

       /ipv6, /6
           Prefer IPv6 AAA record over IPv4 A record

       /kbd:0xid or name
           Keyboard layout

       /kbd-lang:0xid
           Keyboard active language identifier

       /kbd-fn-key:value
           Function key value

       /kbd-list
           List keyboard layouts

       /kbd-lang-list
           List keyboard languages

       /kbd-remap:List of key=value,... pairs to remap scancodes
           Keyboard scancode remapping

       /kbd-subtype:id
           Keyboard subtype

       /kbd-type:id
           Keyboard type

       /load-balance-info:info-string
           Load balance info

       /log-filters:tag:level[,tag:level[,...]]
           Set logger filters, see wLog(7) for details

       /log-level:[OFF|FATAL|ERROR|WARN|INFO|DEBUG|TRACE]
           Set the default log level, see wLog(7) for details

       /max-fast-path-size:size
           Specify maximum fast-path update size

       /max-loop-time:time
           Specify maximum time in milliseconds spend treating packets

       +menu-anims
           menu animations (default:off)

       /microphone[:[sys:sys,][dev:dev,][format:format,][rate:rate,][channel:channel]],
       /mic[:[sys:sys,][dev:dev,][format:format,][rate:rate,][channel:channel]]
           Audio input (microphone)

       /monitor-list
           List detected monitors

       /monitors:id[,id[,...]]
           Select monitors to use

       -mouse-motion
           Send mouse motion (default:on)

       /multimon[:force]
           Use multiple monitors

       +multitouch
           Redirect multitouch input (default:off)

       +multitransport
           Support multitransport protocol (default:off)

       -nego
           protocol security negotiation (default:on)

       /network:[modem|broadband|broadband-low|broadband-high|wan|lan|auto]
           Network connection type

       /nsc, /nscodec
           NSCodec support

       +offscreen-cache
           offscreen bitmap cache (default:off)

       /orientation:[0|90|180|270]
           Orientation of display in degrees

       +old-license
           Use the old license workflow (no CAL and hwId set to 0)
           (default:off)

       /p:password
           Password

       /parallel[:name[,path]]
           Redirect parallel device

       /parent-window:window-id
           Parent window id

       +password-is-pin
           Use smart card authentication with password as smart card PIN
           (default:off)

       /pcb:blob
           Preconnection Blob

       /pcid:id
           Preconnection Id

       /pheight:height
           Physical height of display (in millimeters)

       /play-rfx:pcap-file
           Replay rfx pcap file

       /port:number
           Server port

       -suppress-output
           suppress output when minimized (default:on)

       +print-reconnect-cookie
           Print base64 reconnect cookie after connecting (default:off)

       /printer[:name[,driver]]
           Redirect printer device

       /proxy:[proto://][user:]host:port
           Proxy settings: override env. var (see also environment variable
           below). Protocol "socks5" should be given explicitly where "http"
           is default.

       /pth:password-hash, /pass-the-hash:password-hash
           Pass the hash (restricted admin mode)

       /pwidth:width
           Physical width of display (in millimeters)

       /rdp2tcp:executable path[:arg...]
           TCP redirection

       /reconnect-cookie:base64-cookie
           Pass base64 reconnect cookie to the connection

       /redirect-prefer:FQDN|IP|NETBIOS,[...]
           Override the preferred redirection order

       /relax-order-checks, /relax-order-checks
           Do not check if a RDP order was announced during capability
           exchange, only use when connecting to a buggy server

       /restricted-admin, /restrictedAdmin
           Restricted admin mode

       /rfx
           RemoteFX

       /rfx-mode:[image|video]
           RemoteFX mode

       /scale:[100|140|180]
           Scaling factor of the display (default:100)

       /scale-desktop:percentage
           Scaling factor for desktop applications (value between 100 and 500)
           (default:100)

       /scale-device:100|140|180
           Scaling factor for app store applications (default:100)

       /sec:[rdp|tls|nla|ext]
           Force specific protocol security

       +sec-ext
           NLA extended protocol security (default:off)

       -sec-nla
           NLA protocol security (default:on)

       -sec-rdp
           RDP protocol security (default:on)

       -sec-tls
           TLS protocol security (default:on)

       /serial[:name[,path[,driver[,permissive]]]],
       /tty[:name[,path[,driver[,permissive]]]]
           Redirect serial device

       /shell:shell
           Alternate shell

       /shell-dir:dir
           Shell working directory

       /size:widthxheight or percent%[wh]
           Screen size (default:1024x768)

       /smart-sizing[:widthxheight]
           Scale remote desktop to window size

       /smartcard[:str[,str...]]
           Redirect the smartcard devices containing any of the <str> in their
           names.

       /smartcard-logon
           Activates Smartcard Logon authentication. (EXPERIMENTAL: NLA not
           supported)

       /sound[:[sys:sys,][dev:dev,][format:format,][rate:rate,][channel:channel,][latency:latency,][quality:quality]],
       /audio[:[sys:sys,][dev:dev,][format:format,][rate:rate,][channel:channel,][latency:latency,][quality:quality]]
           Audio output (sound)

       /span
           Span screen over multiple monitors

       /spn-class:service-class
           SPN authentication service class

       /ssh-agent, /ssh-agent
           SSH Agent forwarding channel

       /t:title, /title:title
           Window title

       -themes
           themes (default:on)

       /timeout:time in ms, /timeout:time in ms
           Advanced setting for high latency links: Adjust connection timeout,
           use if you encounter timeout failures with your connection
           (default:9000)

       /tls-ciphers:[netmon|ma|ciphers]
           Allowed TLS ciphers

       /tls-seclevel:level
           TLS security level - defaults to 1 (default:1)

       +enforce-tlsv1_2
           Force use of TLS1.2 for connection. Some servers have a buggy TLS
           version negotiation and might fail without this (default:off)

       -toggle-fullscreen
           Alt+Ctrl+Enter to toggle fullscreen (default:on)

       /tune:setting:value,setting:value
           [experimental] directly manipulate freerdp settings, use with
           extreme caution! (default:)

       /tune-list
           Print options allowed for /tune

       /u:[[domain\]user|user[@domain]]
           Username

       +unmap-buttons
           Let server see real physical pointer button (default:off)

       /v:server[:port]
           Server hostname

       /vc:channel[,options]
           Static virtual channel

       /version
           Print version

       /video
           Video optimized remoting channel

       /vmconnect[:vmid]
           Hyper-V console (use port 2179, disable negotiation)

       /w:width
           Width (default:1024)

       -wallpaper
           wallpaper (default:on)

       +window-drag
           full window drag (default:off)

       /window-position:xposxypos
           window position

       /wm-class:class-name
           Set the WM_CLASS hint for the window instance

       /workarea
           Use available work area

ENVIRONMENT VARIABLES
       wlog environment variable
           xfreerdp uses wLog as its log facility, you can refer to the
           corresponding man page (wlog(7)) for more informations. Arguments
           passed via the /log-level or /log-filters have precedence over the
           environment variables.

EXAMPLES
       xfreerdp connection.rdp /p:Pwd123! /f
           Connect in fullscreen mode using a stored configuration
           connection.rdp and the password Pwd123!

       xfreerdp /u:USER /size:50%h /v:rdp.contoso.com
           Connect to host rdp.contoso.com with user USER and a size of 50
           percent of the height. If width (w) is set instead of height (h)
           like /size:50%w. 50 percent of the width is used.

       xfreerdp /u:CONTOSO\\JohnDoe /p:Pwd123! /v:rdp.contoso.com
           Connect to host rdp.contoso.com with user CONTOSO\\JohnDoe and
           password Pwd123!

       xfreerdp /u:JohnDoe /p:Pwd123! /w:1366 /h:768 /v:192.168.1.100:4489
           Connect to host 192.168.1.100 on port 4489 with user JohnDoe,
           password Pwd123!. The screen width is set to 1366 and the height to
           768

       xfreerdp /u:JohnDoe /p:Pwd123!
       /vmconnect:C824F53E-95D2-46C6-9A18-23A5BB403532 /v:192.168.1.100
           Establish a connection to host 192.168.1.100 with user JohnDoe,
           password Pwd123!  and connect to Hyper-V console (use port 2179,
           disable negotiation) with VMID C824F53E-95D2-46C6-9A18-23A5BB403532

       +clipboard
           Activate clipboard redirection

       /drive:home,/home/user
           Activate drive redirection of /home/user as home drive

       /smartcard:<device>
           Activate smartcard redirection for device device

       /printer:<device>,<driver>
           Activate printer redirection for printer device using driver driver

       /serial:<device>
           Activate serial port redirection for port device

       /parallel:<device>
           Activate parallel port redirection for port device

       /sound:sys:alsa
           Activate audio output redirection using device sys:alsa

       /microphone:sys:alsa
           Activate audio input redirection using device sys:alsa

       /multimedia:sys:alsa
           Activate multimedia redirection using device sys:alsa

       /usb:id,dev:054c:0268
           Activate USB device redirection for the device identified by
           054c:0268

LINKS
       http://www.freerdp.com/

AUTHOR
       The FreeRDP Team

freerdp                           2022-11-28                       XFREERDP(1)
```

***

#### libfreerdp-client2-2 <a href="#libfreerdp-client2-2" id="libfreerdp-client2-2"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

This package contains the shared library for common client functionality.

**Installed size:** `859 KB`\
**How to install:** `sudo apt install libfreerdp-client2-2`

<details>

<summary>Dependencies:</summary>

* libasound2
* libc6
* libcups2
* libfreerdp2-2
* libpulse0
* libusb-1.0-0
* libwinpr2-2

</details>

***

#### libfreerdp-server2-2 <a href="#libfreerdp-server2-2" id="libfreerdp-server2-2"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

This package contains the shared library with common server functionality.

**Installed size:** `399 KB`\
**How to install:** `sudo apt install libfreerdp-server2-2`

<details>

<summary>Dependencies:</summary>

* libc6
* libfreerdp2-2
* libwinpr2-2

</details>

***

#### libfreerdp-shadow-subsystem2-2 <a href="#libfreerdp-shadow-subsystem2-2" id="libfreerdp-shadow-subsystem2-2"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

This package contains the shadow subsystem libraries.

**Installed size:** `169 KB`\
**How to install:** `sudo apt install libfreerdp-shadow-subsystem2-2`

<details>

<summary>Dependencies:</summary>

* libc6
* libfreerdp-shadow2-2
* libfreerdp2-2
* libpam0g
* libwinpr2-2
* libx11-6
* libxdamage1
* libxext6
* libxfixes3
* libxinerama1
* libxtst6

</details>

***

#### libfreerdp-shadow2-2 <a href="#libfreerdp-shadow2-2" id="libfreerdp-shadow2-2"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

This package contains the shadow libraries.

**Installed size:** `241 KB`\
**How to install:** `sudo apt install libfreerdp-shadow2-2`

<details>

<summary>Dependencies:</summary>

* libc6
* libfreerdp-server2-2
* libfreerdp2-2
* libwinpr-tools2-2
* libwinpr2-2

</details>

***

#### libfreerdp2-2 <a href="#libfreerdp2-2" id="libfreerdp2-2"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

This package contains the shared library with all core functionality.

**Installed size:** `1.62 MB`\
**How to install:** `sudo apt install libfreerdp2-2`

<details>

<summary>Dependencies:</summary>

* libavcodec59
* libavutil57
* libc6
* libjpeg62-turbo
* libssl3
* libswresample4
* libswscale6
* libwinpr2-2
* libx11-6
* libxkbfile1

</details>

***

#### libuwac0-0 <a href="#libuwac0-0" id="libuwac0-0"></a>

Using wayland as a client (uwac) is a library to provide common functionality for wayland clients.

This package contains the using wayland as a client library.

**Installed size:** `201 KB`\
**How to install:** `sudo apt install libuwac0-0`

<details>

<summary>Dependencies:</summary>

* libc6
* libfreerdp2-2
* libwayland-client0
* libwayland-cursor0
* libxkbcommon0

</details>

***

#### libuwac0-dev <a href="#libuwac0-dev" id="libuwac0-dev"></a>

Using wayland as a client (uwac) is a library to provide common functionality for wayland clients.

This package contains the libuwac development files

**Installed size:** `175 KB`\
**How to install:** `sudo apt install libuwac0-dev`

<details>

<summary>Dependencies:</summary>

* libuwac0-0

</details>

***

#### libwinpr-tools2-2 <a href="#libwinpr-tools2-2" id="libwinpr-tools2-2"></a>

FreeRDP is a libre client/server implementation of the Remote Desktop Protocol (RDP).

This package contains the shared library for Windows Portable Runtime utilities and tools.

**Installed size:** `172 KB`\
**How to install:** `sudo apt install libwinpr-tools2-2`

<details>

<summary>Dependencies:</summary>

* libc6
* libssl3
* libwinpr2-2

</details>

***

#### libwinpr2-2 <a href="#libwinpr2-2" id="libwinpr2-2"></a>

WinPR is a spin-off project of FreeRDP which aims at providing a portable implementation of important portions of the Windows API. Just like FreeRDP, WinPR is released under the Apache license. Unlike Wine, WinPR does not provide binary compatibility, and does not require applications to be built for Windows. Instead, WinPR provides API compatibility for applications targeting non-Windows environments. When on Windows, the original native API is being used instead of the equivalent WinPR implementation, without having to modify the code using it.

This package contains the WinPR shared library.

**Installed size:** `1.31 MB`\
**How to install:** `sudo apt install libwinpr2-2`

<details>

<summary>Dependencies:</summary>

* libc6
* libicu72
* libssl3
* libsystemd0

</details>

***

#### libwinpr2-dev <a href="#libwinpr2-dev" id="libwinpr2-dev"></a>

WinPR is a spin-off project of FreeRDP which aims at providing a portable implementation of important portions of the Windows API. Just like FreeRDP, WinPR is released under the Apache license. Unlike Wine, WinPR does not provide binary compatibility, and does not require applications to be built for Windows. Instead, WinPR provides API compatibility for applications targeting non-Windows environments. When on Windows, the original native API is being used instead of the equivalent WinPR implementation, without having to modify the code using it.

This package contains the WinPR development files.

**Installed size:** `1.09 MB`\
**How to install:** `sudo apt install libwinpr2-dev`

<details>

<summary>Dependencies:</summary>

* libssl-dev
* libwinpr-tools2-2
* libwinpr2-2

</details>

***

#### winpr-utils <a href="#winpr-utils" id="winpr-utils"></a>

WinPR is a spin-off project of FreeRDP which aims at providing a portable implementation of important portions of the Windows API. Just like FreeRDP, WinPR is released under the Apache license. Unlike Wine, WinPR does not provide binary compatibility, and does not require applications to be built for Windows. Instead, WinPR provides API compatibility for applications targeting non-Windows environments. When on Windows, the original native API is being used instead of the equivalent WinPR implementation, without having to modify the code using it.

This package contains WinPR command line utils (winpr-hash, winpr-makecert).

**Installed size:** `169 KB`\
**How to install:** `sudo apt install winpr-utils`

<details>

<summary>Dependencies:</summary>

* libc6
* libwinpr-tools2-2
* libwinpr2-2

</details>

**winpr-hash**

NTLM hashing tool

```
:~# winpr-hash --help
missing username or password

winpr-hash: NTLM hashing tool
Usage: winpr-hash -u <username> -p <password> [-d <domain>] [-f <_default_,sam>] [-v <_1_,2>]
```

***

**winpr-makecert**

A tool to create X.509 certificates.

```
:~# winpr-makecert -h
Usage: winpr-makecert [options] [output file]

    -rdp                 	Unsupported - Generate certificate with required options for RDP usage.
    -silent              	Silently generate certificate without verbose output.
    -live                	Generate certificate live in memory when used as a library.
    -format <crt|pem|pfx>	Specify certificate file format
    -path <path>         	Specify certificate file output path
    -p <password>        	Specify certificate export password
    -n <name>            	Specifies the subject's certificate name. This name must conform to the X.500 standard. The simplest method is to specify the name in double quotes, preceded by CN=; for example, -n "CN=myName".
    -pe                  	Unsupported - Marks the generated private key as exportable. This allows the private key to be included in the certificate.
    -sk <keyname>        	Unsupported - Specifies the subject's key container location, which contains the private key. If a key container does not exist, it will be created.
    -sr <location>       	Unsupported - Specifies the subject's certificate store location. location can be either currentuser (the default) or localmachine.
    -ss <store>          	Unsupported - Specifies the subject's certificate store name that stores the output certificate.
    -# <number>          	Specifies a serial number from 1 to 2,147,483,647. The default is a unique value generated by Makecert.exe.
    -$ <authority>       	Unsupported - Specifies the signing authority of the certificate, which must be set to either commercial (for certificates used by commercial software publishers) or individual (for certificates used by individual software publishers).
    -a <algorithm>       	Specifies the signature algorithm. algorithm must be md5, sha1, sha256 (the default), sha384, or sha512.
    -b <mm/dd/yyyy>      	Unsupported - Specifies the start of the validity period. Defaults to the current date.
    -crl                 	Unsupported - Generates a certificate relocation list (CRL) instead of a certificate.
    -cy <certType>       	Unsupported - Specifies the certificate type. Valid values are end for end-entity and authority for certification authority.
    -e <mm/dd/yyyy>      	Unsupported - Specifies the end of the validity period. Defaults to 12/31/2039 11:59:59 GMT.
    -eku <oid[,oid…]>  	Unsupported - Inserts a list of comma-separated, enhanced key usage object identifiers (OIDs) into the certificate.
    -h <number>          	Unsupported - Specifies the maximum height of the tree below this certificate.
    -ic <file>           	Unsupported - Specifies the issuer's certificate file.
    -ik <keyName>        	Unsupported - Specifies the issuer's key container name.
    -iky <keyType>       	Unsupported - Specifies the issuer's key type, which must be one of the following: signature (which indicates that the key is used for a digital signature), exchange (which indicates that the key is used for key encryption and key exchange), or an integer that represents a provider type. By default, you can pass 1 for an exchange key or 2 for a signature key.
    -in <name>           	Unsupported - Specifies the issuer's certificate common name.
    -ip <provider>       	Unsupported - Specifies the issuer's CryptoAPI provider name. For information about the CryptoAPI provider name, see the –sp option.
    -ir <location>       	Unsupported - Specifies the location of the issuer's certificate store. location can be either currentuser (the default) or localmachine.
    -is <store>          	Unsupported - Specifies the issuer's certificate store name.
    -iv <pvkFile>        	Unsupported - Specifies the issuer's .pvk private key file.
    -iy <type>           	Unsupported - Specifies the issuer's CryptoAPI provider type. For information about the CryptoAPI provider type, see the –sy option.
    -l <link>            	Unsupported - Links to policy information (for example, to a URL).
    -len <number>        	Specifies the generated key length, in bits.
    -m <number>          	Specifies the duration, in months, of the certificate validity period.
    -y <number>          	Specifies the duration, in years, of the certificate validity period.
    -nscp                	Unsupported - Includes the Netscape client-authorization extension.
    -r                   	Unsupported - Creates a self-signed certificate.
    -sc <file>           	Unsupported - Specifies the subject's certificate file.
    -sky <keyType>       	Unsupported - Specifies the subject's key type, which must be one of the following: signature (which indicates that the key is used for a digital signature), exchange (which indicates that the key is used for key encryption and key exchange), or an integer that represents a provider type. By default, you can pass 1 for an exchange key or 2 for a signature key.
    -sp <provider>       	Unsupported - Specifies the subject's CryptoAPI provider name, which must be defined in the registry subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\Defaults\Provider. If both –sp and –sy are present, the type of the CryptoAPI provider must correspond to the Type value of the provider's subkey.
    -sv <pvkFile>        	Unsupported - Specifies the subject's .pvk private key file. The file is created if none exists.
    -sy <type>           	Unsupported - Specifies the subject's CryptoAPI provider type, which must be defined in the registry subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\Defaults\Provider Types. If both –sy and –sp are present, the name of the CryptoAPI provider must correspond to the Name value of the provider type subkey.
    -tbs <file>          	Unsupported - Specifies the certificate or CRL file to be signed.
    -?                   	print help
    -!                   	print extended help
```

***

Updated on: 2023-Mar-08\


***
