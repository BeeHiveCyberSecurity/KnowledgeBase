---
description: >-
  Apache2 is a popular open-source web server software used for hosting websites
  and applications on the internet. It's reliable, secure and customizable.
---

# 🌐 apache2

### Packages and Binaries:

#### apache2 <a href="#apache2" id="apache2"></a>

The Apache HTTP Server Project’s goal is to build a secure, efficient and extensible HTTP server as standards-compliant open source software. The result has long been the number one web server on the Internet.

Installing this package results in a full installation, including the configuration files, init scripts and support scripts.

**Installed size:** `565 KB`\
**How to install:** `sudo apt install apache2`

<details>

<summary>Dependencies:</summary>

* apache2-bin
* apache2-data
* apache2-utils
* init-system-helpers
* lsb-base
* media-types
* perl
* procps

</details>

**a2disconf**

Enable or disable an apache2 configuration file

```
:~# man a2disconf
A2ENCONF(8)                 System Manager's Manual                A2ENCONF(8)

NAME
       a2enconf, a2disconf - enable or disable an apache2 configuration file

SYNOPSIS
       a2enconf [-q|--quiet] [-m|--maintmode] [ configuration ]

       a2disconf [-q|--quiet] [-m|--maintmode] [-p|--purge] [ configuration ]

DESCRIPTION
       This manual page documents briefly the a2enconf and a2disconf commands.

       a2enconf  is  a  script  that  enables the specified configuration file
       within the apache2 configuration.  It does this  by  creating  symlinks
       within  /etc/apache2/conf-enabled.  Likewise, a2disconf disables a spe-
       cific configuration part by removing those symlinks.  It is not an  er-
       ror  to  enable a configuration which is already enabled, or to disable
       one which is already disabled.

       Note that many configuration file may have  a  dependency  to  specific
       modules.   Unlike module dependencies, these are not resolved automati-
       cally. Configuration fragments stored in the  conf-available  directory
       are  considered  non-essential or being installed and manged by reverse
       dependencies (e.g. web scripts).

OPTIONS
       -q, --quiet
              Don't show informative messages.

       -m, --maintmode
              Enables the maintainer mode, that is the program  invocation  is
              effectuated  automatically  by  a maintainer script. This switch
              should not be used by end users.

       -p, --purge
              When disabling a module, purge all traces of the module  in  the
              internal state data base.

EXIT STATUS
       a2enconf  and  a2disconf  exit  with status 0 if all configurations are
       processed successfully, 1 if errors occur, 2 if an invalid  option  was
       used.

EXAMPLES
              a2enconf security
              a2disconf charset

       Enables Apache security directives stored in the security configuration
       files, and disables the charset configuration.

FILES
       /etc/apache2/conf-available
              Directory with files giving information on available  configura-
              tion files.

       /etc/apache2/conf-enabled
              Directory  with links to the files in conf-available for enabled
              configuration files.

SEE ALSO
       apache2ctl(8), a2enmod(8), a2dismod(8), a2ensite(8), a2dissite(8).

AUTHOR
       This manual page was written by Arno Toell <>  for  the
       Debian  GNU/Linux  distribution, as it is a Debian-specific script with
       the package.

                               14 February 2012                    A2ENCONF(8)
```

***

**a2dismod**

Enable or disable an apache2 module

```
:~# man a2dismod
A2ENMOD(8)                  System Manager's Manual                 A2ENMOD(8)

NAME
       a2enmod, a2dismod - enable or disable an apache2 module

SYNOPSIS
       a2enmod [-q|--quiet] [-m|--maintmode] [ module ]

       a2dismod [-q|--quiet] [-f|--force] [-m|--maintmode] [-p|--purge] [ mod-
       ule ]

DESCRIPTION
       This manual page documents briefly the a2enmod and a2dismod commands.

       a2enmod is a script  that  enables  the  specified  module  within  the
       apache2  configuration.   It  does  this  by  creating  symlinks within
       /etc/apache2/mods-enabled.  Likewise, a2dismod disables a module by re-
       moving  those symlinks.  It is not an error to enable a module which is
       already enabled, or to disable one which is already disabled.

       Note that many modules have, in addition to a .load file, an associated
       .conf  file.   Enabling the module puts the configuration directives in
       the .conf file as directives into the main server context of apache2.

OPTIONS
       -q, --quiet
              Don't show informative messages.

       -f, --force
              When disabling a module, also cascade disables all modules  that
              depends on it.

       -m, --maintmode
              Enables  the  maintainer mode, that is the program invocation is
              effectuated automatically by a maintainer  script.  This  switch
              should not be used by end users.

       -p, --purge
              When  disabling  a module, purge all traces of the module in the
              internal state data base.

EXIT STATUS
       a2enmod and a2dismod exit with status 0 if all  modules  are  processed
       successfully, 1 if errors occur, 2 if an invalid option was used.

EXAMPLES
              a2enmod imagemap
              a2dismod mime_magic

       Enables  the  mod_imagemap module, and disables the mod_mime_magic mod-
       ule.

FILES
       /etc/apache2/mods-available
              Directory with files giving information on available modules.

       /etc/apache2/mods-enabled
              Directory with links to the files in mods-available for  enabled
              modules.

SEE ALSO
       apache2ctl(8), a2enconf(8), a2disconf(8), a2ensite(8), a2dissite(8).

AUTHOR
       This manual page was written by Daniel Stone <> for the
       Debian GNU/Linux distribution, as it is a Debian-specific  script  with
       the package.

                                12 October 2006                     A2ENMOD(8)
```

***

**a2dissite**

Enable or disable an apache2 site / virtual host

```
:~# man a2dissite
A2ENSITE(8)                 System Manager's Manual                A2ENSITE(8)

NAME
       a2ensite, a2dissite - enable or disable an apache2 site / virtual host

SYNOPSIS
       a2ensite [-q|--quiet] [-m|--maintmode] [ site ]

       a2dissite [-q|--quiet] [-m|--maintmode] [-p|--purge] [ site ]

DESCRIPTION
       This manual page documents briefly the a2ensite and a2dissite commands.

       a2ensite  is a script that enables the specified site (which contains a
       <VirtualHost> block) within the apache2 configuration.  It does this by
       creating  symlinks within /etc/apache2/sites-enabled.  Likewise, a2dis-
       site disables a site by removing those symlinks.  It is not an error to
       enable  a site which is already enabled, or to disable one which is al-
       ready disabled.

       Apache treats the very first virtual host enabled  specially  as  every
       request  not  matching  any actual directive is being redirected there.
       Thus it should be called 000-default in order to sort  before  the  re-
       maining hosts to be loaded first.

OPTIONS
       -q, --quiet
              Don't show informative messages.

       -m, --maintmode
              Enables  the  maintainer mode, that is the program invocation is
              effectuated automatically by a maintainer  script.  This  switch
              should not be used by end users.

       -p, --purge
              When  disabling  a module, purge all traces of the module in the
              internal state data base.

EXIT STATUS
       a2ensite and a2dissite exit with status 0 if all  sites  are  processed
       successfully, 1 if errors occur, 2 if an invalid option was used.

EXAMPLES
              a2dissite 000-default

       Disables the default site.

FILES
       /etc/apache2/sites-available
              Directory with files giving information on available sites.

       /etc/apache2/sites-enabled
              Directory with links to the files in sites-available for enabled
              sites.

SEE ALSO
       apache2ctl(8), a2enmod(8), a2dismod(8), a2enconf(8), a2disconf(8).

AUTHOR
       This manual page was written by Stefan Fritsch  <>  (based
       on  the a2enmod manual page by Daniel Stone <>) for the
       Debian GNU/Linux distribution.

                                  8 June 2007                      A2ENSITE(8)
```

***

**a2enconf**

Enable or disable an apache2 configuration file

```
:~# man a2enconf
A2ENCONF(8)                 System Manager's Manual                A2ENCONF(8)

NAME
       a2enconf, a2disconf - enable or disable an apache2 configuration file

SYNOPSIS
       a2enconf [-q|--quiet] [-m|--maintmode] [ configuration ]

       a2disconf [-q|--quiet] [-m|--maintmode] [-p|--purge] [ configuration ]

DESCRIPTION
       This manual page documents briefly the a2enconf and a2disconf commands.

       a2enconf  is  a  script  that  enables the specified configuration file
       within the apache2 configuration.  It does this  by  creating  symlinks
       within  /etc/apache2/conf-enabled.  Likewise, a2disconf disables a spe-
       cific configuration part by removing those symlinks.  It is not an  er-
       ror  to  enable a configuration which is already enabled, or to disable
       one which is already disabled.

       Note that many configuration file may have  a  dependency  to  specific
       modules.   Unlike module dependencies, these are not resolved automati-
       cally. Configuration fragments stored in the  conf-available  directory
       are  considered  non-essential or being installed and manged by reverse
       dependencies (e.g. web scripts).

OPTIONS
       -q, --quiet
              Don't show informative messages.

       -m, --maintmode
              Enables the maintainer mode, that is the program  invocation  is
              effectuated  automatically  by  a maintainer script. This switch
              should not be used by end users.

       -p, --purge
              When disabling a module, purge all traces of the module  in  the
              internal state data base.

EXIT STATUS
       a2enconf  and  a2disconf  exit  with status 0 if all configurations are
       processed successfully, 1 if errors occur, 2 if an invalid  option  was
       used.

EXAMPLES
              a2enconf security
              a2disconf charset

       Enables Apache security directives stored in the security configuration
       files, and disables the charset configuration.

FILES
       /etc/apache2/conf-available
              Directory with files giving information on available  configura-
              tion files.

       /etc/apache2/conf-enabled
              Directory  with links to the files in conf-available for enabled
              configuration files.

SEE ALSO
       apache2ctl(8), a2enmod(8), a2dismod(8), a2ensite(8), a2dissite(8).

AUTHOR
       This manual page was written by Arno Toell <>  for  the
       Debian  GNU/Linux  distribution, as it is a Debian-specific script with
       the package.

                               14 February 2012                    A2ENCONF(8)
```

***

**a2enmod**

Enable or disable an apache2 module

```
:~# man a2enmod
A2ENMOD(8)                  System Manager's Manual                 A2ENMOD(8)

NAME
       a2enmod, a2dismod - enable or disable an apache2 module

SYNOPSIS
       a2enmod [-q|--quiet] [-m|--maintmode] [ module ]

       a2dismod [-q|--quiet] [-f|--force] [-m|--maintmode] [-p|--purge] [ mod-
       ule ]

DESCRIPTION
       This manual page documents briefly the a2enmod and a2dismod commands.

       a2enmod is a script  that  enables  the  specified  module  within  the
       apache2  configuration.   It  does  this  by  creating  symlinks within
       /etc/apache2/mods-enabled.  Likewise, a2dismod disables a module by re-
       moving  those symlinks.  It is not an error to enable a module which is
       already enabled, or to disable one which is already disabled.

       Note that many modules have, in addition to a .load file, an associated
       .conf  file.   Enabling the module puts the configuration directives in
       the .conf file as directives into the main server context of apache2.

OPTIONS
       -q, --quiet
              Don't show informative messages.

       -f, --force
              When disabling a module, also cascade disables all modules  that
              depends on it.

       -m, --maintmode
              Enables  the  maintainer mode, that is the program invocation is
              effectuated automatically by a maintainer  script.  This  switch
              should not be used by end users.

       -p, --purge
              When  disabling  a module, purge all traces of the module in the
              internal state data base.

EXIT STATUS
       a2enmod and a2dismod exit with status 0 if all  modules  are  processed
       successfully, 1 if errors occur, 2 if an invalid option was used.

EXAMPLES
              a2enmod imagemap
              a2dismod mime_magic

       Enables  the  mod_imagemap module, and disables the mod_mime_magic mod-
       ule.

FILES
       /etc/apache2/mods-available
              Directory with files giving information on available modules.

       /etc/apache2/mods-enabled
              Directory with links to the files in mods-available for  enabled
              modules.

SEE ALSO
       apache2ctl(8), a2enconf(8), a2disconf(8), a2ensite(8), a2dissite(8).

AUTHOR
       This manual page was written by Daniel Stone <> for the
       Debian GNU/Linux distribution, as it is a Debian-specific  script  with
       the package.

                                12 October 2006                     A2ENMOD(8)
```

***

**a2ensite**

Enable or disable an apache2 site / virtual host

```
:~# man a2ensite
A2ENSITE(8)                 System Manager's Manual                A2ENSITE(8)

NAME
       a2ensite, a2dissite - enable or disable an apache2 site / virtual host

SYNOPSIS
       a2ensite [-q|--quiet] [-m|--maintmode] [ site ]

       a2dissite [-q|--quiet] [-m|--maintmode] [-p|--purge] [ site ]

DESCRIPTION
       This manual page documents briefly the a2ensite and a2dissite commands.

       a2ensite  is a script that enables the specified site (which contains a
       <VirtualHost> block) within the apache2 configuration.  It does this by
       creating  symlinks within /etc/apache2/sites-enabled.  Likewise, a2dis-
       site disables a site by removing those symlinks.  It is not an error to
       enable  a site which is already enabled, or to disable one which is al-
       ready disabled.

       Apache treats the very first virtual host enabled  specially  as  every
       request  not  matching  any actual directive is being redirected there.
       Thus it should be called 000-default in order to sort  before  the  re-
       maining hosts to be loaded first.

OPTIONS
       -q, --quiet
              Don't show informative messages.

       -m, --maintmode
              Enables  the  maintainer mode, that is the program invocation is
              effectuated automatically by a maintainer  script.  This  switch
              should not be used by end users.

       -p, --purge
              When  disabling  a module, purge all traces of the module in the
              internal state data base.

EXIT STATUS
       a2ensite and a2dissite exit with status 0 if all  sites  are  processed
       successfully, 1 if errors occur, 2 if an invalid option was used.

EXAMPLES
              a2dissite 000-default

       Disables the default site.

FILES
       /etc/apache2/sites-available
              Directory with files giving information on available sites.

       /etc/apache2/sites-enabled
              Directory with links to the files in sites-available for enabled
              sites.

SEE ALSO
       apache2ctl(8), a2enmod(8), a2dismod(8), a2enconf(8), a2disconf(8).

AUTHOR
       This manual page was written by Stefan Fritsch  <>  (based
       on  the a2enmod manual page by Daniel Stone <>) for the
       Debian GNU/Linux distribution.

                                  8 June 2007                      A2ENSITE(8)
```

***

**a2query**

Retrieve runtime configuration from a local Apache 2 HTTP server

```
:~# a2query --help
/usr/sbin/a2query version [unknown] calling Getopt::Std::getopts (version 1.13 [paranoid]),
running under Perl version 5.36.0.

Usage: a2query [-OPTIONS [-MORE_OPTIONS]] [--] [PROGRAM_ARG1 ...]

The following single-character options are accepted:
	With arguments: -m -s -c
	Boolean (without arguments): -h -a -v -M -d -q

Options may be merged together.  -- stops processing of options.
Space is not required between options and their arguments.

For more details run
	perldoc -F /usr/sbin/a2query
  [Now continuing due to backward compatibility and excessive paranoia.
   See 'perldoc Getopt::Std' about $Getopt::Std::STANDARD_HELP_VERSION.]
```

***

**apache2ctl**

Apache HTTP server control interface

```
:~# apache2ctl -h
Usage: /usr/sbin/apache2 [-D name] [-d directory] [-f file]
                         [-C "directive"] [-c "directive"]
                         [-k start|restart|graceful|graceful-stop|stop]
                         [-v] [-V] [-h] [-l] [-L] [-t] [-T] [-S] [-X]
Options:
  -D name            : define a name for use in <IfDefine name> directives
  -d directory       : specify an alternate initial ServerRoot
  -f file            : specify an alternate ServerConfigFile
  -C "directive"     : process directive before reading config files
  -c "directive"     : process directive after reading config files
  -e level           : show startup errors of level (see LogLevel)
  -E file            : log startup errors to file
  -v                 : show version number
  -V                 : show compile settings
  -h                 : list available command line options (this page)
  -l                 : list compiled in modules
  -L                 : list available configuration directives
  -t -D DUMP_VHOSTS  : show parsed vhost settings
  -t -D DUMP_RUN_CFG : show parsed run settings
  -S                 : a synonym for -t -D DUMP_VHOSTS -D DUMP_RUN_CFG
  -t -D DUMP_MODULES : show all loaded modules 
  -M                 : a synonym for -t -D DUMP_MODULES
  -t -D DUMP_INCLUDES: show all included configuration files
  -t                 : run syntax check for config files
  -T                 : start without DocumentRoot(s) check
  -X                 : debug mode (only one worker, do not detach)
```

***

**apachectl**

Apache HTTP server control interface

```
:~# apachectl -h
Usage: /usr/sbin/apache2 [-D name] [-d directory] [-f file]
                         [-C "directive"] [-c "directive"]
                         [-k start|restart|graceful|graceful-stop|stop]
                         [-v] [-V] [-h] [-l] [-L] [-t] [-T] [-S] [-X]
Options:
  -D name            : define a name for use in <IfDefine name> directives
  -d directory       : specify an alternate initial ServerRoot
  -f file            : specify an alternate ServerConfigFile
  -C "directive"     : process directive before reading config files
  -c "directive"     : process directive after reading config files
  -e level           : show startup errors of level (see LogLevel)
  -E file            : log startup errors to file
  -v                 : show version number
  -V                 : show compile settings
  -h                 : list available command line options (this page)
  -l                 : list compiled in modules
  -L                 : list available configuration directives
  -t -D DUMP_VHOSTS  : show parsed vhost settings
  -t -D DUMP_RUN_CFG : show parsed run settings
  -S                 : a synonym for -t -D DUMP_VHOSTS -D DUMP_RUN_CFG
  -t -D DUMP_MODULES : show all loaded modules 
  -M                 : a synonym for -t -D DUMP_MODULES
  -t -D DUMP_INCLUDES: show all included configuration files
  -t                 : run syntax check for config files
  -T                 : start without DocumentRoot(s) check
  -X                 : debug mode (only one worker, do not detach)
```

***

#### apache2-bin <a href="#apache2-bin" id="apache2-bin"></a>

The Apache HTTP Server Project’s goal is to build a secure, efficient and extensible HTTP server as standards-compliant open source software. The result has long been the number one web server on the Internet.

This package contains the binaries only and does not set up a working web-server instance. Install the “apache2” package to get a fully working instance.

**Installed size:** `4.89 MB`\
**How to install:** `sudo apt install apache2-bin`

<details>

<summary>Dependencies:</summary>

* libapr1
* libaprutil1
* libaprutil1-dbd-sqlite3 | libaprutil1-dbd-mysql | libaprutil1-dbd-odbc | libaprutil1-dbd-pgsql | libaprutil1-dbd-freetds
* libaprutil1-ldap
* libbrotli1
* libc6
* libcrypt1
* libcurl4
* libjansson4
* libldap-2.5-0
* liblua5.3-0
* libnghttp2-14
* libpcre2-8-0
* libssl3
* libxml2
* perl
* zlib1g

</details>

**apache2**

Apache Hypertext Transfer Protocol Server

```
:~# apache2 -h
Usage: apache2 [-D name] [-d directory] [-f file]
               [-C "directive"] [-c "directive"]
               [-k start|restart|graceful|graceful-stop|stop]
               [-v] [-V] [-h] [-l] [-L] [-t] [-T] [-S] [-X]
Options:
  -D name            : define a name for use in <IfDefine name> directives
  -d directory       : specify an alternate initial ServerRoot
  -f file            : specify an alternate ServerConfigFile
  -C "directive"     : process directive before reading config files
  -c "directive"     : process directive after reading config files
  -e level           : show startup errors of level (see LogLevel)
  -E file            : log startup errors to file
  -v                 : show version number
  -V                 : show compile settings
  -h                 : list available command line options (this page)
  -l                 : list compiled in modules
  -L                 : list available configuration directives
  -t -D DUMP_VHOSTS  : show parsed vhost settings
  -t -D DUMP_RUN_CFG : show parsed run settings
  -S                 : a synonym for -t -D DUMP_VHOSTS -D DUMP_RUN_CFG
  -t -D DUMP_MODULES : show all loaded modules 
  -M                 : a synonym for -t -D DUMP_MODULES
  -t -D DUMP_INCLUDES: show all included configuration files
  -t                 : run syntax check for config files
  -T                 : start without DocumentRoot(s) check
  -X                 : debug mode (only one worker, do not detach)
```

***

#### apache2-data <a href="#apache2-data" id="apache2-data"></a>

The Apache HTTP Server Project’s goal is to build a secure, efficient and extensible HTTP server as standards-compliant open source software. The result has long been the number one web server on the Internet.

This package contains architecture-independent common files such as icons, error pages and static index files.

**Installed size:** `849 KB`\
**How to install:** `sudo apt install apache2-data`

***

#### apache2-dev <a href="#apache2-dev" id="apache2-dev"></a>

The Apache HTTP Server Project’s goal is to build a secure, efficient and extensible HTTP server as standards-compliant open source software. The result has long been the number one web server on the Internet.

This package provides development headers and the apxs2 binary for the Apache 2 HTTP server, useful to develop and link third party additions to the Debian Apache HTTP server package.

It also provides dh\_apache2 and dh sequence addons useful to install various Debian Apache2 extensions with debhelper. It supports

* Apache 2 module configurations and shared objects
* Site configuration files
* Global configuration files

**Installed size:** `1.06 MB`\
**How to install:** `sudo apt install apache2-dev`

<details>

<summary>Dependencies:</summary>

* debhelper
* libapr1-dev
* libaprutil1-dev
* libpcre2-dev
* openssl
* perl

</details>

**apxs**

APache eXtenSion tool

```
:~# apxs --help
apxs:Error: Unknown option: -.
apxs:Error: Unknown option: h.
Usage: apxs -g [-S <var>=<val>] -n <modname>
       apxs -q [-v] [-S <var>=<val>] [<query> ...]
       apxs -c [-S <var>=<val>] [-o <dsofile>] [-D <name>[=<value>]]
               [-I <incdir>] [-L <libdir>] [-l <libname>] [-Wc,<flags>]
               [-Wl,<flags>] [-p] <files> ...
       apxs -i [-S <var>=<val>] [-a] [-A] [-n <modname>] <dsofile> ...
       apxs -e [-S <var>=<val>] [-a] [-A] [-n <modname>] <dsofile> ...
```

***

**apxs2**

APache eXtenSion tool

```
:~# apxs2 --help
apxs:Error: Unknown option: -.
apxs:Error: Unknown option: h.
Usage: apxs -g [-S <var>=<val>] -n <modname>
       apxs -q [-v] [-S <var>=<val>] [<query> ...]
       apxs -c [-S <var>=<val>] [-o <dsofile>] [-D <name>[=<value>]]
               [-I <incdir>] [-L <libdir>] [-l <libname>] [-Wc,<flags>]
               [-Wl,<flags>] [-p] <files> ...
       apxs -i [-S <var>=<val>] [-a] [-A] [-n <modname>] <dsofile> ...
       apxs -e [-S <var>=<val>] [-a] [-A] [-n <modname>] <dsofile> ...
```

***

**dh\_apache2**

Register configuration snippets to the Apache web server

```
:~# dh_apache2 -h
Usage: dh_apache2 [options]

  dh_apache2 is a part of debhelper. See debhelper(7)
  and dh_apache2(1) for complete usage instructions.
```

***

#### apache2-doc <a href="#apache2-doc" id="apache2-doc"></a>

The Apache HTTP Server Project’s goal is to build a secure, efficient and extensible HTTP server as standards-compliant open source software. The result has long been the number one web server on the Internet.

This package provides the documentation for the Apache 2 HTTP server. The documentation is shipped in HTML format and can be accessed from a local running Apache HTTP server instance or by browsing the file system directly.

**Installed size:** `24.53 MB`\
**How to install:** `sudo apt install apache2-doc`

***

#### apache2-ssl-dev <a href="#apache2-ssl-dev" id="apache2-ssl-dev"></a>

The Apache HTTP Server Project’s goal is to build a secure, efficient and extensible HTTP server as standards-compliant open source software. The result has long been the number one web server on the Internet.

This package provides the development header and the dependencies for modules that interact with mod\_ssl’s internal openssl state.

**Installed size:** `13 KB`\
**How to install:** `sudo apt install apache2-ssl-dev`

<details>

<summary>Dependencies:</summary>

* apache2-dev
* libssl-dev

</details>

***

#### apache2-suexec-custom <a href="#apache2-suexec-custom" id="apache2-suexec-custom"></a>

Provides a customizable version of the suexec helper program for mod\_suexec. This is not the version from upstream, but can be configured with a configuration file.

If you do not need non-standard document root or userdir settings, it is recommended that you use the standard suexec helper program from the apache2-suexec-pristine package instead.

**Installed size:** `184 KB`\
**How to install:** `sudo apt install apache2-suexec-custom`

<details>

<summary>Dependencies:</summary>

* apache2-bin
* libc6

</details>

***

#### apache2-suexec-pristine <a href="#apache2-suexec-pristine" id="apache2-suexec-pristine"></a>

Provides the standard suexec helper program for mod\_suexec. This version is compiled with document root /var/www and userdir suffix public\_html. If you need different settings, use the package apache2-suexec-custom.

**Installed size:** `174 KB`\
**How to install:** `sudo apt install apache2-suexec-pristine`

<details>

<summary>Dependencies:</summary>

* apache2-bin
* libc6

</details>

***

#### apache2-utils <a href="#apache2-utils" id="apache2-utils"></a>

Provides some add-on programs useful for any web server. These include:

* ab (Apache benchmark tool)
* fcgistarter (Start a FastCGI program)
* logresolve (Resolve IP addresses to hostnames in logfiles)
* htpasswd (Manipulate basic authentication files)
* htdigest (Manipulate digest authentication files)
* htdbm (Manipulate basic authentication files in DBM format, using APR)
* htcacheclean (Clean up the disk cache)
* rotatelogs (Periodically stop writing to a logfile and open a new one)
* split-logfile (Split a single log including multiple vhosts)
* checkgid (Checks whether the caller can setgid to the specified group)
* check\_forensic (Extract mod\_log\_forensic output from Apache log files)
* httxt2dbm (Generate dbm files for use with RewriteMap)

**Installed size:** `429 KB`\
**How to install:** `sudo apt install apache2-utils`

<details>

<summary>Dependencies:</summary>

* libapr1
* libaprutil1
* libc6
* libcrypt1
* libssl3

</details>

**ab**

Apache HTTP server benchmarking tool

```
:~# ab --help
ab: wrong number of arguments
Usage: ab [options] [http[s]://]hostname[:port]/path
Options are:
    -n requests     Number of requests to perform
    -c concurrency  Number of multiple requests to make at a time
    -t timelimit    Seconds to max. to spend on benchmarking
                    This implies -n 50000
    -s timeout      Seconds to max. wait for each response
                    Default is 30 seconds
    -b windowsize   Size of TCP send/receive buffer, in bytes
    -B address      Address to bind to when making outgoing connections
    -p postfile     File containing data to POST. Remember also to set -T
    -u putfile      File containing data to PUT. Remember also to set -T
    -T content-type Content-type header to use for POST/PUT data, eg.
                    'application/x-www-form-urlencoded'
                    Default is 'text/plain'
    -v verbosity    How much troubleshooting info to print
    -w              Print out results in HTML tables
    -i              Use HEAD instead of GET
    -x attributes   String to insert as table attributes
    -y attributes   String to insert as tr attributes
    -z attributes   String to insert as td or th attributes
    -C attribute    Add cookie, eg. 'Apache=1234'. (repeatable)
    -H attribute    Add Arbitrary header line, eg. 'Accept-Encoding: gzip'
                    Inserted after all normal header lines. (repeatable)
    -A attribute    Add Basic WWW Authentication, the attributes
                    are a colon separated username and password.
    -P attribute    Add Basic Proxy Authentication, the attributes
                    are a colon separated username and password.
    -X proxy:port   Proxyserver and port number to use
    -V              Print version number and exit
    -k              Use HTTP KeepAlive feature
    -d              Do not show percentiles served table.
    -S              Do not show confidence estimators and warnings.
    -q              Do not show progress when doing more than 150 requests
    -l              Accept variable document length (use this for dynamic pages)
    -g filename     Output collected data to gnuplot format file.
    -e filename     Output CSV file with percentages served
    -r              Don't exit on socket receive errors.
    -m method       Method name
    -h              Display usage information (this message)
    -I              Disable TLS Server Name Indication (SNI) extension
    -Z ciphersuite  Specify SSL/TLS cipher suite (See openssl ciphers)
    -f protocol     Specify SSL/TLS protocol
                    (SSL2, TLS1, TLS1.1, TLS1.2, TLS1.3 or ALL)
    -E certfile     Specify optional client certificate chain and private key
```

***

**check\_forensic**

Tool to extract mod\_log\_forensic output from apache log files

```
:~# man check_forensic
check_forensic(8)           System Manager's Manual          check_forensic(8)

NAME
       check_forensic  -  tool  to extract mod_log_forensic output from apache
       log files

SYNOPSIS
       check_forensic <log_file>

DESCRIPTION
       chech_forensic is a simple shell script designed to help apache  admin-
       istrators  to  extract  mod_log_forensic output from apache2 log files.
       It checks the forensic log for requests that did not complete and  out-
       puts the request log for each one.

AUTHOR
       This  manual  page  was  written  by  Fabio  M. Di Nitto <
       bione.net>, for the Debian GNU/Linux system (but may be  used  by  oth-
       ers).

                                                             check_forensic(8)
```

***

**checkgid**

Checks the gid

```
:~# man checkgid
CHECKGID(8)                 System Manager's Manual                CHECKGID(8)

NAME
       checkgid - checks the gid

SYNOPSIS
       checkgid group

DESCRIPTION
       This manual page documents briefly the checkgid command.

       checkgid  is  a  program that checks whether it can setgid to the group
       specified. This is to see if it is a valid group for apache2 to use  at
       runtime.  If the user (should be run as superuser) is in that group, or
       can setgid to it, it will return 0.

AUTHOR
       This manual page was written by Daniel Stone <> for the
       Debian GNU/Linux distribution, as the original did not have a manpage.

                              November 3rd, 2001                   CHECKGID(8)
```

***

**fcgistarter**

Start a FastCGI program

```
:~# fcgistarter -h
fcgistarter: illegal option -- h
usage: fcgistarter -c <command> -p <port> [-i <interface> -N <num>]

If an interface is not specified, any available will be used.
```

***

**htcacheclean**

Clean up the disk cache

```
:~# htcacheclean --help
htcacheclean error: Option -p must be specified
htcacheclean -- program for cleaning the disk cache.
Usage: htcacheclean [-Dvtrn] -pPATH [-lLIMIT] [-LLIMIT] [-PPIDFILE]
       htcacheclean [-nti] -dINTERVAL -pPATH [-lLIMIT] [-LLIMIT] [-PPIDFILE]
       htcacheclean [-Dvt] -pPATH URL ...

Options:
  -d   Daemonize and repeat cache cleaning every INTERVAL minutes.
       This option is mutually exclusive with the -D, -v and -r
       options.

  -D   Do a dry run and don't delete anything. This option is mutually
       exclusive with the -d option. When doing a dry run and deleting
       directories with -t, the inodes reported deleted in the stats
       cannot take into account the directories deleted, and will be
       marked as an estimate.

  -v   Be verbose and print statistics. This option is mutually
       exclusive with the -d option.

  -r   Clean thoroughly. This assumes that the Apache web server is 
       not running. This option is mutually exclusive with the -d
       option and implies -t.

  -n   Be nice. This causes slower processing in favour of other
       processes.

  -t   Delete all empty directories. By default only cache files are
       removed, however with some configurations the large number of
       directories created may require attention.

  -p   Specify PATH as the root directory of the disk cache.

  -P   Specify PIDFILE as the file to write the pid to.

  -R   Specify amount to round sizes up to.

  -l   Specify LIMIT as the total disk cache size limit. Attach 'K',
       'M' or 'G' to the number for specifying KBytes, MBytes or
        GBytes.

  -L   Specify LIMIT as the total disk cache inode limit. 'K', 'M' or
       'G' suffix can also be used.

  -i   Be intelligent and run only when there was a modification of
       the disk cache. This option is only possible together with the
       -d option.

  -a   List the URLs currently stored in the cache. Variants of the
       same URL will be listed once for each variant.

  -A   List the URLs currently stored in the cache, along with their
       attributes in the following order: url, header size, body size,
       status, entity version, date, expiry, request time,
       response time, body present, head request.

Should an URL be provided on the command line, the URL will be
deleted from the cache. A reverse proxied URL is made up as follows:
http://<hostname>:<port><path>?[query]. So, for the path "/" on the
host "localhost" and port 80, the URL to delete becomes
"http://localhost:80/?". Note the '?' in the URL must always be
specified explicitly, whether a query string is present or not.
```

***

**htdbm**

Manipulate DBM password databases

```
:~# htdbm -h
htdbm: illegal option -- h
htdbm -- program for manipulating DBM password databases.

Usage: htdbm   [-cimBdpstvx] [-C cost] [-TDBTYPE] database username
                -b[cmBdptsv] [-C cost] [-TDBTYPE] database username password
                -n[imBdpst]  [-C cost] username
                -nb[mBdpst]  [-C cost] username password
                -v[imBdps]   [-C cost] [-TDBTYPE] database username
                -vb[mBdps]   [-C cost] [-TDBTYPE] database username password
                -x                     [-TDBTYPE] database username
                -l                     [-TDBTYPE] database
Options:
   -c   Create a new database.
   -n   Don't update database; display results on stdout.
   -b   Use the password from the command line rather than prompting for it.
   -i   Read password from stdin without verification (for script usage).
   -m   Force MD5 encryption of the password (default).
   -B   Force BCRYPT encryption of the password (very secure).
   -C   Set the computing time used for the bcrypt algorithm
        (higher is more secure but slower, default: 5, valid: 4 to 31).
   -d   Force CRYPT encryption of the password (8 chars max, insecure).
   -s   Force SHA encryption of the password (insecure).
   -p   Do not encrypt the password (plaintext, insecure).
   -T   DBM Type (SDBM|GDBM|DB|default).
   -l   Display usernames from database on stdout.
   -v   Verify the username/password.
   -x   Remove the username record from database.
   -t   The last param is username comment.
The SHA algorithm does not use a salt and is less secure than the MD5 algorithm.
```

***

**htdigest**

Manage user files for digest authentication

```
:~# htdigest -h
Usage: htdigest [-c] passwordfile realm username
The -c flag creates a new file.
```

***

**htpasswd**

Manage user files for basic authentication

```
:~# htpasswd -h
htpasswd: illegal option -- h
Usage:
	htpasswd [-cimBdpsDv] [-C cost] passwordfile username
	htpasswd -b[cmBdpsDv] [-C cost] passwordfile username password

	htpasswd -n[imBdps] [-C cost] username
	htpasswd -nb[mBdps] [-C cost] username password
 -c  Create a new file.
 -n  Don't update file; display results on stdout.
 -b  Use the password from the command line rather than prompting for it.
 -i  Read password from stdin without verification (for script usage).
 -m  Force MD5 encryption of the password (default).
 -B  Force bcrypt encryption of the password (very secure).
 -C  Set the computing time used for the bcrypt algorithm
     (higher is more secure but slower, default: 5, valid: 4 to 17).
 -d  Force CRYPT encryption of the password (8 chars max, insecure).
 -s  Force SHA encryption of the password (insecure).
 -p  Do not encrypt the password (plaintext, insecure).
 -D  Delete the specified user.
 -v  Verify password for the specified user.
On other systems than Windows and NetWare the '-p' flag will probably not work.
The SHA algorithm does not use a salt and is less secure than the MD5 algorithm.
```

***

**httxt2dbm**

Generate dbm files for use with RewriteMap

```
:~# httxt2dbm -h
httxt2dbm: illegal option -- h
Error: Parsing Arguments Failed

httxt2dbm -- Program to Create DBM Files for use by RewriteMap
Usage: httxt2dbm [-v] [-f format] -i SOURCE_TXT -o OUTPUT_DBM

Options: 
 -v    More verbose output

 -i    Source Text File. If '-', use stdin.

 -o    Output DBM.

 -f    DBM Format.  If not specified, will use the APR Default.
           GDBM for GDBM files (available)
           SDBM for SDBM files (available)
           DB   for berkeley DB files (available)
           NDBM for NDBM files (unavailable)
           default for the default DBM type

```

***

**logresolve**

Resolve IP-addresses to hostnames in Apache log files

```
:~# logresolve -h
logresolve: illegal option -- h
logresolve -- Resolve IP-addresses to hostnames in Apache log files.
Usage: logresolve [-s STATFILE] [-c]

Options:
  -s   Record statistics to STATFILE when finished.

  -c   Perform double lookups when resolving IP addresses.
```

***

**rotatelogs**

Piped logging program to rotate Apache logs

```
:~# rotatelogs -h
rotatelogs: illegal option -- h
Usage: rotatelogs [-v] [-l] [-L linkname] [-p prog] [-f] [-D] [-t] [-e] [-c] [-n number] <logfile> {<rotation time in seconds>|<rotation size>(B|K|M|G)} [offset minutes from UTC]

Add this:

TransferLog "|rotatelogs /some/where 86400"

or 

TransferLog "|rotatelogs /some/where 5M"

to httpd.conf. By default, the generated name will be
<logfile>.nnnn where nnnn is the system time at which the log
nominally starts (N.B. if using a rotation time, the time will
always be a multiple of the rotation time, so you can synchronize
cron scripts with it). If <logfile> contains strftime conversion
specifications, those will be used instead. At the end of each
rotation time or when the file size is reached a new log is
started.

Options:
  -v       Verbose operation. Messages are written to stderr.
  -l       Base rotation on local time instead of UTC.
  -L path  Create hard link from current log to specified path.
  -p prog  Run specified program after opening a new log file. See below.
  -f       Force opening of log on program start.
  -D       Create parent directories of log file.
  -t       Truncate logfile instead of rotating, tail friendly.
  -e       Echo log to stdout for further processing.
  -c       Create log even if it is empty.
  -n num   Rotate file by adding suffixes '.1', '.2', ..., '.num'.

The program for '-p' is invoked as "[prog] <curfile> [<prevfile>]"
where <curfile> is the filename of the newly opened logfile, and
<prevfile>, if given, is the filename of the previously used logfile.

```

***

**split-logfile**

Split combined virtual hosts access log into one file per virtual host

```
:~# man split-logfile
SPLIT-LOGFILE(8)                 split-logfile                SPLIT-LOGFILE(8)

NAME
       split-logfile  -  Split combined virtual hosts access log into one file
       per virtual host

SYNOPSIS
       split-logfile < logfile

SUMMARY
       This script will take a combined Web server access log file  and  break
       its  contents  into separate files.  It assumes that the first field of
       each line is the virtual host identity (put there by  "%v"),  and  that
       the logfiles should be named that+".log" in the current directory.

       The  combined  log  file  is read from stdin.  Records read will be ap-
       pended to any existing log files.

EXAMPLES
       split-logfile < /var/log/apache2/other_vhosts_access.log

Apache HTTP Server                2009-12-06                  SPLIT-LOGFILE(8)
```

***

#### libapache2-mod-md <a href="#libapache2-mod-md" id="libapache2-mod-md"></a>

This is a transitional package to apache2 for users of libapache2-mod-md. It can be safely removed after the installation is complete.

**Installed size:** `6 KB`\
**How to install:** `sudo apt install libapache2-mod-md`

<details>

<summary>Dependencies:</summary>

* apache2

</details>

***

#### libapache2-mod-proxy-uwsgi <a href="#libapache2-mod-proxy-uwsgi" id="libapache2-mod-proxy-uwsgi"></a>

This is a transitional package to apache2 for users of libapache2-mod-proxy-uwsgi. It can be safely removed after the installation is complete.

**Installed size:** `10 KB`\
**How to install:** `sudo apt install libapache2-mod-proxy-uwsgi`

<details>

<summary>Dependencies:</summary>

* apache2

</details>

***

Updated on: 2023-Mar-08\


***
