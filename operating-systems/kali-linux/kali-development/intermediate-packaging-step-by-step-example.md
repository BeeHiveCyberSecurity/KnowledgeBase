# Intermediate packaging step-by-step example

### Photon <a href="#photon" id="photon"></a>

[Photon](https://github.com/s0md3v/Photon) is a **Python3** application with multiple dependencies. This makes it a more interesting package than [Instaloader](broken-reference) as potentially more work is involved.

[Photon Code Overview](broken-reference)

Like before with [Instaloader](broken-reference) we will first take a look at [their GitHub page](https://github.com/s0md3v/photon) to see what information we can acquire. In this case we notice the following:

* There is no `setup.py`, however there is a `requirements.txt` ([file](https://github.com/s0md3v/Photon/blob/master/requirements.txt))
* The [license is GPL-3](https://github.com/s0md3v/Photon/blob/master/LICENSE.md)
* It has [a release](https://github.com/s0md3v/photon/releases)

Because there is no `setup.py` file we will have to do more work during the packaging process, and do some things differently than with [Instaloader](broken-reference).

[Setting Up Environment](broken-reference)

We assume we have already followed our [documentation on setting up a packing environment](broken-reference).

Let’s set up our directories now for this package:

```
:~$ mkdir -p ~/kali/packages/photon/ ~/kali/upstream
:~$
```

[Downloading Tag Release](broken-reference)

As this package has a tag release like [Instaloader](broken-reference), we will follow the same process. We go to Photon’s [GitHub’s release page](https://github.com/s0md3v/photon/releases) and see the latest release is version **1.3.0**. We then **download it** with the filename format of `[name]_[version].orig.tar.gz`:

```
:~$ wget https://github.com/s0md3v/photon/archive/v1.3.0.tar.gz -O ~/kali/upstream/photon_1.3.0.orig.tar.gz
:~$
```

[Creating Package Source Code](broken-reference)

We can now go to the working directory for the process now that the prerequisites are done:

```
:~$ cd ~/kali/packages/photon/
:~/kali/packages/photon$
```

We then can make it into an **empty Git repository**:

```
:~/kali/packages/photon$ git init
Initialized empty Git repository in /home/kali/packages/photon/.git/
:~/kali/packages/photon$
```

We can now **import** the `.tar.gz` we previously downloaded into the empty Git repository we just created. When prompted, we remember to accept the default values:

```
:~/kali/packages/photon$ gbp import-orig ~/kali/upstream/photon_1.3.0.orig.tar.gz
What will be the source package name? [photon]
What is the upstream version? [1.3.0]
gbp:info: Importing '/home/kali/kali/upstream/photon_1.3.0.orig.tar.gz' to branch 'upstream'...
gbp:info: Source package is photon
gbp:info: Upstream version is 1.3.0
gbp:info: Successfully imported version 1.3.0 of /home/kali/kali/upstream/photon_1.3.0.orig.tar.gz
:~/kali/packages/photon$
```

We remember to **change the default branch**, from `master` to `kali/master` (as `master` is for upstream development), then **delete the old branch**. _We also run a quick `git branch -v` to visually see the change:_

```
:~/kali/packages/photon$ git checkout -b kali/master
Switched to a new branch 'kali/master'
:~/kali/packages/photon$
:~/kali/packages/photon$ git branch -D master
Deleted branch master (was 95b196b).
:~/kali/packages/photon$
:~/kali/packages/photon$ git branch -v
* kali/master  95b196b New upstream version 4.4.4
  pristine-tar 7e90962 pristine-tar data for photon_1.3.0.orig.tar.gz
  upstream     95b196b New upstream version 4.4.4
:~/kali/packages/photon$
```

We can now **generate the `debian/` folder** and related files. We will again go with **S**ingle for this package. We will manually specify the downloaded file _(as it is not located in `../`)_, and also the package name to use in the template:

```
:~/kali/packages/photon$ dh_make --file ~/kali/upstream/photon_1.3.0.orig.tar.gz -p photon_1.3.0
Type of package: (single, indep, library, python)
[s/i/l/p]?
Maintainer Name     : Joseph O'Gorman
Email-Address       : 
Date                : Mon, 13 Jul 2020 17:28:51 -0400
Package Name        : photon
Version             : 1.3.0
License             : blank
Package Type        : single
Are the details correct? [Y/n/q]
Skipping creating ../photon_1.3.0.orig.tar.gz because it already exists
Currently there is not top level Makefile. This may require additional tuning
Done. Please edit the files in the debian/ subdirectory now.
:~/kali/packages/photon$
:~/kali/packages/photon$ rm debian/*.docs debian/README* debian/*.ex debian/*.EX
:~/kali/packages/photon$
```

As a quick refresher of what each of these files are for:

* `debian/changelog` - tracks **when the package gets an update** (including why and who by). This is responsible for the **package version**
* `debian/control` - is the **metadata for the package** (often seen with `apt`)
* `debian/copyright` - what is under **what license**. The package can be under something different to the work we have put in to create the package
* `debian/rules` - **how to build** the software and turn it into a package
* `debian/source/format` - is the **source package** format

At this point, we have the base packaging files in place, and it feels like a good idea to commit before starting some real work:

```
:~/kali/packages/photon$ git add debian/
:~/kali/packages/photon$
:~/kali/packages/photon$ git commit -m "Initial packaging files"
[kali/master 52042da] Initial packaging files
 5 files changed, 93 insertions(+)
 create mode 100644 debian/changelog
 create mode 100644 debian/control
 create mode 100644 debian/copyright
 create mode 100755 debian/rules
 create mode 100644 debian/source/format
:~/kali/packages/photon$
```

We now need to edit each one to make sure the information is accurate. We can use what we found on [GitHub](https://github.com/s0md3v/photon) to supply the correct info into the `debian/` files:

* License
* Dependencies
* Maintainers
* Description

[Collecting Information](broken-reference)[License/Maintainers](broken-reference)

This package, like [Instaloader](broken-reference), is very straightforward and [**GitHub**](https://github.com/s0md3v/photon) **has already detected the** [**license**](https://github.com/s0md3v/photon/blob/master/LICENSE.md) as [**GPL-3**](https://www.gnu.org/licenses/gpl-3.0.html).

For GPL-3 licenses we do not have to copy the entirety as-is in the upstream license file. If we look at `/usr/share/common-licenses/` we can see that there are multiple licenses in their entirety already available locally. As we can see from [GPL-3’s page from Debian](https://ftp-master.debian.org/licenses/good/gpl3/) we can use a shortened down version of the license that will be acceptable.

Unfortunately, when we look at the license file from upstream we do not see any contact information or names. We will have to look elsewhere for it.

If we look through the [**README.me**](https://github.com/s0md3v/Photon/blob/master/README.md) [on Photon’s GitHub page](https://github.com/s0md3v/Photon/blob/master/README.md), we can see that `s0md3v` appears to be the sole maintainer as his [Twitter](https://twitter.com/s0md3v) is linked however no other maintainers are seen. If we look at [s0md3v’s GitHub profile page](https://github.com/s0md3v), we notice that an email is shown _(if we are logged in)_! With this, we have the **maintainer name** and **email address** we can use to continue.

[Dependencies/Maintainers](broken-reference)

We now need to find out **what dependencies** are needed for this tool to work. Fortunately, we have a `requirements.txt` file that we spotted earlier. Looking at this we can see **four** dependencies needed:

```
:~/kali/packages/photon$ cat requirements.txt
requests
requests[socks]
urllib3
tld
:~/kali/packages/photon$
```

We now need to find the proper name in `apt` to make sure that we have everything for when we edit the `debian/control` file later.

From [Instaloader](broken-reference), we already know that **requests** will be available with `python3-requests`. However, **requests\[socks]** will not so we have to find a way to install socks. If we search for `python3-requests`, we can see that there is no result that includes any mention of socks:

```
:~/kali/packages/photon$ apt-cache search python3-requests | grep -i socks
:~/kali/packages/photon$
:~/kali/packages/photon$ apt-cache search python3-requests
beancount - Double-entry accounting from text files
python-requests-toolbelt-doc - Utility belt for python3-requests (documentation)
python3-awsauth - AWS authentication for Amazon S3 for the python3-requests module
python3-beancount - Double-entry accounting from text files - Python module
python3-httmock - Mocking library for python3-requests
python3-proxmoxer - Python Wrapper for the Proxmox 2.x API (HTTP and SSH) (Python 3)
python3-requests - elegant and simple HTTP library for Python3, built for human beings
python3-requests-cache - persistent cache for requests library (Python 3)
python3-requests-file - File transport adapter for Requests - Python 3.X
python3-requests-futures - library for asynchronous HTTP requests (Python 3)
python3-requests-kerberos - Kerberos/GSSAPI authentication handler for python-requests - Python 3.x
python3-requests-mock - mock out responses from the requests package - Python 3.x
python3-requests-ntlm - Adds support for NTLM authentication to the requests library
python3-requests-oauthlib - module providing OAuthlib auth support for requests (Python 3)
python3-requests-toolbelt - Utility belt for advanced users of python3-requests
python3-requests-unixsocket - Use requests to talk HTTP via a UNIX domain socket - Python 3.x
python3-requestsexceptions - import exceptions from bundled packages in requests. - Python 3.x
units - converts between different systems of units
:~/kali/packages/photon$
```

If we broaden our search and utilize `grep` we are able to find what we need!

```
:~/kali/packages/photon$ apt-cache search python3 | grep -i socks
python3-aiohttp-socks - SOCKS proxy connector for aiohttp (Python 3)
python3-asysocks - Socks5 / Socks4 client and server library (Python 3)
python3-socks - Python 3 SOCKS client module
python3-socksipychain - Python SOCKS/HTTP/SSL chaining proxy module
:~/kali/packages/photon$
```

Looks like `python3-socks` is our **second dependency**. However, we can make sure that this is indeed the correct package:

* We will first go to the [PyPI page for requests](https://pypi.org/project/requests/) to find the proper upstream source.
* Next we can find the [setup.py file](https://github.com/psf/requests/blob/master/setup.py) and look for the [line with socks](https://github.com/psf/requests/blob/master/setup.py#L106). Here we can see that PySocks is the PyPI module name.
* Again we can find the upstream source from the [PyPI page for PySocks](https://pypi.org/project/PySocks/)
* We can finally compare the upstream source from PySocks to the homepage provided with python3-socks and see that they match:

```
:~/kali/packages/photon$ apt-cache show python3-socks | grep Homepage
Homepage: https://github.com/Anorov/PySocks
:~/kali/packages/photon$
```

Keeping this in mind, lets find **urllib3** and **tld**:

```
:~/kali/packages/photon$ apt-cache search python3 | grep urllib3
python3-urllib3 - HTTP library with thread-safe connection pooling for Python3
:~/kali/packages/photon$
:~/kali/packages/photon$ apt-cache search python3 | grep tld
python3-tld - Extract the top level domain (TLD) from a given URL (Python 3)
python3-tldextract - Python library for separating TLDs
:~/kali/packages/photon$
```

There are the other two! We now have all four dependencies figured out (`python3-requests`,`python3-socks`,`python3-urllib3` & `python3-tld`), and can move forward.

[Maintainers](broken-reference)

Like [Instaloader](broken-reference), while doing the other parts we have discovered the authors and maintainers of the software, so we don’t need to do anything extra for this.

[Description](broken-reference)

Similarly to [Instaloader](broken-reference) we will pull the descriptions from the [GitHub page](https://github.com/s0md3v/photon). Remember we need two description values, a short one and a long one.

The first description we create is the **short description**. For this one, we will take the summary from the about section of the GitHub and expand “OSINT” to be “Open Source INTelligence” for anyone who would not know what “OSINT” means.

For the **long description** we will repeat the about description, and then utilize the explanation under **Data Extraction** from the README. The reason we do this is because the long description cannot start with the name of the package, so we will repeat the short description and modify it to provide further context. However, for now this is something to remember until we edit the `debian/control` file.

[Editing Package Source Code](broken-reference)

Now that we have that information copied down, we can start to populate the files in the `debian/` folder we created with `dh_make`.

[Changelog](broken-reference)

Here we will need to alter:

* **distribution** from `unstable` to `kali-dev`
  * unstable is the development distribution for Debian, kali-dev is the one we use in Kali.
* **version** (from `1.3.0-1` to `1.3.0-0kali1`)
  * The format is `[softwareversion]-0kali[release]`. We put `0kali` in case this package makes it into Debian, it avoids conflicting versions and ensures proper upgrade to the Debian version.
* The **log entry** - We keep it simple with `Initial release`

```
:~/kali/packages/photon$ vim debian/changelog
:~/kali/packages/photon$
:~/kali/packages/photon$ cat debian/changelog
photon (1.3.0-0kali1) kali-dev; urgency=medium

  * Initial release

 -- Joseph O'Gorman <>  Mon, 13 Jul 2020 17:28:51 -0400
 :~/kali/packages/photon$
```

[Control](broken-reference)

Most of this we have now figured out from [Instaloader](broken-reference), so it should make it easier to fill in. We supply the values that we found from our information gathering and get the following:

```
:~/kali/packages/photon$ vim debian/control
:~/kali/packages/photon$
:~/kali/packages/photon$ cat debian/control
Source: photon
Section: net
Priority: optional
Maintainer: Kali Developers <>
Uploaders: Joseph O'Gorman <>
Build-Depends: debhelper-compat (= 12),
               dh-python,
               python3-all,
               python3-requests,
               python3-socks,
               python3-tld,
               python3-urllib3,
Standards-Version: 4.5.0
Homepage: https://github.com/s0md3v/Photon
Vcs-Browser: https://gitlab.com/kalilinux/packages/photon
Vcs-Git: https://gitlab.com/kalilinux/packages/photon.git

Package: photon
Architecture: all
Depends: ${python3:Depends},
         ${misc:Depends},
         python3-requests,
         python3-socks,
         python3-tld,
         python3-urllib3,
Description: Incredibly fast crawler designed for open source intelligence
 This package includes a fast and flexible crawler designed for open source
 intelligence (OSINT).
 .
 Photon can extract the following data while crawling:
  - URLs (in-scope & out-of-scope)
  - URLs with parameters (example.com/gallery.php?id=2)
  - Intel (emails, social media accounts, amazon buckets etc.)
  - Files (pdf, png, xml etc.)
  - Secret keys (auth/API keys & hashes)
  - JavaScript files & Endpoints present in them
  - Strings matching custom regex pattern
  - Subdomains & DNS related data
 .
 The extracted information is saved in an organized manner or can be exported
 as json.
:~/kali/packages/photon$
```

In `Build-Depends` now, this is a Python3 Package so we need to add in:

* **dh-python**
* **python3-all**
* **python3-requests**
* **python3-socks**
* **python3-tld**
* **python3-urllib3**

For this package however, as we do not have a **setup.py** file, we will make a small change compared to [Instaloader](broken-reference). This change is that we do not include the build dependency of `python3-setuptools`. We will still include `python3-all`, and that is for a separate reason. We will also include all of the dependencies that are for the package. We do this to ensure that a test suite can be ran if there is one.

As stated previously, `python3-all` is still included. This is due to its reliance on a python module that requires compiled binary extensions. These can be found by doing the following:

```
:~/kali/packages/photon$ find /usr/lib/python3.8/ -name '*.so'
/usr/lib/python3.8/lib-dynload/_codecs_hk.cpython-38-x86_64-linux-gnu.so
[...]
/usr/lib/python3.8/dist-packages/cryptography/hazmat/bindings/_openssl.abi3.so
/usr/lib/python3.8/config-3.8-x86_64-linux-gnu/libpython3.8.so
:~/kali/packages/photon$
```

This can be a bit overwhelming, and at first glance does not give too much helpful information. We can use this to learn if we are going to have any dependency that will eventually call in one of the previous files. To do this we do the following:

```
:~/kali/packages/photon$ apt depends python3-urllib3
python3-urllib3
  Depends: <python3:any>
    python3
  Depends: python3-six
  Recommends: ca-certificates
  Suggests: python3-cryptography
  Suggests: python3-idna
  Suggests: python3-openssl
  Suggests: python3-socks
:~/kali/packages/photon$
```

As we can see, `python3-urllib3` suggests the python3 module **cryptography**, which we can tell from the previous list will have us require `python3-all`. This is sufficient to include `python3-all`.

In `Depends` we change **${shlibs:Depends}** to **${python3:Depends}** like before and add in the `apt` names that we found previously (`python3-requests`, `python3-socks`, `python3-tld` & `python3-urllib3`).

[Copyright](broken-reference)

We already have figured out the **copyright license** description we will use, and have the `Upstream-Contact` information, so we can easily populate this file:

```
:~/kali/packages/photon$ vim debian/copyright
:~/kali/packages/photon$
:~/kali/packages/photon$ cat debian/copyright
Format: https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/
Upstream-Name: photon
Upstream-Contact: s0md3v <>
Source: https://gihub.com/s0md3v/Photon

Files: *
Copyright: 2020 s0md3v <>
License: GPL-3+

Files: debian/*
Copyright: 2020 Joseph O'Gorman <>
License: GPL-3+

License: GPL-3+
 This package is free software; you can redistribute it and/or modify
 it under the terms of the GNU General Public License as published by
 the Free Software Foundation; either version 3 of the License, or
 (at your option) any later version.
 .
 This package is distributed in the hope that it will be useful,
 but WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 GNU General Public License for more details.
 .
 You should have received a copy of the GNU General Public License
 along with this program. If not, see <https://www.gnu.org/licenses/>
 .
 On Debian systems, the complete text of the GNU General
 Public License version 3 can be found in "/usr/share/common-licenses/GPL-3".
:~/kali/packages/photon$
```

[Rules](broken-reference)

This rules file will look similar to [Instaloader](broken-reference)’s, with **how to install**, however there is one key difference that will change significantly how the package is built. As there is no `setup.py`, we **do not need** to set the `pybuild` build system:

```
:~/kali/packages/photon$ vim debian/rules
:~/kali/packages/photon$
:~/kali/packages/photon$ cat debian/rules
#!/usr/bin/make -f
#export DH_VERBOSE = 1
export PYBUILD_NAME=photon

%:
	dh  --with python3
:~/kali/packages/photon$
```

Beware that the “dh” line needs to be indented by a single tabulation character.

[Watch](broken-reference)

This watch file is easier than [Instaloader](broken-reference)’s in that we do not have to worry about version mangling. We can do a straightforward watch file like so:

```
:~/kali/packages/photon$ vim debian/watch
:~/kali/packages/photon$
:~/kali/packages/photon$ cat debian/watch
version=4
opts=filenamemangle=s/.+\/v?(\d\S+)\.tar\.gz/photon-$1\.tar\.gz/ \
  https://github.com/s0md3v/photon/tags .*/v?(\d\S+)\.tar\.gz
:~/kali/packages/photon$
```

[.Install & Helper-Scripts](broken-reference)

The `.install` and helper-script file for this package are very straightforward.

We first will create the helper-script:

```
:~/kali/packages/photon$ mkdir -p debian/helper-script/
:~/kali/packages/photon$
:~/kali/packages/photon$ vim debian/helper-script/photon
:~/kali/packages/photon$
:~/kali/packages/photon$ cat debian/helper-script/photon
#!/bin/sh
exec python3 /usr/share/photon/photon.py ""
:~/kali/packages/photon$
```

We can now create the install file. For this install file, we ensure that we copy over the files that `photon.py` will use:

```
:~/kali/packages/photon$ vim debian/photon.install
:~/kali/packages/photon$
:~/kali/packages/photon$ cat debian/photon.install
core usr/share/photon/
plugins usr/share/photon/
photon.py usr/share/photon/
debian/helper-script/photon usr/bin/
:~/kali/packages/photon$
```

Now we can leave this package here. It is a **working package**, and everything appears to be correct when we build it: `gbp buildpackage --git-builder=sbuild --git-export=WC`

However, we want this package to be the best possible package it can be! If we take a look at the `photon.py` file we can see that it has the ability to update built in. This is something that we should **patch out** [using gbp pq](https://manpages.debian.org/unstable/git-buildpackage/gbp-pq.1.en.html). Additionally, due to the helpfulness of [autopkgtests](broken-reference) we should contribute a **minimal test**.

[Patches](broken-reference)

Patches are occasionally used to fix an issue with the upstream tool or adhere to standards. For this tool we will be creating a patch that will remove the update functionality from `photon.py`, so users will update the tool from **apt** instead.

We will be [using gbp pq](https://manpages.debian.org/unstable/git-buildpackage/gbp-pq.1.en.html) to create a patch for this package:

```
:~/kali/packages/photon$ gbp pq import
gbp:info: Trying to apply patches at 'ac95fad43f0418dd05510a9647b9f8e08c24ce12'
gbp:info: 0 patches listed in 'debian/patches/series' imported on 'patch-queue/kali/master'
:~/kali/packages/photon$
```

We first will create a separate branch where we can work freely. With this command, any patches that are already created will be automatically imported and applied:

```
:~/kali/packages/photon$ vim photon.py
:~/kali/packages/photon$
:~/kali/packages/photon$ git commit -m "disable update option"
[patch-queue/kali/master 799ec4a] disable update option
 1 file changed, 8 deletions(-)
:~/kali/packages/photon$
```

After we make our changes we will do a commit. The commit message will be the title of the patch:

```
:~/kali/packages/photon$ gbp pq export
gbp:info: On 'patch-queue/kali/master', switching to 'kali/master'
gbp:info: Generating patches from git (kali/master..patch-queue/kali/master)
:~/kali/packages/photon$
```

We export the commits into a patch with the titles of the commits we made. We can see there are some new files made up:

```
:~/kali/packages/photon$ ls debian/patches/
disable-update-option.patch  series
:~/kali/packages/photon$
```

[Autopkgtest](broken-reference)

[Autopkgtest](https://autopkgtest.kali.org/) is a huge help to **detecting issues when updating packages**. For this package, we will create a simple test that may not catch more advanced errors however it is better than nothing. We first will get started with creating the directory we will create the test in:

```
:~/kali/packages/photon$ mkdir -p debian/tests
```

We now have to create a control file. If we had multiple commands/tests, we would put different information into this file, however as we have only the one command/test we will be running we can work directly in this file.

For this test we will simply supply `--help` to photon and see if it works correctly. Because we only use photon, we only need what the tool is dependent on. For this we will use **@**. Finally, because it is a simple test that wont catch much, we make sure to note that this is a **superficial** test:

```
:~/kali/packages/photon$ vim debian/tests/control
:~/kali/packages/photon$
:~/kali/packages/photon$ cat debian/tests/control
Test-Command: photon --help
Depends: @
Restrictions: superficial
:~/kali/packages/photon$
```

More information on runtime tests can be found on [our docs](broken-reference) which has many other helpful resources that explain in detail runtime tests.

[Packing Up](broken-reference)

We can now commit our changes and see if it all works:

```
:~/kali/packages/photon$ git add debian/
:~/kali/packages/photon$
:~/kali/packages/photon$ git commit -m "Initial release"
[kali/master 9d93880] Initial release
 12 files changed, 139 insertions(+), 6 deletions(-)
 create mode 100644 debian/changelog
 create mode 100644 debian/control
 create mode 100644 debian/copyright
 create mode 100644 debian/helper-script/photon
 create mode 100644 debian/patches/disable-update-option.patch
 create mode 100644 debian/patches/series
 create mode 100644 debian/photon.install
 create mode 100755 debian/rules
 create mode 100644 debian/source/format
 create mode 100644 debian/tests/control
 create mode 100644 debian/watch
:~/kali/packages/photon$
```

Lets try and build the package!

```
:~/kali/packages/photon$ gbp buildpackage --git-builder=sbuild --git-export=WC
gbp:info: Creating /home/kali/kali/build-area/photon_1.3.0.orig.tar.gz
gbp:info: Exporting 'WC' to '/home/kali/kali/build-area/photon-tmp'
gbp:info: Moving '/home/kali/kali/build-area/photon-tmp' to '/home/kali/kali/build-area/photon-1.3.0'
gbp:info: Performing the build
dh clean --with python3
   dh_clean
[...]
Processing triggers for libc-bin (2.30-8) ...
W: photon: binary-without-manpage usr/bin/photon

I: Lintian run was successful.

+------------------------------------------------------------------------------+
| Post Build                                                                   |
+------------------------------------------------------------------------------+


+------------------------------------------------------------------------------+
| Cleanup                                                                      |
+------------------------------------------------------------------------------+

Purging /<<BUILDDIR>>
Not cleaning session: cloned chroot in use

+------------------------------------------------------------------------------+
| Summary                                                                      |
+------------------------------------------------------------------------------+

Build Architecture: amd64
Build Type: full
Build-Space: 524
Build-Time: 2
Distribution: kali-dev
Host Architecture: amd64
Install-Time: 126
Job: /home/kali/kali/build-area/photon_1.3.0-0kali1.dsc
Lintian: warn
Machine Architecture: amd64
Package: photon
Package-Time: 752
Source-Version: 1.3.0-0kali1
Space: 524
Status: successful
Version: 1.3.0-0kali1
--------------------------------------------------------------------------------
Finished at 2020-07-13T22:11:01Z
Build needed 00:12:32, 524k disk space
:~/kali/packages/photon$
```

Looks successful! We can now finish up the packaging by testing it out, committing and pushing changes, and send request for it to be added!
