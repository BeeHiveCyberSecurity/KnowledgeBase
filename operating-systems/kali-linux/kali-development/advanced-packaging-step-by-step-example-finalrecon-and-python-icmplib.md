# Advanced Packaging Step-By-Step Example (FinalRecon & Python-icmplib)

_This guide is accurate at the time of writing. As it references a lot of external resources out of our control, items may be different over time (as software gets updated)._

[**FinalRecon**](https://github.com/thewhiteh4t/FinalRecon) is a **Python 3** application with multiple Python dependencies. At the time of writing, one of the dependencies ([**python3-icmplib**](https://github.com/ValentinBELYN/icmplib)) is not in the Kali Linux repository. In this guide we will have to learn how to follow dependency chains, and fix anything required to ensure that the end package can be included. We will also create a patch, helper-script, as well as a [runtime test](broken-reference) for the package.

We will assume we have already followed our [documentation on setting up a packaging environment](broken-reference) as well as our previous other packaging guides [#1 (Instaloader)](broken-reference) & [#2 (Photon)](broken-reference) as this will explain their contents.

[FinalRecon Code Overview](broken-reference)

The first action we will take, will be to look at [FinalRecon’s source code](https://github.com/thewhiteh4t/FinalRecon) to see what information we can acquire. Using this, we notice the following:

* It has [no tag release](https://github.com/thewhiteh4t/FinalRecon/releases)
* The [MIT license file](https://github.com/thewhiteh4t/FinalRecon/blob/0d41eb61a023c1ae467ede8653d37cc847695f01/LICENSE)
* There is no `setup.py` file (which is used for [setuptools](https://packaging.python.org/tutorials/packaging-projects/))
* There is a `requirements.txt` [file](https://github.com/thewhiteh4t/FinalRecon/blob/0d41eb61a023c1ae467ede8653d37cc847695f01/requirements.txt) (which is used for [pip](https://pip.pypa.io/en/stable/user\_guide/#requirements-files))
* Various descriptions about the tool & usage guides
* Various external links _(if any additional research is required)_

[Missing Tag Releases](broken-reference)

As FinalRecon does [not have a tag release](https://github.com/thewhiteh4t/FinalRecon/releases) we will have to create our own upstream tar file. Looking to see what branches there are, we discover there is just one (there isn’t a stable/production one, or is there a beta/deployment/staging one). As a result, we will use whatever is the latest commit on the main branch until the author does a tag release. _We can auto open up an issue request and/or email them seeing if they will response to such an act_.

Note that having a “tagged” release is preferred when doing Debian packaging. End users often want something that is “stable”, and which has been fully tested. It’s also easier for the distribution to know when to update the package: we just wait for upstream to release something, which is a clear signal that the code is ready to be used. So when it’s possible, we favor packaging a tagged release over the latest Git commit.

[License](broken-reference)

This package has been detected as having a [**MIT**](https://opensource.org/licenses/MIT) license by [**GitHub**](https://github.com/thewhiteh4t/FinalRecon). If we look at the specific [license file](https://github.com/thewhiteh4t/FinalRecon/blob/0d41eb61a023c1ae467ede8653d37cc847695f01/LICENSE) we can see that there is not a lot to copy, so we will be copying this exactly as-is. Unfortunately, though we have found a maintainer we have not found any contact information yet. We will have to continue searching for contact information.

[Dependencies](broken-reference)

As there is a `requirements.txt` [file](https://github.com/thewhiteh4t/FinalRecon/blob/0d41eb61a023c1ae467ede8653d37cc847695f01/requirements.txt) (which is used for Python’s [pip](https://pip.pypa.io/en/stable/user\_guide/#requirements-files) to install any **Python dependencies** that are required for this tool to work), we will need check to see what’s needed.

[Description(s)](broken-reference)

We will once again pull our description from [FinalRecon’s GitHub](https://github.com/thewhiteh4t/FinalRecon).

For the **short description** we will use a modified version of the first line in the [README](https://github.com/thewhiteh4t/FinalRecon/blob/0d41eb61a023c1ae467ede8653d37cc847695f01/README.md), “A fast and simple python script for web reconnaissance.”

For the **long description** we will also use a modified version of the first line in the [README](https://github.com/thewhiteh4t/FinalRecon/blob/0d41eb61a023c1ae467ede8653d37cc847695f01/README.md), however we will expand this time, “A fast and simple python script for web reconnaissance that follows a modular structure and provides detailed information on various areas.”

[Maintainer(s)](broken-reference)

If we were to look all over the GitHub we would not find an email address. We could look in `git log` and view the email addresses associated, however these do not seem to be solid as there are multiple for “thewhiteh4t” _(at least 3)_. Instead, we do more digging. We notice that there is a YouTube video demo linked in the `README.md`, if we go to the YouTube channel’s [about page](https://www.youtube.com/c/thewhiteh4t/about) we can **view an email address** for business inquiries (which does not match to any in the git log). This will be a good choice to use as the contact information. With that said all said, not having a contact information is not an essential part , so if we were unable to find one we could still continue to package.

[Setting Up The Environment](broken-reference)

We will assume that we have already followed our [documentation on setting up a packing environment](broken-reference).

Let’s set up our directories now for this package:

```
:~$ mkdir -p ~/kali/packages/finalrecon/ ~/kali/upstream/
:~$
```

[Downloading Git Snapshot](broken-reference)

We’re going to download an archive of the upstream source code. Since upstream didn’t tag any release yet, we’ll package the latest Git commit on the main branch. There are different (many?) ways to do that, and in this example we will use `uscan` for the task. `uscan` is able to download a Git repository, pack it into a `.tar.gz` archive, and come up with a meaningful (and somewhat standard) version string.

This last point is important: a Debian package must have a version, however a Git commit doesn’t have a version _per se_. So we need to associate a version with a Git commit, and there are **many ways to get that wrong**. So rather than deciding by ourselves what the package version should be, we’ll let the tooling (`uscan` in this case) do that for us.

In order to use uscan, we need a `watch` file. This file is usually part of the packaging files, and located in `debian/watch`.

Let’s start by entering the working directory, and then create the `debian` dir:

```
:~$ cd ~/kali/packages/finalrecon/
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ mkdir debian
:~/kali/packages/finalrecon$
```

And now let’s create the `watch` file. The purpose of the watch file is to provide instructions to find the latest upstream release online. In this particular case though, upstream didn’t provide any tagged release yet, so we’ll configure the watch file to track the latest Git commit on the main branch:

```
:~/kali/packages/finalrecon$ vim debian/watch
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/watch
version=4
opts="mode=git, pgpmode=none" \
  https://github.com/thewhiteh4t/FinalRecon HEAD
:~/kali/packages/finalrecon$
```

At this point, we have enough to run uscan to download and pack the latest Git commit from upstream:

```
:~/kali/packages/finalrecon$ uscan --destdir ~/kali/upstream/ --force-download \
    --package finalrecon --upstream-version 0~0 --watchfile debian/watch
uscan: Newest version of finalrecon on remote site is 0.0~git20201107.0d41eb6, local version is 0~0
uscan:  => Newer package available from:
        => https://github.com/thewhiteh4t/FinalRecon HEAD
uscan warn: Missing debian/source/format, switch compression to gzip
Successfully repacked ~/kali/upstream/finalrecon-0.0~git20201107.0d41eb6.tar.xz as ~/kali/upstream/finalrecon_0.0~git20201107.0d41eb6.orig.tar.gz.
```

This command warrants some explanations. Since at this point we run uscan from an almost empty directory, we need to be explicit about what we want to do. In particular:

* `--watchfile` tells uscan where is the watch file that we want it to use.
* `--package` is used to give the package name.
* `--upstream-version` is actually the “current upstream version”. In general, uscan works by comparing the latest version found online with the version that is currently packaged, and it downloads the latest upstream version only if it’s newer than the current version. However here there’s no “current version” since we’re creating a new package, so we tell uscan that the current version is `0~0`, ie. the lowest version possible, so that whatever version found online is deemed higher than that.
* `--destdir` tells uscan where to save the download files.
* `--force-download` overrides uscan’s guess of what it should do: we want it to download the latest upstream version.

To be sure, we can have a look in the `~/kali/upstream` directory to check what files landed there:

```
:~/kali/packages/finalrecon$ ls ~/kali/upstream
finalrecon_0.0~git20201107.0d41eb6.orig.tar.gz  finalrecon-0.0~git20201107.0d41eb6.tar.xz
```

uscan packed the code from Git in a `.tar.xz` file, and for some reason (see the line starting with `uscan warn:` above), it repacked in as a `.tar.gz`. We don’t really care about the compression, we’re fine with both `.gz` and `.xz`. What matters is that we’ll use the file which name ends with `.orig.tar.*`, so we’re going to use the `.tar.gz`.

uscan came up with a funny-looking (and rather complicated) version string: `0.0~git20201107.0d41eb6`. Why is that?

* `0.0~` is the lowest starting point for a version string. It’s handy to start from there, so that whenever upstream does a “tagged release”, whatever they choose, it will be greater than our version. So we’ll be able to use it for the package version “as is”.
* `git` is informative, and it obviously refers to the VCS used by upstream (examples of other VCS: `svn` or `bzr`).
* `20201107` is the date (`YYYYMMDD` aka. ISO-8601 format) of the upstream commit that we package. Having the date part of the version string is needed so that whenever we’ll want to import a new Git snapshot, the date will be newer, and the new version string will be sorted above by the package manager (version strings must ALWAYS go ascending).
* `0d41eb6` is the Git commit. It’s informative, and it’s a non-ambiguous way to know exactly what upstream code is included in the package. Without it, a developer who wants to know what Git commit was packaged would rely on the date, and if there’s more than one commit on this date, it wouldn’t be clear what commit exactly was packaged. Additionally, this is an UTC date, while usual tools or web browser usuall show dates in local time: another source of error for those who rely on the date only. So having the Git commit part of the version string is really useful for developers (maybe not so much for users).

Alright, we hope that you appreciated this overwhelming amount of information. Let’s move on and keep working on the package.

[Creating Package Source Code](broken-reference)

We are now going to create a new **empty Git repository**:

```
:~/kali/packages/finalrecon$ git init
Initialized empty Git repository in /home/kali/kali/packages/finalrecon/.git/
:~/kali/packages/finalrecon$
```

We can now **import** the `.tar.gz` we previously downloaded into the empty Git repository we just created. When prompted, we remember to accept the default values _(or use the flag `--no-interactive`)_:

```
:~/kali/packages/finalrecon$ gbp import-orig ~/kali/upstream/finalrecon_0.0~git20201107.0d41eb6.orig.tar.gz
What will be the source package name? [finalrecon] 
What is the upstream version? [0.0~git20201107.0d41eb6] 
gbp:info: Importing '../upstream/finalrecon_0.0~git20201107.0d41eb6.orig.tar.gz' to branch 'upstream'...
gbp:info: Source package is finalrecon
gbp:info: Upstream version is 0.0~git20201107.0d41eb6
gbp:info: Successfully imported version 0.0~git20201107.0d41eb6 of /home/kali/kali/upstream/finalrecon_0.0~git20201107.0d41eb6.orig.tar.gz
:~/kali/packages/finalrecon$
```

We remember to **change the default branch**, from `master` to `kali/master` (as `master` is for upstream development), then **delete the old branch**. _We also run a quick `git branch -v` to visually see the change:_

```
:~/kali/packages/finalrecon$ git checkout -b kali/master
Switched to a new branch 'kali/master'
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git branch -D master
Deleted branch master (was 95b196b).
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git branch -v
* kali/master  bd003d7 New upstream version 0.0~git20201107.0d41eb6
  pristine-tar 2413cfe pristine-tar data for finalrecon_0.0~git20201107.0d41eb6.orig.tar.gz
  upstream     bd003d7 New upstream version 0.0~git20201107.0d41eb6
:~/kali/packages/finalrecon$
```

We can now **populate the `debian/` folder** with its related files. We will manually specify the upstream `.tar.gz` file _(as it is not located in `../`, but instead `~/kali/upstream/`)_. We will also set the package name to use in the same naming convention as before _(`<packagename>_<version>` as is Debian standards)_.

Note that we need to use the option `--addmissing` as there’s already a `debian/` directory (we created it above for the only purpose of having a watch file).

Afterwards we will remove any example files that get automatically generated, as they are not used:

```
:~/kali/packages/finalrecon$ dh_make --file ~/kali/upstream/finalrecon_0.0~git20201107.0d41eb6.orig.tar.gz -p finalrecon_0.0~git20201107.0d41eb6 --addmissing --single -y
Maintainer Name     : Joseph O'Gorman
Email-Address       : 
Date                : Fri, 22 Apr 2022 11:33:33 +0000
Package Name        : finalrecon
Version             : 0.0~git20201107.0d41eb6
License             : blank
Package Type        : single
Currently there is not top level Makefile. This may require additional tuning
File watch.ex exists, skipping
Done. Please edit the files in the debian/ subdirectory now.

:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ rm -f debian/*.docs debian/README* debian/*.ex debian/*.EX
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git status
On branch kali/master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	debian/

nothing added to commit but untracked files present (use "git add" to track)
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ ls debian/
changelog  control  copyright  rules  source  watch
:~/kali/packages/finalrecon$
```

At this point, we have the base packaging files in place, and it feels like a good idea to commit before starting some real work:

```
:~/kali/packages/finalrecon$ git add debian/
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git commit -m "Initial packaging files"
[kali/master 52042da] Initial packaging files
 6 files changed, 93 insertions(+)
 create mode 100644 debian/changelog
 create mode 100644 debian/control
 create mode 100644 debian/copyright
 create mode 100755 debian/rules
 create mode 100644 debian/source/format
 create mode 100644 debian/watch
:~/kali/packages/finalrecon$
```

***

We can now start to edit the files in the `debian/` folder to make sure the information is accurate. We can use what we found from before on [FinalRecon’s GitHub](https://github.com/thewhiteh4t/FinalRecon) to supply the correct information. To recap, we need to make sure we got the following bits of information to locate:

* Dependencies
* Description
* License
* Maintainers

[FinalRecon (Pip) Dependencies](broken-reference)

As there is a `requirements.txt` [file](https://github.com/thewhiteh4t/FinalRecon/blob/0d41eb61a023c1ae467ede8653d37cc847695f01/requirements.txt) (which is used for Python’s [pip](https://pip.pypa.io/en/stable/user\_guide/#requirements-files) to install any **Python dependencies** that are required for this tool to work), we will need check to see what’s needed.

For this tool to work, it requires additional software to be installed, aka dependencies. Depending on how the tool is coded, will depend on what is required (or only recommended) to be installed. FinalRecon is using various Python libraries and does not call any system commands.

In Python’s eco-system, there is [pip](https://pip.pypa.io/en/stable/user\_guide/#requirements-files). This is Python’s package manager, which can be used to download and install any Python libraries. However, we are trying to build a package for Debian package management instead. As a result, any Python libraries need to be ported over to Debian format, in order for our package to use them (so the OS can track any files, allowing for cleaner upgrades and un-installs of packages). Lets start out by looking to see what is needed outside of the standard values, for this tool to work:

```
:~/kali/packages/finalrecon$ cat requirements.txt
requests
ipwhois
bs4
lxml
dnslib
aiohttp
aiodns
psycopg2
tldextract
icmplib
:~/kali/packages/finalrecon$
```

***

We then try to search for each dependency from `requirements.txt` in `apt-cache`, to make sure that we have everything in Kali Linux’ repository:

```
:~/kali/packages/finalrecon$ sudo apt update
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ apt-cache search ipwhois | grep -i python3
python3-ipwhois - Retrieve and parse whois data for IP addresses (Python 3)
:~/kali/packages/finalrecon$
```

***

We could search each one manually by repeating the above process for all items in `requirements.txt`, or we can make a quick loop to automate it.

During this process, we will notice **one dependency which does not have an entry (`icmplib`)**:

```
:~/kali/packages/finalrecon$ cat requirements.txt | while read x; do
  apt-cache search $x | grep -i "python3-$x -" \
    || echo --MISSING $x--;
done
python3-requests - elegant and simple HTTP library for Python3, built for human beings
python3-ipwhois - Retrieve and parse whois data for IP addresses (Python 3)
python3-bs4 - error-tolerant HTML parser for Python 3
python3-lxml - pythonic binding for the libxml2 and libxslt libraries
python3-dnslib - Module to encode/decode DNS wire-format packets (Python 3)
python3-aiohttp - http client/server for asyncio
python3-aiodns - Asynchronous DNS resolver library for Python 3
python3-psycopg2 - Python 3 module for PostgreSQL
python3-tldextract - Python library for separating TLDs
--MISSING icmplib--
:~/kali/packages/finalrecon$
```

***

We can try and **broaden our search** for `icmplib`, as we were limiting output last time _(by using grep)_:

```
:~/kali/packages/finalrecon$ apt-cache search icmplib | grep -i python3
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ apt-cache search icmplib
:~/kali/packages/finalrecon$
```

***

Unfortunately it appears that Kali Linux does not have this dependency (Python’s icmplib) in the repository at this point in time. This means we will need to **extend our packaging process** to accommodate for packaging up icmplib as well, to allow us to completely package up FinalRecon.

We will first look for `icmplib` in the [**pypi.org**](https://pypi.org/) **repository**. We can easily find [icmplib on PyPI](https://pypi.org/project/icmplib/) along with the link to its [GitHub page](https://github.com/ValentinBELYN/icmplib). If we do the same process with icmplib looking over the GitHub page as we did for FinalRecon, we can see that **icmplib will not need additional dependencies** (no `requirements.txt` file and `setup.py` [does not list anything for](https://packaging.python.org/discussions/install-requires-vs-requirements/) `install_requires`) and therefore will be a relatively straightforward Python package.

We can now either:

* Continue to package FinalRecon, before moving onto icmplib. We have to remember that we cannot successfully build a complete working package until we are done with `icmplib`.
* Pause FinalRecon packaging, and switch our focus to icmplib. We have to make sure we took detailed notes with the work we have done so far and information gathered.

We will go with the former option, and **continue as far as we can with FinalRecon**.

[Editing FinalRecon Package Source Code](broken-reference)

We can now start to edit the files in the `debian/` folder.

[Changelog](broken-reference)

We will now perform what are our standard changes ([#1 (Instaloader)](broken-reference) & [#2 (Photon)](broken-reference)) to the **version**, **distribution** and **description**. The resulting file should be similar to the following:

```
:~/kali/packages/finalrecon$ vim debian/changelog
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/changelog
finalrecon (0.0~git20201107.0d41eb6-0kali1) kali-dev; urgency=medium

  * Initial release

 -- Joseph O'Gorman <>  Fri, 22 Apr 2022 11:33:33 +0700
:~/kali/packages/finalrecon$
```

You could also use `dch -r` or `gbp dch` to edit the file, rather than `vim`.

You will need to update the version to make the same date as used previously.

[Control](broken-reference)

Using what we know from the information we have already gathered from GitHub and the source code, it is once again similar to our previous packaging guides ([#1 (Instaloader)](broken-reference) & [#2 (Photon)](broken-reference)). We should have a good understanding of what needs to be altered now.

As there is no code that needs to be compiled, we can set `Architecture: all`. This is true for most Python scripts, as they are not providing Python “extensions”. If they are, they would generate a compiled `.so` files (e.g. [psycopg2](https://pkg.kali.org/pkg/psycopg2)).

We make sure to include the **Python dependencies** for building the package as well as the tool dependencies to run (the values from pip).

There is one thing to note, and that is `python3-icmplib`. **This package does not exist yet**. We are adding this in for the time being as we will be creating it soon, to prevent going back and adding it we will add it now. This does **mean that we will be unable to build our package until** we finish with `icmplib`:

```
:~/kali/packages/finalrecon$ vim debian/control
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/control
Source: finalrecon
Section: misc
Priority: optional
Maintainer: Kali Developers <>
Uploaders: Joseph O'Gorman <>
Build-Depends: debhelper-compat (= 12),
               dh-python,
               python3-aiodns,
               python3-aiohttp,
               python3-all,
               python3-bs4,
               python3-dnslib,
               python3-icmplib,
               python3-ipwhois,
               python3-lxml,
               python3-psycopg2,
               python3-requests,
               python3-tldextract,
Standards-Version: 4.5.0
Homepage: https://github.com/thewhiteh4t/FinalRecon
Vcs-Browser: https://gitlab.com/kalilinux/packages/finalrecon
Vcs-Git: https://gitlab.com/kalilinux/packages/finalrecon

Package: finalrecon
Architecture: all
Depends: ${misc:Depends},
         ${python3:Depends},
         python3-aiodns,
         python3-aiohttp,
         python3-bs4,
         python3-dnslib,
         python3-icmplib,
         python3-ipwhois,
         python3-lxml,
         python3-psycopg2,
         python3-requests,
         python3-tldextract,
Description: A fast and simple python script for web reconnaissance
 A fast and simple python script for web reconnaissance that follows
 a modular structure and provides detailed information on various areas.
:~/kali/packages/finalrecon$
```

[Copyright](broken-reference)

As we have already finished getting the copyright information (license, name, contact, year and source), we now just need to add it:

```
:~/kali/packages/finalrecon$ vim debian/copyright
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/copyright
Format: https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/
Upstream-Name: finalrecon
Upstream-Contact: thewhiteh4t <>
Source: https://github.com/thewhiteh4t/FinalRecon

Files: *
Copyright: 2020 thewhiteh4t <>
License: MIT

Files: debian/*
Copyright: 2020 Joseph O'Gorman <>
License: MIT

License: MIT
 Copyright (c) 2020 thewhiteh4t
 .
 Permission is hereby granted, free of charge, to any person obtaining a copy
 of this software and associated documentation files (the "Software"), to deal
 in the Software without restriction, including without limitation the rights
 to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
 copies of the Software, and to permit persons to whom the Software is
 furnished to do so, subject to the following conditions:
 .
 The above copyright notice and this permission notice shall be included in all
 copies or substantial portions of the Software.
 .
 THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
 IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
 FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
 AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
 LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
 OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
 SOFTWARE.
:~/kali/packages/finalrecon$
```

[Rules](broken-reference)

The start of the rules file will look very similar to [#2 (Photon)](broken-reference), however there is a new lower section. This part is to set the permissions on `finalrecon.py`, so when we call it using the symlinks (by `debian/links`), it will be executable:

```
:~/kali/packages/finalrecon$ vim debian/rules
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/rules
#!/usr/bin/make -f
#export DH_VERBOSE = 1
export PYBUILD_NAME=finalrecon

%:
	dh  --with python3

override_dh_install:
	dh_install
	chmod 0755 debian/finalrecon/usr/share/finalrecon/finalrecon.py
:~/kali/packages/finalrecon$
```

Beware that the “dh” line needs to be indented by a single tabulation character, rather than spaces.

[Watch](broken-reference)

The watch file was already covered at the beginning of this example, and is configured to track the latest Git commit on the main branch.

You can also add the [**common configuration for GitHub**](https://wiki.debian.org/debian/watch), but leave it commented out, so that whenever upstream will issue a release, everything is ready in your watch file and you’ll just need to uncomment it:

```
:~/kali/packages/finalrecon$ vim debian/watch
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/watch
version=4                                       
opts=mode=git,pgpmode=none \
  https://github.com/thewhiteh4t/FinalRecon HEAD

# Use the following when upstream starts to tag releases:
#opts=filenamemangle=s/.+\/v?(\d\S+)\.tar\.gz/finalrecon-$1\.tar\.gz/ \
#  https://github.com/thewhiteh4t/FinalRecon/tags .*/v?(\d\S+)\.tar\.gz
:~/kali/packages/finalrecon$
```

[Links](broken-reference)

Whereas last time ([#1 (Instaloader)](broken-reference) & [#2 (Photon)](broken-reference)), we are not going to use a “helper-script” but instead create a symlink pointing to the main Python file, which will still be in `$PATH`:

```
:~/kali/packages/finalrecon$ vim debian/links
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/links
usr/share/finalrecon/finalrecon.py usr/bin/finalrecon
:~/kali/packages/finalrecon$
```

One thing we notice during the testing process of the script, we have to `cd` into the directory before calling the Python script. This is because the tool attempts to drop files into the `dumps` folder, and if it is not in path FinalRecon will fail.

This could be discovered by auditing the source code, or trial and error when testing the package after its built.

[.Install](broken-reference)

We can now create the install file, which is required to say **what files go where on the system during the unpacking of the package**. We need to make sure to include everything from the root of the package directory:

```
:~/kali/packages/finalrecon$ vim debian/finalrecon.install
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/finalrecon.install
conf usr/share/finalrecon/
finalrecon.py usr/share/finalrecon/
modules usr/share/finalrecon/
wordlists usr/share/finalrecon/
:~/kali/packages/finalrecon$
```

There is not a leading slash on the destination directory

[Patches](broken-reference)

For this tool we will need to also implement a **patch to disable the update and dependency checker**. If the program self updates, the system will not be aware of any additional files outside of the package, so things then start to get messy. The dependency is also being handled by our package now instead. Knowing you need to do this, comes with either knowing the tool, or auditing the source code.

The patch process looks like the following (for more information see [our previous guide, #2 (Photon)](broken-reference)):

```
:~/kali/packages/finalrecon$ gbp pq import
gbp:info: Trying to apply patches at 'f1c4c9f8d25224186749ce69a9f403f207feda03'
gbp:info: 0 patches listed in 'debian/patches/series' imported on 'patch-queue/kali/master'
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ vim finalrecon.py
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git add finalrecon.py
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git commit -m "disable requirements check"
[...]
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ vim finalrecon.py
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git add finalrecon.py
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git commit -m "disable ver_check"
[...]
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ gbp pq export
gbp:info: On 'patch-queue/kali/master', switching to 'kali/master'
gbp:info: Generating patches from git (kali/master..patch-queue/kali/master)
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git branch -v
* kali/master             bd003d7 New upstream version 0.0~git20201107.0d41eb6
  patch-queue/kali/master 2935f22 disable ver_check
  pristine-tar            2413cfe pristine-tar data for finalrecon_0.0~git20201107.0d41eb6.orig.tar.gz
  upstream                bd003d7 New upstream version 0.0~git20201107.0d41eb6
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ ls debian/patches/
disable-requirements-check.patch  disable-ver_check.patch  series
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/patches/disable-requirements-check.patch
From: Joseph O'Gorman <>
Subject: disable requirements check

---
 finalrecon.py | 32 ++++++++++++++++----------------
 1 file changed, 16 insertions(+), 16 deletions(-)

diff --git a/finalrecon.py b/finalrecon.py
index 735f40b..95e99f1 100644
--- a/finalrecon.py
+++ b/finalrecon.py
@@ -26,22 +26,22 @@ else:

 path_to_script = os.path.dirname(os.path.realpath(__file__))

-with open(path_to_script + '/requirements.txt', 'r') as rqr:
-       pkg_list = rqr.read().strip().split('\n')
-
-print('\n' + G + '[+]' + C + ' Checking Dependencies...' + W + '\n')
-
-for pkg in pkg_list:
-       spec = importlib.util.find_spec(pkg)
-       if spec is None:
-               print(R + '[-]' + W + ' {}'.format(pkg) + C + ' is not Installed!' + W)
-               fail = True
-       else:
-               pass
-if fail == True:
-       print('\n' + R + '[-]' + C + ' Please Execute ' + W + 'pip3 install -r requirements.txt' + C + ' to Install Missing Packages' + W + '\n')
-       os.remove(pid_path)
-       sys.exit()
+#with open(path_to_script + '/requirements.txt', 'r') as rqr:
+#      pkg_list = rqr.read().strip().split('\n')
+
+#print('\n' + G + '[+]' + C + ' Checking Dependencies...' + W + '\n')
+
+#for pkg in pkg_list:
+#      spec = importlib.util.find_spec(pkg)
+#      if spec is None:
+#              print(R + '[-]' + W + ' {}'.format(pkg) + C + ' is not Installed!' + W)
+#              fail = True
+#      else:
+#              pass
+#if fail == True:
+#      print('\n' + R + '[-]' + C + ' Please Execute ' + W + 'pip3 install -r requirements.txt' + C + ' to Install Missing Packages' + W + '\n')
+#      os.remove(pid_path)
+#      sys.exit()

 import argparse

:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/patches/disable-requirements-check.patch
From: Joseph O'Gorman <>
Subject: disable ver_check

---
 finalrecon.py | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/finalrecon.py b/finalrecon.py
index 95e99f1..d21877c 100644
--- a/finalrecon.py
+++ b/finalrecon.py
@@ -207,7 +207,7 @@ def full_recon():
 try:
        fetch_meta()
        banner()
-       ver_check()
+       #ver_check()

        if target.startswith(('http', 'https')) == False:
                print(R + '[-]' + C + ' Protocol Missing, Include ' + W + 'http://' + C + ' or ' + W + 'https://' + '\n')
:~/kali/packages/finalrecon$
```

[Runtime Test](broken-reference)

The [runtime test](broken-reference) process looks like the following (for more information see [our previous guide, #2 (Photon)](broken-reference)). Just like last time, we will just create a **minimal test to look for the help screen**:

```
:~/kali/packages/finalrecon$ mkdir -p debian/tests/
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ vim debian/tests/control
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ cat debian/tests/control
Test-Command: finalrecon -h
Restrictions: superficial
:~/kali/packages/finalrecon$
```

[Completing dependencies](broken-reference)

In theory, we should have a complete working package now with the exception of the missing `icmplib` dependency. So we now need to package up `icmplib`, before trying to finally build FinalRecong.

[icmplib](broken-reference)[Naming Packages](broken-reference)

Unlike our previous guides ([#1 (Instaloader)](broken-reference) & [#2 (Photon)](broken-reference)) where we use the same name for both **source package** and **binary package**, this time we will differ them.

The naming convention for a **binary package is `python3-<package>`**, which is important to follow as it has a impact at a technical level. However a **source package can be `python-<package>`** (or even just `<package>`). It does not matter if this is not followed as it will not break anything if its not followed. However, from a Kali team point of view we prefer and will use `python-<package>`. See this [Debian resource](https://www.debian.org/doc/packaging-manuals/python-policy/ch-module\_packages.html) for more information.

[Cheat Sheet Packaging](broken-reference)

This package is straightforward using `python3-setuptools` (like in our [first guide (Instaloader)](broken-reference)), so to prevent this guide from getting too long, we will not be going step by step for `icmplib`.

For more information on building Python libraries, see the [Debian resource](https://wiki.debian.org/Python/LibraryStyleGuide)

Here is a quick overview of the **commands needed to build the package**:

```
mkdir -p ~/kali/upstream/ ~/kali/build-area/ ~/kali/packages/python-icmplib/ 
wget https://github.com/ValentinBELYN/icmplib/archive/v1.2.2.tar.gz -O ~/kali/upstream/python-icmplib_1.2.2.orig.tar.gz
cd ~/kali/packages/python-icmplib/
git init
gbp import-orig ~/kali/upstream/python-icmplib_1.2.2.orig.tar.gz --no-interactive --debian-branch=kali/master
dh_make --file ~/kali/upstream/python-icmplib_1.2.2.orig.tar.gz -p python-icmplib_1.2.2 --python -y
rm -f debian/{*.docs,README*,*.ex,*.EX}
vim debian/changelog
vim debian/control
vim debian/copyright
vim debian/rules
vim debian/watch
gbp buildpackage --git-builder=sbuild --git-export=WC
sudo dpkg -i ~/kali/build-area/python3-icmplib_1.2.2-0kali1_all.deb
pip search icmplib
git add debian/
git commit -m "Initial release"
```

***

Previewing the contents of the key filesin `debian/`:

[**Changelog**](broken-reference)

Straight forward, like all the other guides, [#1 (Instaloader)](broken-reference) & [#2 (Photon)](broken-reference), edit **version**, **distribution** and **description**.

Note, `python-icmplib` needs to match the source name in `debian/control`:

```
:~/kali/packages/python-icmplib$ cat debian/changelog
python-icmplib (1.2.2-0kali1) kali-dev; urgency=medium

  * Initial release

 -- Joseph O'Gorman <>  Mon, 12 Oct 2020 18:10:27 -0400
:~/kali/packages/python-icmplib$
```

[**Control**](broken-reference)

This is a bit different to what we have seen previously with `Section: python`. This is because its a **Python library**. For more information see [Debian’s write up](https://www.debian.org/doc/debian-policy/ch-archive.html#s-subsections) as well as the [different options](https://packages.debian.org/testing/).

We also need to name the package differently. The source package part of `debian/control` is the top part, which gets named with the `Source:` field, whereas the binary part the lower half and uses `Package:` to name. _Were possible Kali Linux will always try and do both a source and binary package (See the_ [_Debian resource_](https://wiki.debian.org/Packaging/SourcePackage) _for more information)._

Note, the source name `python-icmplib` needs to match in `debian/changelog`:

```
:~/kali/packages/python-icmplib$ cat debian/control
Source: python-icmplib
Section: python
Priority: optional
Maintainer: Kali Developers <>
Uploaders: Joseph O'Gorman <>
Build-Depends: debhelper-compat (= 12),
                                dh-python,
                                python3-all,
                                python3-setuptools
Standards-Version: 4.5.0
Homepage: https://github.com/ValentinBELYN/icmplib
Vcs-Browser: https://gitlab.com/kalilinux/packages/python-icmplib
Vcs-Git: https://gitlab.com/kalilinux/packages/python-icmplib.git

Package: python3-icmplib
Architecture: all
Depends: ${python3:Depends}, ${misc:Depends}
Description: Python tool to forge ICMP packages
 icmplib is a brand new and modern implementation of the ICMP protocol in Python
 Able to forge ICMP packages to make your own ping, multiping, traceroute etc
:~/kali/packages/python-icmplib$
```

[**Copyright**](broken-reference)

As we renamed the `orig.tar.gz`, upstream name is incorrect, as it normally would not have a leading `python3-`. We can get this from the **source URL**:

```
:~/kali/packages/python-icmplib$ cat debian/copyright
Format: https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/
Upstream-Name: icmplib
Upstream-Contact: Valentin BELYN <>
Source: https://github.com/ValentinBELYN/icmplib

Files: *
Copyright: 2020 Valentin BELYN <>
License: LGPL-3+

Files: debian/*
Copyright: 2020 Joseph O'Gorman <>
License: LGPL-3+

License: LGPL-3+
 This program is free software; you can redistribute it and/or modify it
 under the terms of the GNU Lesser General Public License as
 published by the Free Software Foundation; either version 3 of
 the License, or (at your option) any later version.
 .
 This program is distributed in the hope that it will be useful, but
 WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
 Lesser General Public License for more details.
 .
 You should have received a copy of the GNU Lesser General Public
 License along with this program; if not, see <https://www.gnu.org/licenses/>.
 .
 On Debian systems, the full text of the GNU Lesser General Public
 License version 3 can be found in the file
 `/usr/share/common-licenses/LGPL-3'.
:~/kali/packages/python-icmplib$
```

[**Rules**](broken-reference)

We need to make sure to drop any leading `python-` when being defined in `PYBUILD_NAME`, even though the binary package which gets produced (as defined in `debian/control`) will be `python3-icmplib`. This is because of [PyBuild](https://wiki.debian.org/Python/Pybuild), **only wanting the Python module name**:

```
:~/kali/packages/python-icmplib$ cat debian/rules
#!/usr/bin/make -f
#export DH_VERBOSE = 1
export PYBUILD_NAME=icmplib

%:
	dh  --with python3 --buildsystem=pybuild
:~/kali/packages/python-icmplib$
```

[**Watch**](broken-reference)

Straight forward, like all the other guides, [#1 (Instaloader)](broken-reference) & [#2 (Photon)](broken-reference), using the [**Debian standard watch file for GitHub**](https://wiki.debian.org/debian/watch):

```
:~/kali/packages/python-icmplib$ cat debian/watch
version=4
opts=filenamemangle=s/.+\/v?(\d\S+)\.tar\.gz/icmplib-$1\.tar\.gz/ \
  https://github.com/ValentinBELYN/icmplib/tags .*/v?(\d\S+)\.tar\.gz
:~/kali/packages/python-icmplib$
```

***

We have successfully managed to build a Python 3 library file, icmplib!

[**Final FinalRecon Build**](broken-reference)

As we may not have pushed out, had `python3-icmplib` being accepted yet into Kali Linux, or you may want to submit both at the same time, we can **include the recently generated package in the chroot** for `sbuild` to use, it is a listed requirement for FinalRecon.

We are also unsure about the status of the package, we may not want to commit the latest edits to Git. So we will add `--git-export=WC` when **building the package**:

```
:~/kali/packages/python-icmplib$ cd ~/kali/packages/finalrecon/
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ gbp buildpackage \
  --git-builder=sbuild --git-export=WC \
  --extra-package=$HOME/kali/build-area/python3-icmplib_1.2.2-0kali1_all.deb
[...]
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ ls -lah ~/kali/build-area/finalrecon_*.deb
-rw-rw-r-- 1 kali kali 83K Nov  8 07:44 /home/kali/kali/build-area/finalrecon_0.0~git20201107.0d41eb6-0kali1_all.deb
:~/kali/packages/finalrecon$
```

***

Before we try to test our newly generated package, we remember that in `debian/control` we listed a few dependencies (not only to build the package but to run the package). Using `dpkg`, it will not satisfy these requirements, so we need to manually install them first. We can **check what is missing from our operating system**, by doing:

```
:~/kali/packages/finalrecon$ dpkg-checkbuilddeps
dpkg-checkbuilddeps: error: Unmet build dependencies: python3-ipwhois python3-dnslib python3-aiohttp python3-aiodns python3-psycopg2 python3-tldextract
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ sudo apt -y build-dep .
[...]
:~/kali/packages/finalrecon$
```

If you fail to do install the package, you may end up with the following mess:

```
:~/kali/packages/finalrecon$ sudo dpkg -i ~/kali/build-area/finalrecon_*.deb
(Reading database ... 167589 files and directories currently installed.)
Preparing to unpack .../finalrecon_0.0~git20201107.0d41eb6-0kali1_all.deb ...
Unpacking finalrecon (0.0~git20201107.0d41eb6-0kali1) over (0.0~git20201107.0d41eb6-0kali1) ...
dpkg: dependency problems prevent configuration of finalrecon:
 finalrecon depends on python3-ipwhois; however:
  Package python3-ipwhois is not installed.
 finalrecon depends on python3-dnslib; however:
  Package python3-dnslib is not installed.
 finalrecon depends on python3-aiohttp; however:
  Package python3-aiohttp is not installed.
 finalrecon depends on python3-aiodns; however:
  Package python3-aiodns is not installed.
 finalrecon depends on python3-psycopg2; however:
  Package python3-psycopg2 is not installed.
 finalrecon depends on python3-tldextract; however:
  Package python3-tldextract is not installed.
dpkg: error processing package finalrecon (–install):
dependency problems - leaving unconfigured
Processing triggers for kali-menu (2020.3.2) …
Errors were encountered while processing:
finalrecon
:~/kali/packages/finalrecon$
```

***

You will then hit the issue of the next time you try and install or update a package, it will fail:

```
:~/kali/packages/finalrecon$ sudo apt upgrade
Reading package lists... Done
Building dependency tree
Reading state information... Done
You might want to run 'apt --fix-broken install' to correct these.
The following packages have unmet dependencies:
 finalrecon : Depends: python3-ipwhois but it is not installed
              Depends: python3-dnslib but it is not installed
              Depends: python3-aiohttp but it is not installed
              Depends: python3-aiodns but it is not installed
              Depends: python3-psycopg2 but it is not installed
              Depends: python3-tldextract but it is not installed
E: Unmet dependencies. Try 'apt --fix-broken install' with no packages (or specify a solution).
:~/kali/packages/finalrecon$
```

***

Following what it says, running `sudo apt --fix-broken install` often fixes the issue.

***

Our package has been built and dependencies have been installed. Its now time to **finally install FinalRecon**:

```
:~/kali/packages/finalrecon$ sudo dpkg -i ~/kali/build-area/finalrecon_*.deb
[...]
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ dpkg -l | grep final
ii  finalrecon                           0.0~git20201107.0d41eb6-0kali1               all          A fast and simple python script for web reconnaissance
:~/kali/packages/finalrecon$
```

You can also install by doing:

```
:~/kali/packages/finalrecon$ sudo debi --debs-dir ~/kali/build-area/
```

***

We have **successfully managed to build FinalRecon as a package**!

Let’s test to **make sure it works**:

```
:~/kali/packages/finalrecon$ finalrecon
usage: finalrecon [-h] [--headers] [--sslinfo] [--whois] [--crawl] [--dns] [--sub] [--trace] [--dir] [--ps] [--full] [-t T] [-T T] [-w W] [-r] [-s]
                  [-sp SP] [-d D] [-e E] [-m M] [-p P] [-tt TT] [-o O]
                  url
finalrecon: error: the following arguments are required: url
:~/kali/packages/finalrecon$
```

[Saving Our Work](broken-reference)

At this point, we can **save the work** we have put in:

```
:~/kali/packages/finalrecon$ git add debian/
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git commit -m "Initial release"
[kali/master d1c9f75] Initial release
 12 files changed, 169 insertions(+)
 create mode 100644 debian/changelog
 create mode 100644 debian/control
 create mode 100644 debian/copyright
 create mode 100644 debian/finalrecon.install
 create mode 100644 debian/links
 create mode 100644 debian/patches/disable-requirements-check.patch
 create mode 100644 debian/patches/disable-ver_check.patch
 create mode 100644 debian/patches/series
 create mode 100755 debian/rules
 create mode 100644 debian/source/format
 create mode 100644 debian/tests/control
 create mode 100644 debian/watch
:~/kali/packages/finalrecon$
:~/kali/packages/finalrecon$ git status
On branch kali/master
nothing to commit, working tree clean
:~/kali/packages/finalrecon$
```

***

We can now finish up the packaging by **putting in a request on the** [**Kali Linux bug tracker**](https://bugs.kali.org/) for these packages to be added!

[Message From Kali Team](broken-reference)

During the packaging process, we worked with the tool author (upstream), so the program would be [better fit with FHS](https://tldp.org/LDP/Linux-Filesystem-Hierarchy/html/). An example of this is, not to use `/usr/share/finalrecon/dumps` as writing to `/usr/share` requires root privileges and we also do not want user files to be saved here.
