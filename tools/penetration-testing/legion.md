---
description: >-
  Legion is an open-source, customizable network penetration testing framework
  by GoVanguard, based on Sparta, aiding in discovery and exploitation of
  information systems.
---

# 🎩 legion

Legion, a fork of SECFORCE's Sparta, is an open source, easy-to-use, super-extensible, and semi-automated network penetration testing framework that aids in discovery, reconnaissance, and exploitation of information systems. [Legion](https://govanguard.com/legion) is developed and maintained by [GoVanguard](https://govanguard.com/). More information about Legion, including the [roadmap](https://govanguard.com/legion), can be found on its project page at [https://GoVanguard.com/legion](https://govanguard.com/legion).

If you are interested in contributing to Legion, join our [Legion Keybase Team](https://keybase.io/team/govanguard.dev.legion).

### Fix NMAP 7.92 Sefgaults under Kali

Install NMAP 7.93 using the following:

```
sudo apt install snapd -y
sudo systemctl enable --now snapd.apparmor
sudo systemctl start snapd
sudo snap install nmap
sudo mv /usr/bin/nmap /usr/bin/nmap-7.92
sudo ln -s /snap/bin/nmap /usr/bin/nmap
```

Then verify the version is 7.93 with: `nmap -v`

Update the apparmor profile: `vi /var/lib/snapd/apparmor/profiles/snap.nmap.nmap`

Goto line 300, create new line and add in:

```
owner @{HOME}/.local/share/legion/tmp/** rw,
/etc/ssl/kali.cnf r,
```

Reboot

### 🍿 Features

* Automatic recon and scanning with NMAP, whataweb, nikto, Vulners, Hydra, SMBenum, dirbuster, sslyzer, webslayer and more (with almost 100 auto-scheduled scripts).
* Easy to use graphical interface with rich context menus and panels that allow pentesters to quickly find and exploit attack vectors on hosts.
* Modular functionality allows users to easily customize Legion and automatically call their own scripts/tools.
* Multiple custom scan configurations ideal for testing different environments of various size and complexity.
* Highly customizable stage scanning for ninja-like IPS evasion.
* Automatic detection of CPEs (Common Platform Enumeration) and CVEs (Common Vulnerabilities and Exposures).
* Ties CVEs to Exploits as detailed in Exploit-Database.
* Realtime auto-saving of project results and tasks.

#### Notable changes from Sparta

* Refactored from Python 2.7 to Python 3.6 and the elimination of deprecated and unmaintained libraries.
* Upgraded to PyQT5, increased responsiveness, less buggy, more intuitive GUI that includes features like:
  * Task completion estimates
  * 1-Click scan lists of ips, hostnames and CIDR subnets
  * Ability to purge results, rescan hosts and delete hosts
  * Granular NMAP scanning options
* Support for hostname resolution and scanning of vhosts/sni hosts.
* Revise process queuing and execution routines for increased app reliability and performance.
* Simplification of installation with dependency resolution and installation routines.
* Realtime project auto-saving so in the event some goes wrong, you will not lose any progress!
* Docker container deployment option.
* Supported by a highly active development team.

#### Demo (GIF)

[![](https://camo.githubusercontent.com/d9fb92079473941bf72a41c7084b0044635a9f070c5ca3489b825e99ca7da81e/68747470733a2f2f676f76616e67756172642e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031392f30322f4c6567696f6e44656d6f2e676966)](https://camo.githubusercontent.com/d9fb92079473941bf72a41c7084b0044635a9f070c5ca3489b825e99ca7da81e/68747470733a2f2f676f76616e67756172642e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031392f30322f4c6567696f6e44656d6f2e676966)

### 🌉 Supported Distributions

#### Docker runIt script support

RunIt script (`docker/runIt.sh`) supports:

* Ubuntu 18
* Fedora 30
* ParrotOS
* Kali Linux

It is possible to run the docker image on any Linux distribution, however, different distributions have different hoops to jump through to get a docker app to be able to connect to the X server. Everyone is welcome to try to figure those hoops out and create a PR for runIt.

#### Traditional installation support

We can only promise correct operation on **Ubuntu 18** using the traditional installation at this time. While it should work on ParrotOS, Kali, and others, until we have Legion packaged and placed into the repos for each of these distros, it is musical chairs in regard to platform updates changing and breaking dependencies.

### 💻 Installation

Two installation methods available:

* [Docker method](https://github.com/GoVanguard/legion/blob/master/README.md#traditional-installation-method)
* [Traditional installation method](https://github.com/GoVanguard/legion/blob/master/README.md#traditional-installation-method)

It is **preferable** to use the Docker method over a traditional installation. This is because of all the dependency requirements and the complications that occur in environments which differ from a clean, non-default installation.

> NOTE: Docker versions of Legion are _unlikely_ to work when run as root or under a root X!

#### Docker method

Docker method includes support for various environments, choose the one that works for you.

* [Linux with local X11](https://github.com/GoVanguard/legion/blob/master/README.md#linux-with-local-x11)
* [Linux with remote X11](https://github.com/GoVanguard/legion/blob/master/README.md#linux-with-remote-x11)
* [Windows under WSL](https://github.com/GoVanguard/legion/blob/master/README.md#windows-under-wsl-using-xming-and-docker-desktop)
* [⚠️ Windows without WSL](https://github.com/GoVanguard/legion/blob/master/README.md#windows-using-xming-and-docker-desktop-without-wsl)
* [⚠️ OSX using XQuartz](https://github.com/GoVanguard/legion/blob/master/README.md#osx-using-xquartz)

**Linux with local X11**

Assumes **Docker** and **X11** are installed and set up (including running Docker commands as a non-root user).

It is critical to follow all the instructions for running as a non-root user. Skipping any of them will result in complications getting Docker to communicate with the X server.

See detailed instructions to set up Docker [here](https://github.com/GoVanguard/legion/blob/master/README.md#configuring-docker) and enable running containers as non-root users and granting Docker group SSH rights [here](https://github.com/GoVanguard/legion/blob/master/README.md#setup-docker-to-allow-non-root-users).

Within Terminal:

```
git clone https://github.com/GoVanguard/legion.git
cd legion/docker
chmod +x runIt.sh
./runIt.sh
```

**Linux with remote X11**

Assumes **Docker** and **X11** are installed and set up.

Replace `X.X.X.X` with the IP address of the remote running X11.

Within Terminal:

```
git clone https://github.com/GoVanguard/legion.git
cd legion/docker
chmod +x runIt.sh
./runIt.sh X.X.X.X
```

**Windows under WSL using Xming and Docker Desktop**

Assumes:

* Xming is installed in Windows.
* Docker Desktop is installed in Windows
* Docker Desktop is running in Linux containers mode
* Docker Desktop is connected to WSL.

See detailed Docker instructions [here](https://github.com/GoVanguard/legion/blob/master/README.md#setup-hyper-v-docker-desktop-xming-and-wsl)

Replace `X.X.X.X` with the IP address with which Xming has registered itself. Right click Xming in system tray -> View log and see IP next to "XdmcpRegisterConnection: newAddress"

Within Terminal:

```
git clone https://github.com/GoVanguard/legion.git
cd legion/docker
sudo chmod +x runIt.sh
sudo ./runIt.sh X.X.X.X
```

**Windows using Xming and Docker Desktop without WSL**

Why? Don't do this. :)

**OSX using XQuartz**

Not yet in `runIt.sh` script. Possible to set up using `socat`. See [instructions here](https://kartoza.com/en/blog/how-to-run-a-linux-gui-application-on-osx-using-docker/)

**Configuring Docker**

**Setting up Docker on Linux**

To install Docker components typically needed and add set up the environment for Docker, under a term, run:

```
sudo apt-get update
sudo apt-get install -y docker.io python3-pip -y
sudo groupadd docker
pip install --user docker-compose
```

**Setup Docker to allow non-root users**

To enable non-root users to run Docker commands, under a term, run:

```
sudo usermod -aG docker $USER
sudo chmod 666 /var/run/docker.sock
sudo xhost +local:docker
```

**Setup Hyper-V, Docker Desktop, Xming and WSL**

The order is important for port reservation reasons. If you have WSL, HyperV, or Docker Desktop installed then please uninstall those features before proceeding.

* Cortana / Search -> cmd -> Right click -> Run as Administrator
*   To reserve the Docker port, under CMD, run:

    ```
    netsh int ipv4 add excludedportrange protocol=tcp startport=2375 numberofports=1
    ```

    * This will likely fail if you have Hyper-V already enabled or Docker Desktop installed
*   To install Hyper-V, under CMD, run:

    ```
    dism.exe /Online /Enable-Feature:Microsoft-Hyper-V /All
    ```
* Reboot
* Cortana / Search -> cmd -> Right click -> Run as Administrator
*   To install WSL, under CMD, run:

    ```
    dism.exe /Online /Enable-Feature /FeatureName:Microsoft-Windows-Subsystem-Linux
    ```
* Reboot
* Download from [https://hub.docker.com/editions/community/docker-ce-desktop-windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows) (Free account required)
* Run installer
* Optionally input your Docker Hub login
* Right click Docker Desktop in system tray -> Switch to Linux containers
  * If it says Switch to Windows containers then skip this step, it's already using Linux containers
* Right click Docker Desktop in system tray -> Settings
* General -> Expose on localhost without TLS
* Download [https://sourceforge.net/projects/xming/files/Xming/6.9.0.31/Xming-6-9-0-31-setup.exe/download](https://sourceforge.net/projects/xming/files/Xming/6.9.0.31/Xming-6-9-0-31-setup.exe/download)
* Run installer and select multi window mode
* Open Microsoft Store
* Install Kali, Ubuntu or one of the other WSL Linux Distributions
* Open the distribution, let it bootstrap and fill in the user creation details
*   To install Docker components typically needed and add set up the environment for Docker redirection, under the WSL window, run:

    ```
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    sudo apt-get update
    sudo apt-get install -y docker-ce python-pip -y
    sudo apt autoremove
    sudo usermod -aG docker $USER
    pip install --user docker-compose
    echo "export DOCKER_HOST=tcp://localhost:2375" >> ~/.bashrc && source ~/.bashrc
    ```
*   Test Docker is reachable with:

    ```
    docker images
    ```

#### Traditional installation method

> Please use the Docker image where possible! It's becoming very difficult to support all the various platforms and their own quirks.

Assumes Ubuntu, Kali or Parrot Linux is being used with **Python 3.6** installed.

Within Terminal:

```
git clone https://github.com/GoVanguard/legion.git
cd legion
sudo chmod +x startLegion.sh
sudo ./startLegion.sh
```

### 🏗 Development

#### Executing test cases

To run all test cases, execute the following in root directory:

```
python -m unittest
```

#### Modifying Configuration

The configuration of selected ports and associated terminal actions can be easily modified by editing the legion.conf file.

> \[StagedNmapSettings] defines what ports will be scanned in sequential order as well as any NSE scripts that will be called.
>
> \[SchedulerSettings] defines what actions will occur automatically based upon port scan results.

```
sudoedit /root/.local/share/legion/legion.conf
```

### ⚖️ License

Legion is licensed under the GNU General Public License v3.0. Take a look at the [LICENSE](https://github.com/GoVanguard/legion/blob/master/LICENSE) for more information.

### ⭐️ Attribution

* Refactored Python 3.6+ codebase, added feature set and ongoing development of Legion is credited to [GoVanguard](https://govanguard.com/)
* The initial Sparta Python 2.7 codebase and application design is credited SECFORCE.
* Several additional PortActions, PortTerminalActions and SchedulerSettings are credited to batmancrew.
* The nmap XML output parsing engine was largely based on code by yunshu, modified by ketchup and modified SECFORCE.
* ms08-067\_check script used by `smbenum.sh` is credited to Bernardo Damele A.G.
* Legion relies heavily on nmap, hydra, python, PyQt, SQLAlchemy and many other tools and technologies, so we would like to thank all of the people involved in the creation of those.
* Special thanks to Dmitriy Dubson for his continued contributions to the project!

### Packages and Binaries:

#### legion <a href="#legion" id="legion"></a>

This package contains an open source, easy-to-use, super-extensible and semi-automated network penetration testing tool that aids in discovery, reconnaissance and exploitation of information systems.

Legion is a fork of SECFORCE’s Sparta.

**Installed size:** `3.12 MB`\
**How to install:** `sudo apt install legion`

<details>

<summary>Dependencies:</summary>

* cutycapt
* figlet
* finger
* hping3
* hydra
* ldap-utils
* medusa
* nbtscan
* nfs-common
* nikto
* nmap
* python3
* python3-aiohttp
* python3-aioredis
* python3-apscheduler
* python3-colorama
* python3-impacket
* python3-pandas
* python3-pyexploitdb
* python3-pyfiglet
* python3-pyqt5
* python3-pyshodan
* python3-quamash
* python3-service-identity
* python3-six
* python3-sqlalchemy
* python3-termcolor
* rpcbind
* rwho
* smbclient
* sparta-scripts
* sqlmap
* sslscan
* wapiti
* whatweb
* x11-apps
* xauth
* xsltproc
* xvfb

</details>

**legion**

```
:~# legion -h
 _     _____ ____ ___ ___  _   _ 
| |   | ____/ ___|_ _/ _ \| \ | |
| |   |  _|| |  _ | | | | |  \| |
| |___| |__| |_| || | |_| | |\  |
|_____|_____\____|___\___/|_| \_|
                                 

```

***

Updated on: 2022-Nov-16\


***
