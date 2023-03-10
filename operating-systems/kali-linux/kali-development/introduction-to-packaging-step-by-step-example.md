# Introduction to packaging step-by-step example

### Instaloader <a href="#instaloader" id="instaloader"></a>

[Instaloader](https://github.com/instaloader/instaloader/) is a **Python 3** application with a single dependency (Python’s `requests`). This makes it a relatively simple package, however not as straightforward as only packaging up a shell script would be. Because of the learning opportunities and simplicity, this makes it a good introduction package.

[Instaloader Code Overview](broken-reference)

The first thing we do is look at the application’s [GitHub page](https://github.com/instaloader/instaloader/). A few things stand out which we take a note of:

[![](<../../../.gitbook/assets/instaloader 00.png>)](<../../../.gitbook/assets/instaloader 00.png>)

What we notice here is some information that will come in handy later:

* The tool contains a `setup.py` script
* It has a release
* The license is MIT based

We’ll be digging into each of these more later, for now it is just information to know.

[Setting Up The Environment](broken-reference)

We will assume that we have already followed our [documentation on setting up a packing environment](broken-reference).

Let’s set up our directories now for this package:

```
:~$ mkdir -p ~/kali/packages/instaloader/ ~/kali/upstream/
:~$
```

Everything that relates to us building a package will be using `~/kali/`. In there will be two sub folders:

* `packages/` will be a source code of the package we are going to create
* `upstream/` will be a compressed file of the source code of the application _(ideally from a tag version release which we saw before)_

[Downloading Tag Releases](broken-reference)

Because we are making a new package from scratch, we’ll manually download the version of the tool we want to package up. If we were updating a package (and it was packaged correctly), there is a process to help speed it up. However, this will be covered in [another guide](broken-reference).

Going to the [GitHub’s release page](https://github.com/instaloader/instaloader/releases), we can see the latest version (which at the time of writing is `4.4.4`). Here is the option to download `instaloader-v4.4.4-windows-standalone.zip`, as well as `Source Code (zip)`, and `Source Code (tar.gz)`. We are interested in the `tar.gz` option.

We will use `wget` and make sure to format its name appropriately according to Debian’s standards for source packages (take note of `.orig.tar.gz`):

```
:~$ wget https://github.com/instaloader/instaloader/archive/refs/tags/v4.4.4.tar.gz  -O ~/kali/upstream/instaloader_4.4.4.orig.tar.gz
:~$
```

If there isn’t a tag release for the software _(or it hasn’t had an release in some time)_, we can use the latest git commit. This is covered in another guide. However, it is preferred to use a tag release when available.

[Creating Package Source Code](broken-reference)

We need to switch paths to the working location of the package:

```
:~$ cd ~/kali/packages/instaloader/
:~/kali/packages/instaloader$
```

We are now going to create a new blank git repository:

```
:~/kali/packages/instaloader$ git init
Initialized empty Git repository in /home/kali/kali/packages/instaloader/.git/
:~/kali/packages/instaloader$
```

If we wanted to, we can confirm this by looking at “status” and “log”:

```
:~/kali/packages/instaloader$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git log
fatal: your current branch 'master' does not have any commits yet
:~/kali/packages/instaloader$
```

Great. Everything is empty; we have a clean working area.

We can now import the upstream version into our packing source code by using the file downloaded from `wget` before. Because of the filename format, `gbp` is able to detect the values `instaloader` as the package name, and `4.4.4` as the version. We just press enter to accept the default values:

```
:~/kali/packages/instaloader$ gbp import-orig ~/kali/upstream/instaloader_4.4.4.orig.tar.gz
What will be the source package name? [instaloader]
What is the upstream version? [4.4.4]
gbp:info: Importing '/home/kali/kali/upstream/instaloader_4.4.4.orig.tar.gz' to branch 'upstream'...
gbp:info: Source package is instaloader
gbp:info: Upstream version is 4.4.4
gbp:info: Successfully imported version 4.4.4 of /home/kali/kali/upstream/instaloader_4.4.4.orig.tar.gz
:~/kali/packages/instaloader$
```

If we wanted to check everything is okay, once again, we can use git to do so:

```
:~/kali/packages/instaloader$ git status
On branch master
nothing to commit, working tree clean
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git log
commit 494f71875f10f8d1da69a8edf2fc75300e4485b9 (HEAD -> master, tag: upstream/4.4.4, upstream)
Author: Joseph O'Gorman <>

    New upstream version 4.4.4
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git branch -v
* master       494f718 New upstream version 4.4.4
  pristine-tar 439fe30 pristine-tar data for instaloader_4.4.4.orig.tar.gz
  upstream     494f718 New upstream version 4.4.4
:~/kali/packages/instaloader$
```

So there is now an automatic commit created in the master branch _(which is the current active branch, shown by the `*`)_, as well as two other branches:

* `pristine-tar` which is metadata from the import
* `upstream` which is the source code of the application, without any of our package modifications

We are creating a Kali package, and we don’t use the `master` branch, but rather `kali/master`. So let’s switch:

```
:~/kali/packages/instaloader$ git checkout -b kali/master
Switched to a new branch 'kali/master'
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git branch -D master
Deleted branch master (was 494f718).
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git branch -v
* kali/master  494f718 New upstream version 4.4.4
  pristine-tar 439fe30 pristine-tar data for instaloader_4.4.4.orig.tar.gz
  upstream     494f718 New upstream version 4.4.4
:~/kali/packages/instaloader$
```

Now we can generate the necessary files required to build a Debain-based package and also remove any example files created. During the process, we will be asked if its:

* `Single binary`
* `Arch-Independent`
* `Library`
* `Python`

We are going to keep it simple, and go with “**S**ingle”. Then accept what’s on the screen with `Y`. If you would like more information about when to use what option, please see the [manpage for dh\_make](https://manpages.debian.org/jessie/dh-make/dh\_make.8.en.html).:

```
:~/kali/packages/instaloader$ dh_make --file ~/kali/upstream/instaloader_4.4.4.orig.tar.gz -p instaloader_4.4.4
Type of package: (single, indep, library, python)
[s/i/l/p]?
Maintainer Name     : Joseph O'Gorman
Email-Address       : 
Date                : Thu, 02 Jul 2020 17:59:47 -0400
Package Name        : instaloader
Version             : 4.4.4
License             : blank
Package Type        : single
Are the details correct? [Y/n/q]
Currently there is not top level Makefile. This may require additional tuning
Done. Please edit the files in the debian/ subdirectory now.
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ rm debian/*.docs debian/README* debian/*.ex debian/*.EX
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ rm -r debian/upstream
:~/kali/packages/instaloader$
```

We use `--file` to say where the `orig.tar.gz` file is. If the file was one directory back (`../`), this would not be needed, however as we have created a separate location for the file it is.

If you would like to see what got generated when using `dh_make`, we can use `git`:

```
:~/kali/packages/instaloader$ git status
On branch kali/master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        debian/

nothing added to commit but untracked files present (use "git add" to track)
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ ls -R debian/
debian/:
changelog  control  copyright  rules  source

debian/source:
format
:~/kali/packages/instaloader$
```

A quick overview of each of those files:

* `changelog` - tracks when the package gets an update (including why and by who). This is responsible for the package version
* `control` - is the metadata for the package (often seen with `apt`)
* `copyright` - what is under what license. The package can be under something different to the work we have put in to create the package
* `rules` - how to install the package
* `source/format` - is the source package format

At this point, we have the base packaging files in place, and it feels like a good idea to commit before starting some real work:

```
:~/kali/packages/instaloader$ git add debian/
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git commit -m "Initial packaging files"
[kali/master 52042da] Initial packaging files
 5 files changed, 93 insertions(+)
 create mode 100644 debian/changelog
 create mode 100644 debian/control
 create mode 100644 debian/copyright
 create mode 100755 debian/rules
 create mode 100644 debian/source/format
:~/kali/packages/instaloader$
```

We now need to edit most of these to make sure the information is accurate. We can use what we found on GitHub to supply the correct info into the `debian/` files:

* License
* Dependencies
* Maintainers
* Description

[Collecting Information](broken-reference)[License/Maintainers](broken-reference)

For this package, its straight forward. GitHub has given us a helping hand, and detected the [license](https://github.com/instaloader/instaloader/blob/master/LICENSE) as MIT. We can also see there is a license file:

```
:~/kali/packages/instaloader$ cat LICENSE
The MIT License (MIT)

Copyright (c) 2016-2019 Alexander Graf and André Koch-Kramer.
[...]
:~/kali/packages/instaloader$
```

Reading the license, we can see there are two authors which are given credit too: `Alexander Graf` and `André Koch-Kramer`. However, we don’t have a method of contact for them. We continue to explore the rest of the git repository, looking for something which may give us more authors so we can give credit to them. There isn’t a fixed structure in place, however there are some things to check and look out for:

* `README*` - authors may put contact information here
  * A few examples could be: `README`, `README.txt`, `README.MD` `README.MKDOCS`, or `Readme.txt`
* `AUTHOR*` - They may have a dedicated file for author information
* `CREDIT*` - They may have a dedicated file to who they give credit to
* `LICENSE*` - Like mentioned above, the license file may give author information
* `docs/` - They may place all their documentation in a separate folder
* The “main” starting point of the application may have comments at the top of the file - in this, `instaloader.py`
* Git commits - `git --no-pager log -s --format="%ae" | sort -u`

For our package, we can see:

```
:~/kali/packages/instaloader$ ls
AUTHORS.md  debian  deploy  docs  instaloader  instaloader.py  LICENSE  Pipfile  Pipfile.lock  README.rst  setup.py  test
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ ls docs/
as-module.rst    codesnippets      contributing.rst  installation.rst  logo.svg   requirements.txt             _templates
basic-usage.rst  codesnippets.rst  favicon.ico       logo_heading.png  Makefile   sphinx_autodoc_typehints.py  troubleshooting.rst
cli-options.rst  conf.py           index.rst         logo.png          README.md  _static
:~/kali/packages/instaloader$
```

As it turns out, there is: `AUTHORS.md`, `docs/`, `instaloader.py`, and `README.rst`, so we have a few places to look at. Starting with `AUTHORS.md`, we can see the authors name and their method of contact:

```
:~/kali/packages/instaloader$ cat AUTHORS.md
Authors
=======

Instaloader is written by

- Alexander Graf (@aandergr)
- André Koch-Kramer (@Thammus)
- Lars Lindqvist (@e5150)
:~/kali/packages/instaloader$
```

So rather than an email address, it appears to be a username (could be just for GitHub, or a generic Internet handle). This is enough for us to go forward (even though its not ideal).

Another trick we could try is looking to see if they used a “legit” email address with git:

```
:~/kali/packages/instaloader$ git clone https://github.com/instaloader/instaloader/ /tmp/instaloader
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cd /tmp/instaloader/
:/tmp/instaloader$ git --no-pager log -s --format="%ae" | sort -u | grep -v '@users.noreply.github.com'
[...]
:/tmp/instaloader$
:/tmp/instaloader$ cd ~/kali/packages/instaloader/
:~/kali/packages/instaloader$
```

It doesn’t appear so. Was worth a try!

[Dependencies/Maintainers](broken-reference)

We need to see what is required to be installed on the machine in order for the application to work. Either pre-installed or will be installed using the application.

Some starting places to look at for this information:

* `README*`
* `SETUP*`
* `INSTALL*`
* `docs/`

There is a README for this application, but it just says how to install the application, rather than how to build it/compile from source:

```
:~/kali/packages/instaloader$ grep -C 3 -i install README.rst

::

    $ pip3 install instaloader

    $ instaloader profile [profile ...]

:~/kali/packages/instaloader$
```

Exploring the [pip option](https://pypi.org/project/instaloader/) is something we could do, but out of scope for this guide.

Next we spot `setup.py`, which contains a lot of useful information:

```
:~/kali/packages/instaloader$ cat setup.py
#!/usr/bin/env python3
[...]
if sys.version_info < (3, 5):
    sys.exit('Instaloader requires Python >= 3.5.')

requirements = ['requests>=2.4']

if platform.system() == 'Windows' and sys.version_info < (3, 6):
    requirements.append('win_unicode_console')
[...]
    url='https://instaloader.github.io/',
    license='MIT',
    author='Alexander Graf, André Koch-Kramer',
    author_email=', ',
    description='Download pictures (or videos) along with their captions and other metadata '
                'from Instagram.',
    long_description=open(os.path.join(SRC, 'README.rst')).read(),
    install_requires=requirements,
    python_requires='>=3.5',
[...]
:~/kali/packages/instaloader$
```

We managed to get the following information from this:

* From the shebang, we can see its Python 3 (`#!/usr/bin/env python3`).
* We can see it wants Python 3.5 or higher
* We can see it wants `requests` and for it to be `v2.4` or higher
* We can see if its on Windows, it requires another dependency, but we are Linux, so not the case
* We can see the program’s home URL
* We can see the license (MIT)
* We can see the authors and their email addresses
* We can get a description of the program

Handy!

When packing, we are building a standalone package, which needs to be able to install offline. Something else which needs to be kept in mind, other systems package management systems, such as Python’s pip, or ruby’s gems. Any of these dependencies also need to be in the main OS package management. In our case, we need Python’s `requests`.

We have two ways of searching for it. We can use either:

* [pkg.kali.org](https://pkg.kali.org/)
* `apt-cache`

But we also need to know what we are searching for. There is a naming convention, but if you are un-sure, doing multiple searches may help:

* `requests`
* `python-requests`
* `python3-requests`

We will stick with the command line option for the time being.

Doing just `requests` gives a little too many results:

```
:~/kali/packages/instaloader$ apt-cache search requests | wc -l
561
:~/kali/packages/instaloader$
```

So we need to do better to shorten the list, by just searching **the short version** of the description (we will cover this more later, but its the visible part of the output):

```
:~/kali/packages/instaloader$ apt-cache search --names-only requests | wc -l
19
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ apt-cache search --names-only python-requests
python-requests-cache-doc - persistent cache for requests library (doc)
python-requests-doc - elegant and simple HTTP library for Python (Documentation)
python-requests-mock-doc - mock out responses from the requests package - doc
python-requests-oauthlib-doc - module providing OAuthlib auth support for requests (Common Documentation)
python-requests-toolbelt-doc - Utility belt for python3-requests (documentation)
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ apt-cache search --names-only python-requests | grep -vi 'doc'
:~/kali/packages/instaloader$
```

After removing the documentation from the results, we don’t get any results. So on with the next search!:

```
:~/kali/packages/instaloader$ apt-cache search --names-only python3-requests
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
:~/kali/packages/instaloader$
```

The first result, `python3-requests`, looks exactly right! We can look closer:

```
:~/kali/packages/instaloader$ apt-cache show python3-requests
Package: python3-requests
Source: requests
Version: 2.23.0+dfsg-2
[...]
:~/kali/packages/instaloader$
```

And we can see its version is `2.23.0`, which is higher than than `2.4`, so we don’t need to update the package. This will be covered in another guide when required.

[Maintainers](broken-reference)

While doing the other parts, we have discovered the authors and maintainers of the software, so we don’t need to do anything extra for this.

[Description](broken-reference)

There are two descriptions that we need to supply, a long description and a short description. When we look at the GitHub page we can see an about section that we can use for the short description. For the long description, we can use the description in the README.

[![](<../../../.gitbook/assets/instaloader 01.png>)](<../../../.gitbook/assets/instaloader 01.png>)

We also have a value from the `setup.py`.

[Editing Package Source Code](broken-reference)

Now that we have that information copied down, we can start to populate the files in the `debian/` folder we created with `dh_make`.

More information on the subject can be found on the [Debian documentation](https://www.debian.org/doc/manuals/maint-guide/dreq.en.html).

[Changelog](broken-reference)

If we followed the documentation on [setting up a packaging environment](broken-reference), the only values we will need to alter would be **distribution** (from `UNRELEASED` to `kali-dev`), **version** (from `4.4.4-1` to `4.4.4-0kali1`) and the **log entry**:

```
:~/kali/packages/instaloader$ cat debian/changelog
instaloader (4.4.4-1) UNRELEASED; urgency=medium

  * Initial release (Closes: #nnnn)  <nnnn is the bug number of your ITP>

 -- Joseph O'Gorman <>  Thu, 02 Jul 2020 17:59:47 -0400
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ vim debian/changelog
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cat debian/changelog
instaloader (4.4.4-0kali1) kali-dev; urgency=medium

  * Initial release

 -- Joseph O'Gorman <>  Thu, 02 Jul 2020 17:59:47 -0400
:~/kali/packages/instaloader$
```

[Control](broken-reference)

This file is the metadata for the package, and contains a lot of information.

More information on the subject can be found on the [Debian documentation](https://www.debian.org/doc/manuals/maint-guide/dreq.en.html).

Out of the box, it will look a little like this:

```
:~/kali/packages/instaloader$ cat debian/control
Source: instaloader
Section: unknown
Priority: optional
Maintainer: Joseph O'Gorman <>
Rules-Requires-Root: no
Build-Depends:
 debhelper-compat (= 13)
Standards-Version: 4.6.1
Homepage: <insert the upstream URL, if relevant>
#Vcs-Browser: https://salsa.debian.org/debian/instaloader
#Vcs-Git: https://salsa.debian.org/debian/instaloader.git

Package: instaloader
Architecture: any
Depends:
 ${misc:Depends},
 ${shlibs:Depends},
Description: <insert up to 60 chars description>
 <Insert long description, indented with spaces.>
:~/kali/packages/instaloader$
```

So we can see a few things that need updating:

* `Section` - we set this to be misc, or if we know for sure it should be another section based off of the sections in [Debian testing](https://packages.debian.org/testing/) we can set it to that section
* `Maintainer` - we switch to be the Kali team, rather than an individual
* `Uploaders` - this is the individual(s) who are responsible for packaging up the application
* `Build-Depends` - what packages are required to BUILD the package
* `Homepage` - where is the tool located on the Internet
* `Vcs-Browser` - package source code to view online
* `Vcs-Git` - package source code location
* `Architecture` - what machines can this work on
* `Depends` - what other packages are required for this package to work
* `Description` - short and long description

Most of this we have now figured out from before, so it should make it easier to fill in. We went ahead and created a remote empty git repository on our GitLab account. In our example, this is the end result:

```
:~/kali/packages/instaloader$ vim debian/control
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cat debian/control
Source: instaloader
Section: misc
Priority: optional
Maintainer: Kali Developers <>
Uploaders: Joseph O'Gorman <>
Rules-Requires-Root: no
Build-Depends:
 debhelper-compat (= 13),
 dh-python,
 python3-all,
 python3-requests,
 python3-setuptools,
Standards-Version: 4.6.1
Homepage: https://instaloader.github.io/
Vcs-Browser: https://gitlab.com/kalilinux/packages/instaloader
Vcs-Git: https://gitlab.com/kalilinux/packages/instaloader.git

Package: instaloader
Architecture: all
Depends:
 python3-requests,
 ${misc:Depends},
 ${python3:Depends},
Description: Download media along with their metadata from Instagram
 Downloads public and private profiles, hashtags, user stories, feeds
   and saved media
 Downloads comments, geotags and captions of each post.
 Automatically detects profile name changes and renames the target
   directory accordingly
 Allows fine-grained customization of filters and where to store
   downloaded media
:~/kali/packages/instaloader$
```

NOTE: The `Build-Depends` & `Depends` are indented with one space (and end with commas). The `Description` is also indentend with one space.

There is a lot going on here, so lets point out a few things

Something to keep in mind with the formatting of the **long descriptions**, at about every 70 characters in (to the nearest whole word), we would put a new line, to help keep the formatting under control.

Now onto the dependencies, of which we have: **Build** & **Package**. For the build-dependencies of Python 3 we will have to have four things:

* `debhelper-compat`
* `dh-python`
* `python3-all`
* `python3-setuptools`

In a separate guide there will be an explanation as to why these are included, however only the first two are going to be a staple of Python 3 packaging as the latter two are for more specific cases.

In our application, we have another one, `python3-requests`, which we got from `setup.py` and that is a requirement from the application. Typically, if there was not a `setup.py` file, we would not need to include `python3-requests` in our “Build-Depends”. However, due to the `setup.py` file, we will need to include `python3-requests` in both the “Build-Depends” as well as the package “Depends”. This ensures these packages are always on the system when we install our package (especially handy when using “sbuild”).

The `debhelper-compat` level determines how the package will be built. The higher the compat level, the newer the version. Newer versions have certain menial tasks done automatically, so this should not be lowered.

The package dependencies are relatively straightforward. We get rid of the `${shlibs:Depends}` as we are packaging up a Python tool, and instead replace it with the python3 depends version `${python3:Depends}`. We also ensure that `python3-requests` is included as the tool requires this. No other dependencies are needed by this tool, so we are done.

The final thing we need to ensure we change is the architecture from **any** to **all**, as this tool can be installed on all architectures.

[Copyright](broken-reference)

Everything that gets created has an original author. They control what happens with it and it needs to be respected. We can call out this in the copyright file.

More information on the subject can be found on the [Debian documentation](https://www.debian.org/doc/manuals/maint-guide/dreq.en.html) and [here](https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/).

Below is the skeleton template output (with comments removed):

```
:~/kali/packages/instaloader$ grep -v '#' debian/copyright
Format: https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/
Source: <url://example.com>
Upstream-Name: instaloader
Upstream-Contact: <preferred name and address to reach the upstream project>

Files:
 *
Copyright:
 <years> <put author's name and email here>
 <years> <likewise for another author>
License: <special license>
 <Put the license of the package here indented by 1 space>
 <This follows the format of Description: lines in control file>
 .
 <Including paragraphs>

Files:
 debian/*
Copyright:
 2020 Joseph O'Gorman <>
License: GPL-2+
 This package is free software; you can redistribute it and/or modify
 it under the terms of the GNU General Public License as published by
 the Free Software Foundation; either version 2 of the License, or
 (at your option) any later version.
 .
 This package is distributed in the hope that it will be useful,
 but WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 GNU General Public License for more details.
 .
 You should have received a copy of the GNU General Public License
 along with this program. If not, see <https://www.gnu.org/licenses/>
Comment:
 On Debian systems, the complete text of the GNU General
 Public License version 2 can be found in "/usr/share/common-licenses/GPL-2".

:~/kali/packages/instaloader$
```

The original tool’s author has ownership on their work, and the work we have put into creating the package belongs to us. After updating it, it looks like the following:

```
:~/kali/packages/instaloader$ vim debian/copyright
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cat debian/copyright
Format: https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/
Source: https://github.com/instaloader/instaloader
Upstream-Name: instaloader

Files: *
Copyright:
 2016-2020 Alexander Graf <>
 2016-2020 André Koch-Kramer <>
License: MIT

Files: debian/*
Copyright: 2020 Joseph O'Gorman <>
License: MIT

License: MIT
 The MIT License
 Permission is hereby granted, free of charge, to any person obtaining a copy
 of this software and associated documentation files (the "Software"), to deal
 in the Software without restriction, including without limitation the rights to
 use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
 of the Software, and to permit persons to whom the Software is furnished to do
 so, subject to the following conditions:
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

:~/kali/packages/instaloader$
```

We altered the following:

* We removed an optional parameter (`Upstream-Contact`), as that is touched on in the copyright file.
* We put in the homepage of the application to `Source`
* Put the two authors name and addresses from `setup.py`. The dates came from the `LICENSE` file
* Rather than putting the whole block of MIT license text directly after, we placed it towards the end of the file, and gave a header to it.
* We replaced the `GPL-2+` used as default for the packaging section with the **same** `MIT` license, which is used in the application. This is the standard for Debian packages (packaging work should match the application’s license).

[Rules](broken-reference)

This file is a Makefile, for building the Debian package.

More information on the subject can be found on the [Debian documentation](https://www.debian.org/doc/manuals/maint-guide/dreq.en.html).

The output of the template looks like the following:

```
:~/kali/packages/instaloader$ cat debian/rules
#!/usr/bin/make -f

# See debhelper(7) (uncomment to enable).
# Output every command that modifies files on the build system.
#export DH_VERBOSE = 1


# See FEATURE AREAS in dpkg-buildflags(1).
#export DEB_BUILD_MAINT_OPTIONS = hardening=+all

# See ENVIRONMENT in dpkg-buildflags(1).
# Package maintainers to append CFLAGS.
#export DEB_CFLAGS_MAINT_APPEND  = -Wall -pedantic
# Package maintainers to append LDFLAGS.
#export DEB_LDFLAGS_MAINT_APPEND = -Wl,--as-needed


%:
	dh 


# dh_make generated override targets.
# This is an example for Cmake (see <https://bugs.debian.org/641051>).
#override_dh_auto_configure:
#	dh_auto_configure -- \
#	-DCMAKE_LIBRARY_PATH=$(DEB_HOST_MULTIARCH)

:~/kali/packages/instaloader$
```

So there are a lot of items which are pre-commented out, that may be handy for debugging & troubleshooting. Other than the shebang (`#!/usr/bin/make -f`), there is only two other lines which are currently in use:

```
%:
	dh 
```

Which is a wildcard (`%`), and feed in all the arguments into `dh`.

What needs to go here now starts to depend on the program and how complex it is. As our program is a python application we are going to have to tell it to build with `python3`. We also need to tell it to use `pybuild` to build, as we have a `setup.py` file included in the source of the application. If there was not a `setup.py` file, we would not add this flag. We also need to tell PyBuild the name of the application. This looks like:

```
:~/kali/packages/instaloader$ vim debian/rules
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cat debian/rules
#!/usr/bin/make -f

#export DH_VERBOSE = 1
export PYBUILD_NAME = instaloader

%:
	dh  --with python3 --buildsystem=pybuild
:~/kali/packages/instaloader$
```

NOTE: It uses TAB for indentation, as its a Makefile.

[Watch](broken-reference)

An additional file which we highly recommend to include is a `watch` file. This points to upstream, and is then used to detect if there is a more recent version of the application than what is packaged. This is useful when doing updates to packages.

For more information, and example formats, please see the [Debian wiki](https://wiki.debian.org/debian/watch). Using this wiki, we can see there is an example for GitHub which is where our project is stored - [github.com/instaloader/instaloader/](https://github.com/instaloader/instaloader/):

```
version=4
opts=filenamemangle=s/.+\/v?(\d\S+)\.tar\.gz/<project>-$1\.tar\.gz/ \
  https://github.com/<user>/<project>/tags .*/v?(\d\S+)\.tar\.gz
```

So lets now alter it to fit our needs:

```
:~/kali/packages/instaloader$ vim debian/watch
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cat debian/watch
version=4
opts=filenamemangle=s/.+\/v?(\d\S+)\.tar\.gz/instaloader-$1\.tar\.gz/ \
  https://github.com/instaloader/instaloader/tags .*/v?(\d\S+)\.tar\.gz
:~/kali/packages/instaloader$
```

NOTE: This has two spaces for any indentation

So let’s do a quick check to see if its working right:

```
:~/kali/packages/instaloader$ uscan -vv --no-download
[...]
uscan info: Found the following matching hrefs on the web page (newest first):
   /instaloader/instaloader/archive/v4.4.4rc3.tar.gz (4.4.4rc3) index=4.4.4rc3-1
   /instaloader/instaloader/archive/v4.4.4rc2.tar.gz (4.4.4rc2) index=4.4.4rc2-1
   /instaloader/instaloader/archive/v4.4.4rc1.tar.gz (4.4.4rc1) index=4.4.4rc1-1
   /instaloader/instaloader/archive/v4.4.4.tar.gz (4.4.4) index=4.4.4-1
   /instaloader/instaloader/archive/v4.4.3.tar.gz (4.4.3) index=4.4.3-1
[...]
    $newversion  = 4.4.4rc3
    $lastversion = 4.4.4
[...]
uscan: Newest version of instaloader on remote site is 4.4.4rc3, local version is 4.4.4
uscan:    => Newer package available from
      https://github.com/instaloader/instaloader/archive/v4.4.4rc3.tar.gz
uscan info: Scan finished
:~/kali/packages/instaloader$
```

Looks like its not! Its correctly detected all the versions, but its not sorted the order correctly (due to the release candidate). We know this by going to the [release page](https://github.com/instaloader/instaloader/tags):

[![](<../../../.gitbook/assets/instaloader 02.png>)](<../../../.gitbook/assets/instaloader 02.png>)

Looking back at the [Debian wiki](https://wiki.debian.org/debian/watch), there is a section called [Common mistakes](https://wiki.debian.org/debian/watch#Common\_mistakes):

> Not mangling upstream versions that are alphas, betas or release candidates to make them sort before the final release. The solution is to use “uversionmangle” like this:

```
opts=uversionmangle=s/(\d)[_\.\-\+]?((RC|rc|pre|dev|beta|alpha)\d*)$/$1~$2/
```

However, we need to edit it a bit to fit Instaloader. This can be figured out through trial and error using the above uversionmangle as the base.

Let’s see how it works:

```
:~/kali/packages/instaloader$ vim debian/watch
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cat debian/watch
version=4
opts=uversionmangle=s/(\d)[_\.\-\+]?((RC|rc|pre|dev|beta|alpha|a)\d*)$// \
  https://github.com/instaloader/instaloader/tags .*/v?(\d\S+)\.tar\.gz
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ uscan -vv --no-download
[...]
uscan info: Newest version of instaloader on remote site is 4.4.4, local version is 4.4.4
uscan info:    => Package is up to date for from
      https://github.com/instaloader/instaloader/archive/v4.4.4.tar.gz
uscan info: Scan finished
:~/kali/packages/instaloader$
```

Success!

[.Install & Helper-Scripts](broken-reference)

Everything we have done so far would just be for building the package, but we haven’t said how to install the application:

```
:~/kali/packages/instaloader$ vim debian/instaloader.install
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cat debian/instaloader.install
instaloader.py usr/share/instaloader/
instaloader usr/share/instaloader/
:~/kali/packages/instaloader$
```

NOTE: There is no leading slash in the target directory

We can go forward with this, but it may not behave like we were expecting. This is because we don’t have anything in `$PATH`, so if we went to the command line and tried typing in `instaloader.py` its not going to work (also it has the file extension, `.py`). The solution is to create a **helper-script**, which is placed into `$PATH` (and we include in the `.install` file):

```
:~/kali/packages/instaloader$ mkdir -p debian/helper-script/
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ vim debian/helper-script/instaloader
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cat debian/helper-script/instaloader
#!/bin/sh
exec python3 /usr/share/instaloader/instaloader.py ""
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ vim debian/instaloader.install
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ cat debian/instaloader.install
instaloader.py usr/share/instaloader/
instaloader usr/share/instaloader/
debian/helper-script/instaloader usr/bin/
:~/kali/packages/instaloader$
```

With that, all the necessary `debian/` files are added. Time to build!

[Packing Up](broken-reference)

Time to bundle everything into a file. We are going to use **sbuild** to create the package. This has its pros and cons. One of the pros is that if it builds here, it will also build elsewhere as its meant for build daemons. The down side is, it will require access to a network repository as it will try and handle detecting and installing any dependencies missing in the chroot, making it slower to build.

If you don’t want to use **sbuild**, just drop it from the arguments (e.g. `gbp buildpackage`), However, you will be required then to install what’s in `debian/control` in the `Build-Depends` section (e..g `sudo apt install -y dh-python python3-all python3-setuptools python3-requests`).

So lets give sbuild a try:

```
:~/kali/packages/instaloader$ gbp buildpackage --git-builder=sbuild
gbp:error: Can't determine package type: Failed to read changelog: can't get HEAD:debian/changelog: fatal: path 'debian/changelog' exists on disk, but not in 'HEAD'
:~/kali/packages/instaloader$
```

Oops! We haven’t committed our changes to git. Shame on us.

If we wanted to, we could bypass this by doing `gbp buildpackage --git-builder=sbuild --git-export=WC`, which would allow us to test out our values in `debian/` before committing to it, rather than cluttering up the git history with various debugging/troubleshooting commits. Then when we have our package in a working state, we can then commit to git, and try again, like so:

```
:~/kali/packages/instaloader$ git status
On branch kali/master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        debian/

nothing added to commit but untracked files present (use "git add" to track)
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git add debian/
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git commit -m "Initial release"
[kali/master 10a9e96] Add debian/ files
 8 files changed, 94 insertions(+)
 create mode 100644 debian/changelog
 create mode 100644 debian/control
 create mode 100644 debian/copyright
 create mode 100755 debian/helper-script/instaloader
 create mode 100644 debian/instaloader.install
 create mode 100755 debian/rules
 create mode 100644 debian/source/format
 create mode 100644 debian/watch
:~/kali/packages/instaloader$
```

Let’s try and build again:

NOTE: You may not get the following error (as it depends on how “clean” your OS is):

```
:~/kali/packages/instaloader$ gbp buildpackage --git-builder=sbuild
gbp:info: Exporting 'HEAD' to '/home/kali/kali/build-area/instaloader-tmp'
gbp:info: Moving '/home/kali/kali/build-area/instaloader-tmp' to '/home/kali/kali/build-area/instaloader-4.4.4'
gbp:info: Performing the build
dh clean --with python3 --buildsystem=pybuild
dh: error: unable to load addon python3: Can't locate Debian/Debhelper/Sequence/python3.pm in @INC (you may need to install the Debian::Debhelper::Sequence::python3 module) (@INC contains: /etc/perl /usr/local/lib/x86_64-linux-gnu/perl/5.30.3 /usr/local/share/perl/5.30.3 /usr/lib/x86_64-linux-gnu/perl5/5.30 /usr/share/perl5 /usr/lib/x86_64-linux-gnu/perl-base /usr/lib/x86_64-linux-gnu/perl/5.30 /usr/share/perl/5.30 /usr/local/lib/site_perl) at (eval 25) line 1.
BEGIN failed--compilation aborted at (eval 25) line 1.
make: *** [debian/rules:7: clean] Error 255
E: Failed to clean source directory /home/kali/kali/build-area/instaloader-4.4.4 (/home/kali/kali/build-area/instaloader_4.4.4-0kali1.dsc)
gbp:error: 'sbuild' failed: it exited with 1
:~/kali/packages/instaloader$
```

If you see the above error, this is because `dh-python` is missing from our OS. We can quickly fix this by doing:

```
:~/kali/packages/instaloader$ sudo apt install -y dh-python
:~/kali/packages/instaloader$
```

So, one more try and building:

```
:~/kali/packages/instaloader$ gbp buildpackage --git-builder=sbuild
gbp:info: Exporting 'HEAD' to '/home/kali/kali/build-area/instaloader-tmp'
gbp:info: Moving '/home/kali/kali/build-area/instaloader-tmp' to '/home/kali/kali/build-area/instaloader-4.4.4'
gbp:info: Performing the build
dh clean --with python3 --buildsystem=pybuild
[...]

+------------------------------------------------------------------------------+
| Package contents                                                             |
+------------------------------------------------------------------------------+

[...]

Install lintian build dependencies (apt-based resolver)
-------------------------------------------------------

[...]

E: instaloader source: source-is-missing [docs/_static/bootstrap-4.1.3.bundle.min.js]
W: instaloader: no-manual-page [usr/bin/instaloader]

E: Lintian run failed (runtime error)

[...]

+------------------------------------------------------------------------------+
| Summary                                                                      |
+------------------------------------------------------------------------------+

Build Architecture: amd64
Build Type: full
Build-Space: 2460
Build-Time: 5
Distribution: kali-dev
Host Architecture: amd64
Install-Time: 37
Job: /home/kali/kali/build-area/instaloader_4.4.4-0kali1.dsc
Lintian: error
Machine Architecture: amd64
Package: instaloader
Package-Time: 45
Source-Version: 4.4.4-0kali1
Space: 2460
Status: successful
Version: 4.4.4-0kali1
--------------------------------------------------------------------------------
Finished at 2020-07-03T15:51:09Z
Build needed 00:00:45, 2460k disk space

:~/kali/packages/instaloader$
```

The output here is very long, so we have truncated it, but we can see its being built successfully. Even with an error, warning, and information from `lintian`!

Let’s double check to see what got created:

```
:~/kali/packages/instaloader$ ls ~/kali/build-area/instaloader*
/home/kali/kali/build-area/instaloader_4.4.4-0kali1_all.deb          /home/kali/kali/build-area/instaloader_4.4.4-0kali1.debian.tar.xz
/home/kali/kali/build-area/instaloader_4.4.4-0kali1_amd64.build      /home/kali/kali/build-area/instaloader_4.4.4-0kali1.dsc
/home/kali/kali/build-area/instaloader_4.4.4-0kali1_amd64.buildinfo  /home/kali/kali/build-area/instaloader_4.4.4.orig.tar.gz
/home/kali/kali/build-area/instaloader_4.4.4-0kali1_amd64.changes
:~/kali/packages/instaloader$
```

We have output!

[Making Lintian Happy](broken-reference)

For more information, see [Debian’s documentation](https://www.debian.org/doc/manuals/maint-guide/checkit.en.html).

Let’s try to understand the error `E: instaloader source: source-is-missing [docs/_static/bootstrap-4.1.3.bundle.min.js]`:

```
:~/kali/packages/instaloader$ lintian-explain-tags source-is-missing
N:
E: source-is-missing
N: 
N:   The source of the following file is missing. Lintian checked a few possible paths to find the source, and did not find it.
N:   
N:   Please repack your package to include the source or add it to "debian/missing-sources" directory.
N:   
N:   Please note, that very-long-line-length-in-source-file tagged files are likely tagged source-is-missing. It is a feature not a bug.
N: 
N:   Visibility: error
N:   Show-Always: no
N:   Check: files/source-missing
N: 
:~/kali/packages/instaloader$
```

The issue with the file `docs/_static/bootstrap-4.1.3.bundle.min.js` is that it’s a minified Javascript. It’s not human readable, it can’t be modified, therefore it’s not considered as a source file. As Lintian suggests, we can provide the source for this file in `debian/missing-sources`, however as we do not have the source handy we should explore other options. For this guide we will focus on Lintian overrides. Because the offending file is in the `docs` directory, which, if we investigate the included files, is what Instaloader uses to host their [documentation site](https://instaloader.github.io/) pages, we can ignore this file and tell Lintian to as well.

To do this we will create the file `instaloader.lintian-overrides` located in the `debian` directory. From here we can copy and paste the error message from the `:` on. While we are here, we may as well ignore the warning about `no-manual-page`. Here is our resulting file:

```
:~/kali/packages/instaloader$ vim debian/instaloader.lintian-overrides

:~/kali/packages/instaloader$

:~/kali/packages/instaloader$ cat debian/instaloader.lintian-overrides
source-is-missing [docs/_static/bootstrap-4.1.3.bundle.min.js]
no-manual-page [usr/bin/instaloader]

:~/kali/packages/instaloader$
```

We can now commit our changes and rebuild the package with the same command and see if it was successful with no error:

```
:~/kali/packages/instaloader$ gbp buildpackage --git-builder=sbuild
[...]

+------------------------------------------------------------------------------+
| Package contents                                                             |
+------------------------------------------------------------------------------+

[...]

Install lintian build dependencies (apt-based resolver)
-------------------------------------------------------

[...]

Running lintian...
E: instaloader source: source-is-missing [docs/_static/bootstrap-4.1.3.bundle.min.js]
I: instaloader: unused-override source-is-missing [docs/_static/bootstrap-4.1.3.bundle.min.js] [usr/share/lintian/overrides/instaloader:2]
N: 0 hints overridden; 1 unused override

E: Lintian run failed (runtime error)

[...]
:~/kali/packages/instaloader$
```

Uh oh! It looks like it still failed, and that it didn’t even use our override for the `source-is-missing` error! If we look closer, we can see a difference between the previous warning we were getting about `no-manual-page` and `source-is-missing`. The section before the `:`, telling us the level of error and the package name, includes `source` in our `source-is-missing` error. This is because the issue resides in the _source package_, or the imported package, rather than the output, or the _binary package_. To solve this we will need to create a new `source` directory in `debian/` and a new `lintian-overrides` file. Lets do that now:

```
:~/kali/packages/instaloader$ mkdir debian/source/

:~/kali/packages/instaloader$

:~/kali/packages/instaloader$ vim debian/source/lintian-overrides

:~/kali/packages/instaloader$

:~/kali/packages/instaloader$ cat debian/source/lintian-overrides
source-is-missing [docs/_static/bootstrap-4.1.3.bundle.min.js]

:~/kali/packages/instaloader$
```

Don’t forget to remove the override from our previous file as well!

```
:~/kali/packages/instaloader$ vim debian/instaloader.lintian-overrides

:~/kali/packages/instaloader$

:~/kali/packages/instaloader$ cat debian/instaloader.lintian-overrides
no-manual-page [usr/bin/instaloader]

:~/kali/packages/instaloader$
```

We can once more commit our changes and rebuild the package and see it was successful with no error:

```
:~/kali/packages/instaloader$ gbp buildpackage --git-builder=sbuild
[...]

+------------------------------------------------------------------------------+
| Package contents                                                             |
+------------------------------------------------------------------------------+

[...]

Install lintian build dependencies (apt-based resolver)
-------------------------------------------------------

[...]

Running lintian...

I: Lintian run was successful.

[...]
:~/kali/packages/instaloader$
```

[Manual Install](broken-reference)

Let’s now give our package a test drive:

```
:~/kali/packages/instaloader$ sudo apt install ~/kali/build-area/instaloader_4.4.4-0kali1_all.deb
Selecting previously unselected package instaloader.
(Reading database ... 154513 files and directories currently installed.)
Preparing to unpack .../instaloader_4.4.4-0kali1_all.deb ...
Unpacking instaloader (4.4.4-0kali1) ...
Setting up instaloader (4.4.4-0kali1) ...
Processing triggers for kali-menu (2020.3.0) ...
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ instaloader
usage:
instaloader.py [--comments] [--geotags]
               [--stories] [--highlights] [--tagged] [--igtv]
               [--login YOUR-USERNAME] [--fast-update]
               profile | "#hashtag" | %%location_id | :stories | :feed | :saved
instaloader.py --help
:~/kali/packages/instaloader$
```

Success!

This is looking good (not perfect), and eagle eye spotters may be able to spot why (in the output) - there is the file extension in the output (`instaloader.py`), yet the command used to call it doesn’t have it (`instaloader`). We are going to need to either patch the application or find a different way to call the application to address this. But this will be covered in another guide.

Let’s now make sure everything is in git locally, before we push it out to the remote repository (the one we defined in `debian/control`):

```
:~/kali/packages/instaloader$ git status
On branch kali/master
nothing to commit, working tree clean
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git branch -v
* kali/master  10a9e96 Use lintian-override to clear all warnings and errors
  pristine-tar 439fe30 pristine-tar data for instaloader_4.4.4.orig.tar.gz
  upstream     494f718 New upstream version 4.4.4
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git remote -v
:~/kali/packages/instaloader$
```

We don’t (yet) have a remote repository setup, so we go to GitLab and [create a new project](https://gitlab.com/projects/new) before continuing.

Afterwards:

```
:~/kali/packages/instaloader$ git remote add origin :kalilinux/packages/instaloader.git
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git remote -v
origin  :kalilinux/packages/instaloader.git (fetch)
origin  :kalilinux/packages/instaloader.git (push)
:~/kali/packages/instaloader$
```

Now we need to send our local work to the new remote repository (and don’t forget the tags):

```
:~/kali/packages/instaloader$ git push --all
Enumerating objects: 95, done.
Counting objects: 100% (95/95), done.
Delta compression using up to 2 threads
Compressing objects: 100% (88/88), done.
Writing objects: 100% (95/95), 291.16 KiB | 7.46 MiB/s, done.
Total 95 (delta 1), reused 0 (delta 0), pack-reused 0
remote:
remote: To create a merge request for pristine-tar, visit:
remote:   https://gitlab.com/kalilinux/packages/instaloader/-/merge_requests/new?merge_request%5Bsource_branch%5D=pristine-tar
remote:
remote: To create a merge request for upstream, visit:
remote:   https://gitlab.com/kalilinux/packages/instaloader/-/merge_requests/new?merge_request%5Bsource_branch%5D=upstream
remote:
To gitlab.com:kalilinux/packages/instaloader.git
 * [new branch]      kali/master -> kali/master
 * [new branch]      pristine-tar -> pristine-tar
 * [new branch]      upstream -> upstream
:~/kali/packages/instaloader$
:~/kali/packages/instaloader$ git push --tags
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 172 bytes | 172.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
To gitlab.com:kalilinux/packages/instaloader.git
 * [new tag]         upstream/4.4.4 -> upstream/4.4.4
:~/kali/packages/instaloader$
```

At this point now, a ticket can be opened up on the [Kali Linux bug tracker](https://bugs.kali.org/), with a suggestion of the tool & package which you have created, and our tool team will handle it from there.
