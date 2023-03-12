---
description: >-
  Git is a version control system used for tracking changes in source code
  during software development. It allows collaboration and enables rollbacks.
---

# 📦 git

#### git <a href="#git" id="git"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package provides the git main components with minimal dependencies. Additional functionality, e.g. a graphical user interface and revision tree visualizer, tools for interoperating with other VCS’s, or a web interface, is provided as separate git\* packages.

**Installed size:** `43.43 MB`\
**How to install:** `sudo apt install git`

<details>

<summary>Dependencies:</summary>

* git-man
* libc6
* libcurl3-gnutls
* liberror-perl
* libexpat1
* libpcre2-8-0
* perl
* zlib1g

</details>

**git**

Perl interface to the Git version control system The stupid content tracker

```
:~# git -h
usage: git [-v | --version] [-h | --help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--super-prefix=<path>] [--config-env=<name>=<envvar>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone     Clone a repository into a new directory
   init      Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add       Add file contents to the index
   mv        Move or rename a file, a directory, or a symlink
   restore   Restore working tree files
   rm        Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect    Use binary search to find the commit that introduced a bug
   diff      Show changes between commits, commit and working tree, etc
   grep      Print lines matching a pattern
   log       Show commit logs
   show      Show various types of objects
   status    Show the working tree status

grow, mark and tweak your common history
   branch    List, create, or delete branches
   commit    Record changes to the repository
   merge     Join two or more development histories together
   rebase    Reapply commits on top of another base tip
   reset     Reset current HEAD to the specified state
   switch    Switch branches
   tag       Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch     Download objects and refs from another repository
   pull      Fetch from and integrate with another repository or a local branch
   push      Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help <command>' or 'git help <concept>'
to read about a specific subcommand or concept.
See 'git help git' for an overview of the system.
```

***

**git-receive-pack**

Receive what is pushed into the repository

```
:~# git-receive-pack --help
GIT-RECEIVE-PACK(1)               Git Manual               GIT-RECEIVE-PACK(1)

NAME
       git-receive-pack - Receive what is pushed into the repository

SYNOPSIS
       git receive-pack <git-dir>

DESCRIPTION
       Invoked by git send-pack and updates the repository with the
       information fed from the remote end.

       This command is usually not invoked directly by the end user. The UI
       for the protocol is on the git send-pack side, and the program pair is
       meant to be used to push updates to remote repository. For pull
       operations, see git-fetch-pack(1).

       The command allows for creation and fast-forwarding of sha1 refs
       (heads/tags) on the remote end (strictly speaking, it is the local end
       git-receive-pack runs, but to the user who is sitting at the send-pack
       end, it is updating the remote. Confused?)

       There are other real-world examples of using update and post-update
       hooks found in the Documentation/howto directory.

       git-receive-pack honours the receive.denyNonFastForwards config option,
       which tells it if updates to a ref should be denied if they are not
       fast-forwards.

       A number of other receive.* config options are available to tweak its
       behavior, see git-config(1).

OPTIONS
       <git-dir>
           The repository to sync into.

       --http-backend-info-refs
           Used by git-http-backend(1) to serve up
           $GIT_URL/info/refs?service=git-receive-pack requests. See
           --http-backend-info-refs in git-upload-pack(1).

PRE-RECEIVE HOOK
       Before any ref is updated, if $GIT_DIR/hooks/pre-receive file exists
       and is executable, it will be invoked once with no parameters. The
       standard input of the hook will be one line per ref to be updated:

           sha1-old SP sha1-new SP refname LF

       The refname value is relative to $GIT_DIR; e.g. for the master head
       this is "refs/heads/master". The two sha1 values before each refname
       are the object names for the refname before and after the update. Refs
       to be created will have sha1-old equal to 0{40}, while refs to be
       deleted will have sha1-new equal to 0{40}, otherwise sha1-old and
       sha1-new should be valid objects in the repository.

       When accepting a signed push (see git-push(1)), the signed push
       certificate is stored in a blob and an environment variable
       GIT_PUSH_CERT can be consulted for its object name. See the description
       of post-receive hook for an example. In addition, the certificate is
       verified using GPG and the result is exported with the following
       environment variables:

       GIT_PUSH_CERT_SIGNER
           The name and the e-mail address of the owner of the key that signed
           the push certificate.

       GIT_PUSH_CERT_KEY
           The GPG key ID of the key that signed the push certificate.

       GIT_PUSH_CERT_STATUS
           The status of GPG verification of the push certificate, using the
           same mnemonic as used in %G?  format of git log family of commands
           (see git-log(1)).

       GIT_PUSH_CERT_NONCE
           The nonce string the process asked the signer to include in the
           push certificate. If this does not match the value recorded on the
           "nonce" header in the push certificate, it may indicate that the
           certificate is a valid one that is being replayed from a separate
           "git push" session.

       GIT_PUSH_CERT_NONCE_STATUS

           UNSOLICITED
               "git push --signed" sent a nonce when we did not ask it to send
               one.

           MISSING
               "git push --signed" did not send any nonce header.

           BAD
               "git push --signed" sent a bogus nonce.

           OK
               "git push --signed" sent the nonce we asked it to send.

           SLOP
               "git push --signed" sent a nonce different from what we asked
               it to send now, but in a previous session. See
               GIT_PUSH_CERT_NONCE_SLOP environment variable.

       GIT_PUSH_CERT_NONCE_SLOP
           "git push --signed" sent a nonce different from what we asked it to
           send now, but in a different session whose starting time is
           different by this many seconds from the current session. Only
           meaningful when GIT_PUSH_CERT_NONCE_STATUS says SLOP. Also read
           about receive.certNonceSlop variable in git-config(1).

       This hook is called before any refname is updated and before any
       fast-forward checks are performed.

       If the pre-receive hook exits with a non-zero exit status no updates
       will be performed, and the update, post-receive and post-update hooks
       will not be invoked either. This can be useful to quickly bail out if
       the update is not to be supported.

       See the notes on the quarantine environment below.

UPDATE HOOK
       Before each ref is updated, if $GIT_DIR/hooks/update file exists and is
       executable, it is invoked once per ref, with three parameters:

           $GIT_DIR/hooks/update refname sha1-old sha1-new

       The refname parameter is relative to $GIT_DIR; e.g. for the master head
       this is "refs/heads/master". The two sha1 arguments are the object
       names for the refname before and after the update. Note that the hook
       is called before the refname is updated, so either sha1-old is 0{40}
       (meaning there is no such ref yet), or it should match what is recorded
       in refname.

       The hook should exit with non-zero status if it wants to disallow
       updating the named ref. Otherwise it should exit with zero.

       Successful execution (a zero exit status) of this hook does not ensure
       the ref will actually be updated, it is only a prerequisite. As such it
       is not a good idea to send notices (e.g. email) from this hook.
       Consider using the post-receive hook instead.

POST-RECEIVE HOOK
       After all refs were updated (or attempted to be updated), if any ref
       update was successful, and if $GIT_DIR/hooks/post-receive file exists
       and is executable, it will be invoked once with no parameters. The
       standard input of the hook will be one line for each successfully
       updated ref:

           sha1-old SP sha1-new SP refname LF

       The refname value is relative to $GIT_DIR; e.g. for the master head
       this is "refs/heads/master". The two sha1 values before each refname
       are the object names for the refname before and after the update. Refs
       that were created will have sha1-old equal to 0{40}, while refs that
       were deleted will have sha1-new equal to 0{40}, otherwise sha1-old and
       sha1-new should be valid objects in the repository.

       The GIT_PUSH_CERT* environment variables can be inspected, just as in
       pre-receive hook, after accepting a signed push.

       Using this hook, it is easy to generate mails describing the updates to
       the repository. This example script sends one mail message per ref
       listing the commits pushed to the repository, and logs the push
       certificates of signed pushes with good signatures to a logger service:

           #!/bin/sh
           # mail out commit update information.
           while read oval nval ref
           do
                   if expr "$oval" : '0*$' >/dev/null
                   then
                           echo "Created a new ref, with the following commits:"
                           git rev-list --pretty "$nval"
                   else
                           echo "New commits:"
                           git rev-list --pretty "$nval" "^$oval"
                   fi |
                   mail -s "Changes to ref $ref" 
           done
           # log signed push certificate, if any
           if test -n "${GIT_PUSH_CERT-}" && test ${GIT_PUSH_CERT_STATUS} = G
           then
                   (
                           echo expected nonce is ${GIT_PUSH_NONCE}
                           git cat-file blob ${GIT_PUSH_CERT}
                   ) | mail -s "push certificate from $GIT_PUSH_CERT_SIGNER" 
           fi
           exit 0

       The exit code from this hook invocation is ignored, however a non-zero
       exit code will generate an error message.

       Note that it is possible for refname to not have sha1-new when this
       hook runs. This can easily occur if another user modifies the ref after
       it was updated by git-receive-pack, but before the hook was able to
       evaluate it. It is recommended that hooks rely on sha1-new rather than
       the current value of refname.

POST-UPDATE HOOK
       After all other processing, if at least one ref was updated, and if
       $GIT_DIR/hooks/post-update file exists and is executable, then
       post-update will be called with the list of refs that have been
       updated. This can be used to implement any repository wide cleanup
       tasks.

       The exit code from this hook invocation is ignored; the only thing left
       for git-receive-pack to do at that point is to exit itself anyway.

       This hook can be used, for example, to run git update-server-info if
       the repository is packed and is served via a dumb transport.

           #!/bin/sh
           exec git update-server-info

QUARANTINE ENVIRONMENT
       When receive-pack takes in objects, they are placed into a temporary
       "quarantine" directory within the $GIT_DIR/objects directory and
       migrated into the main object store only after the pre-receive hook has
       completed. If the push fails before then, the temporary directory is
       removed entirely.

       This has a few user-visible effects and caveats:

        1. Pushes which fail due to problems with the incoming pack, missing
           objects, or due to the pre-receive hook will not leave any on-disk
           data. This is usually helpful to prevent repeated failed pushes
           from filling up your disk, but can make debugging more challenging.

        2. Any objects created by the pre-receive hook will be created in the
           quarantine directory (and migrated only if it succeeds).

        3. The pre-receive hook MUST NOT update any refs to point to
           quarantined objects. Other programs accessing the repository will
           not be able to see the objects (and if the pre-receive hook fails,
           those refs would become corrupted). For safety, any ref updates
           from within pre-receive are automatically rejected.

SEE ALSO
       git-send-pack(1), gitnamespaces(7)

GIT
       Part of the git(1) suite

Git 2.39.2                        02/16/2023               GIT-RECEIVE-PACK(1)
```

***

**git-shell**

Restricted login shell for Git-only SSH access

```
:~# git-shell -h
fatal: Run with no arguments or with -c cmd
```

***

**git-upload-archive**

Send archive back to git-archive

```
:~# git-upload-archive --help
GIT-UPLOAD-ARCHIVE(1)             Git Manual             GIT-UPLOAD-ARCHIVE(1)

NAME
       git-upload-archive - Send archive back to git-archive

SYNOPSIS
       git upload-archive <repository>

DESCRIPTION
       Invoked by git archive --remote and sends a generated archive to the
       other end over the Git protocol.

       This command is usually not invoked directly by the end user. The UI
       for the protocol is on the git archive side, and the program pair is
       meant to be used to get an archive from a remote repository.

SECURITY
       In order to protect the privacy of objects that have been removed from
       history but may not yet have been pruned, git-upload-archive avoids
       serving archives for commits and trees that are not reachable from the
       repository's refs. However, because calculating object reachability is
       computationally expensive, git-upload-archive implements a stricter but
       easier-to-check set of rules:

        1. Clients may request a commit or tree that is pointed to directly by
           a ref. E.g., git archive --remote=origin v1.0.

        2. Clients may request a sub-tree within a commit or tree using the
           ref:path syntax. E.g., git archive --remote=origin
           v1.0:Documentation.

        3. Clients may not use other sha1 expressions, even if the end result
           is reachable. E.g., neither a relative commit like master^ nor a
           literal sha1 like abcd1234 is allowed, even if the result is
           reachable from the refs.

       Note that rule 3 disallows many cases that do not have any privacy
       implications. These rules are subject to change in future versions of
       git, and the server accessed by git archive --remote may or may not
       follow these exact rules.

       If the config option uploadArchive.allowUnreachable is true, these
       rules are ignored, and clients may use arbitrary sha1 expressions. This
       is useful if you do not care about the privacy of unreachable objects,
       or if your object database is already publicly available for access via
       non-smart-http.

OPTIONS
       <repository>
           The repository to get a tar archive from.

GIT
       Part of the git(1) suite

Git 2.39.2                        02/16/2023             GIT-UPLOAD-ARCHIVE(1)
```

***

**git-upload-pack**

Send objects packed back to git-fetch-pack

```
:~# git-upload-pack --help
GIT-UPLOAD-PACK(1)                Git Manual                GIT-UPLOAD-PACK(1)

NAME
       git-upload-pack - Send objects packed back to git-fetch-pack

SYNOPSIS
       git-upload-pack [--[no-]strict] [--timeout=<n>] [--stateless-rpc]
                         [--advertise-refs] <directory>

DESCRIPTION
       Invoked by git fetch-pack, learns what objects the other side is
       missing, and sends them after packing.

       This command is usually not invoked directly by the end user. The UI
       for the protocol is on the git fetch-pack side, and the program pair is
       meant to be used to pull updates from a remote repository. For push
       operations, see git send-pack.

OPTIONS
       --[no-]strict
           Do not try <directory>/.git/ if <directory> is no Git directory.

       --timeout=<n>
           Interrupt transfer after <n> seconds of inactivity.

       --stateless-rpc
           Perform only a single read-write cycle with stdin and stdout. This
           fits with the HTTP POST request processing model where a program
           may read the request, write a response, and must exit.

       --http-backend-info-refs
           Used by git-http-backend(1) to serve up
           $GIT_URL/info/refs?service=git-upload-pack requests. See "Smart
           Clients" in gitprotocol-http(5) and "HTTP Transport" in the
           gitprotocol-v2(5) documentation. Also understood by git-receive-
           pack(1).

       <directory>
           The repository to sync from.

ENVIRONMENT
       GIT_PROTOCOL
           Internal variable used for handshaking the wire protocol. Server
           admins may need to configure some transports to allow this variable
           to be passed. See the discussion in git(1).

SEE ALSO
       gitnamespaces(7)

GIT
       Part of the git(1) suite

Git 2.39.2                        02/16/2023                GIT-UPLOAD-PACK(1)
```

***

**scalar**

A tool for managing large Git repositories

```
:~# scalar -h
usage: scalar [-C <directory>] [-c <key>=<value>] <command> [<options>]

Commands:
	clone
	list
	register
	unregister
	run
	reconfigure
	delete
	help
	version
	diagnose

```

***

#### git-all <a href="#git-all" id="git-all"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This is a dummy package which brings in all subpackages.

**Installed size:** `973 KB`\
**How to install:** `sudo apt install git-all`

<details>

<summary>Dependencies:</summary>

* git
* git-cvs
* git-doc
* git-email
* git-gui
* git-mediawiki
* git-svn
* gitk
* gitweb

</details>

***

#### git-cvs <a href="#git-cvs" id="git-cvs"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package provides the git cvsimport, cvsexportcommit, and cvsserver tools, which allow Git to read from and write to CVS repositories and offer access over CVS protocol to Git repositories.

The git cvsimport tool can incrementally import from a repository that is being actively developed and only requires remote access over CVS protocol. Unfortunately, in many situations the import leads to incorrect results. For reliable, one-shot imports, cvs2git from the cvs2svn package or parsecvs may be a better fit.

**Installed size:** `1.32 MB`\
**How to install:** `sudo apt install git-cvs`

<details>

<summary>Dependencies:</summary>

* cvsps
* git
* libdbd-sqlite3-perl

</details>

**git-cvsserver**

A CVS server emulator for Git

```
:~# git-cvsserver --help
Unknown option: help
usage: git cvsserver [options] [pserver|server] [<directory> ...]
    --base-path <path>  : Prepend to requested CVSROOT
                          Can be read from GIT_CVSSERVER_BASE_PATH
    --strict-paths      : Don't allow recursing into subdirectories
    --export-all        : Don't check for gitcvs.enabled in config
    --version, -V       : Print version information and exit
    -h, -H              : Print usage information and exit

<directory> ... is a list of allowed directories. If no directories
are given, all are allowed. This is an additional restriction, gitcvs
access still needs to be enabled by the gitcvs.enabled config option.
Alternately, one directory may be specified in GIT_CVSSERVER_ROOT.
```

***

#### git-daemon-run <a href="#git-daemon-run" id="git-daemon-run"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

git-daemon, as provided by the git package, is a simple server for git repositories, ideally suited for read-only updates, i.e. pulling from git repositories through the network. This package provides a runit service for running git-daemon permanently. This configuration is simpler and more reliable than git-daemon-sysvinit, at a cost of being less familiar for administrators accustomed to sysvinit.

**Installed size:** `985 KB`\
**How to install:** `sudo apt install git-daemon-run`

<details>

<summary>Dependencies:</summary>

* adduser
* git
* runit

</details>

***

#### git-daemon-sysvinit <a href="#git-daemon-sysvinit" id="git-daemon-sysvinit"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

git-daemon, as provided by the git package, is a simple server for git repositories, ideally suited for read-only updates, i.e. pulling from git repositories through the network. This package provides a sysvinit service for running git-daemon permanently. Unlike git-daemon-run, this package provides the usual sysvinit service management commands (“service git-daemon start/stop”) for git-daemon.

**Installed size:** `989 KB`\
**How to install:** `sudo apt install git-daemon-sysvinit`

<details>

<summary>Dependencies:</summary>

* adduser
* git
* lsb-base

</details>

***

#### git-doc <a href="#git-doc" id="git-doc"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package provides the documentation.

**Installed size:** `12.69 MB`\
**How to install:** `sudo apt install git-doc`

***

#### git-email <a href="#git-email" id="git-email"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package provides the git-send-email program for sending series of patch emails.

**Installed size:** `1.02 MB`\
**How to install:** `sudo apt install git-email`

<details>

<summary>Dependencies:</summary>

* git

</details>

***

#### git-gui <a href="#git-gui" id="git-gui"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package provides the git graphical user interface.

If aspell is installed, it can check the spelling of commit messages as the user types.

If meld is installed, it can be used for displaying diffs and for interactive merge conflict resolution.

**Installed size:** `2.33 MB`\
**How to install:** `sudo apt install git-gui`

<details>

<summary>Dependencies:</summary>

* git
* tk

</details>

***

#### git-man <a href="#git-man" id="git-man"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package provides reference documentation for use by the ‘man’ utility and the ‘git help’ command.

**Installed size:** `2.05 MB`\
**How to install:** `sudo apt install git-man`

***

#### git-mediawiki <a href="#git-mediawiki" id="git-mediawiki"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package provides the mediawiki remote helper, which allows Git to read from and write to a wiki such as Wikipedia as though it were a remote Git repository, and a ‘git mw’ command that can show a preview of how wiki markup will be rendered before pushing.

**Installed size:** `1.00 MB`\
**How to install:** `sudo apt install git-mediawiki`

<details>

<summary>Dependencies:</summary>

* git
* libdatetime-format-iso8601-perl
* liblwp-protocol-https-perl
* libmediawiki-api-perl

</details>

***

#### git-svn <a href="#git-svn" id="git-svn"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package provides tools for interoperating with Subversion repositories, and importing SVN development history.

**Installed size:** `1.19 MB`\
**How to install:** `sudo apt install git-svn`

<details>

<summary>Dependencies:</summary>

* git
* libsvn-perl
* libterm-readkey-perl
* libyaml-perl

</details>

***

#### gitk <a href="#gitk" id="gitk"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package provides the gitk program, a tcl/tk revision tree visualizer.

**Installed size:** `1.75 MB`\
**How to install:** `sudo apt install gitk`

<details>

<summary>Dependencies:</summary>

* git
* tk

</details>

**gitk**

The Git repository browser

```
:~# gitk -h
application-specific initialization failed: couldn't connect to display ""
Error in startup script: Command-specific options:
 -sync:     Use synchronous mode for display server
 -colormap: Colormap for main window
 -display:  Display to use
 -geometry: Initial geometry for window
 -name:     Name to use for application
 -visual:   Visual for main window
 -use:      Id of window in which to embed application
 --:        Marks the end of the options
 -help:     Print summary of command-line options and abort
    (processing arguments in argv variable)
    invoked from within
"load /usr/lib/x86_64-linux-gnu/libtk8.6.so"
    ("package ifneeded Tk 8.6.13" script)
    invoked from within
"package require Tk"
    (file "/usr/bin/gitk" line 10)
```

***

#### gitweb <a href="#gitweb" id="gitweb"></a>

Git is popular version control system designed to handle very large projects with speed and efficiency; it is used for many high profile open source projects, most notably the Linux kernel.

Git falls in the category of distributed source code management tools. Every Git working directory is a full-fledged repository with full revision tracking capabilities, not dependent on network access or a central server.

This package configures a web interface for browsing git repositories.

If apache2 is installed, the web interface is automatically made available at http://localhost/gitweb. Other servers that support CGI or mod\_perl are supported through manual configuration.

If libcgi-fast-perl is installed, gitweb can also be run over FastCGI (and served by nginx, for example).

**Installed size:** `994 KB`\
**How to install:** `sudo apt install gitweb`

<details>

<summary>Dependencies:</summary>

* git
* libcgi-pm-perl
* perl

</details>

***
