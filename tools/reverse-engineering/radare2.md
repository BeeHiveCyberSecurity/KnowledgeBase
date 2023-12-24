---
description: >-
  Radare2 is an open-source command-line reverse engineering tool with features
  for analyzing and manipulating binary files, including debugging and
  cryptographic analysis.
---

# 📎 radare2

### Packages and Binaries:

#### libradare2-5.0.0 <a href="#libradare2-500" id="libradare2-500"></a>

The project aims to create a complete, portable, multi-architecture, unix-like toolchain for reverse engineering.

It is composed by an hexadecimal editor (radare) with a wrapped IO layer supporting multiple backends for local/remote files, debugger (OS X, BSD, Linux, W32), stream analyzer, assembler/disassembler (rasm) for x86, ARM, PPC, m68k, Java, MSIL, SPARC, code analysis modules and scripting facilities. A bindiffer named radiff, base converter (rax), shellcode development helper (rasc), a binary information extractor supporting PE, mach0, ELF, class, etc. named rabin, and a block-based hash utility called rahash.

This package provides the libraries from radare2.

**Installed size:** `22.23 MB`\
**How to install:** `sudo apt install libradare2-5.0.0`

<details>

<summary>Dependencies:</summary>

* libc6
* libcapstone4
* liblz4-1
* libmagic1
* libradare2-common
* libuv1
* libxxhash0
* libzip4
* zlib1g

</details>

***

#### libradare2-common <a href="#libradare2-common" id="libradare2-common"></a>

The project aims to create a complete, portable, multi-architecture, unix-like toolchain for reverse engineering.

It is composed by an hexadecimal editor (radare) with a wrapped IO layer supporting multiple backends for local/remote files, debugger (OS X, BSD, Linux, W32), stream analyzer, assembler/disassembler (rasm) for x86, ARM, PPC, m68k, Java, MSIL, SPARC, code analysis modules and scripting facilities. A bindiffer named radiff, base converter (rax), shellcode development helper (rasc), a binary information extractor supporting PE, mach0, ELF, class, etc. named rabin, and a block-based hash utility called rahash.

This package provides the arch independent files from radare2.

**Installed size:** `3.52 MB`\
**How to install:** `sudo apt install libradare2-common`

***

#### libradare2-dev <a href="#libradare2-dev" id="libradare2-dev"></a>

The project aims to create a complete, portable, multi-architecture, unix-like toolchain for reverse engineering.

It is composed by an hexadecimal editor (radare) with a wrapped IO layer supporting multiple backends for local/remote files, debugger (OS X, BSD, Linux, W32), stream analyzer, assembler/disassembler (rasm) for x86, ARM, PPC, m68k, Java, MSIL, SPARC, code analysis modules and scripting facilities. A bindiffer named radiff, base converter (rax), shellcode development helper (rasc), a binary information extractor supporting PE, mach0, ELF, class, etc. named rabin, and a block-based hash utility called rahash.

This package provides the devel files from radare2.

**Installed size:** `1.15 MB`\
**How to install:** `sudo apt install libradare2-dev`

<details>

<summary>Dependencies:</summary>

* libcapstone-dev
* liblz4-dev
* libmagic-dev
* libradare2-5.0.0
* libuv1-dev
* libzip-dev

</details>

***

#### radare2 <a href="#radare2" id="radare2"></a>

The project aims to create a complete, portable, multi-architecture, unix-like toolchain for reverse engineering.

It is composed by an hexadecimal editor (radare) with a wrapped IO layer supporting multiple backends for local/remote files, debugger (OS X, BSD, Linux, W32), stream analyzer, assembler/disassembler (rasm) for x86, ARM, PPC, m68k, Java, MSIL, SPARC, code analysis modules and scripting facilities. A bindiffer named radiff, base converter (rax), shellcode development helper (rasc), a binary information extractor supporting PE, mach0, ELF, class, etc. named rabin, and a block-based hash utility called rahash.

**Installed size:** `2.15 MB`\
**How to install:** `sudo apt install radare2`

<details>

<summary>Dependencies:</summary>

* libc6
* libradare2-5.0.0

</details>

**r2**

Advanced command-line hexadecimal editor, disassembler and debugger

```
root@kali:~# r2 -h
Usage: r2 [-ACdfLMnNqStuvwzX] [-P patch] [-p prj] [-a arch] [-b bits] [-i file]
          [-s addr] [-B baddr] [-m maddr] [-c cmd] [-e k=v] file|pid|-|--|=
 --           run radare2 without opening any file
 -            same as 'r2 malloc://512'
 =            read file from stdin (use -i and -c to run cmds)
 -=           perform !=! command to run all commands remotely
 -0           print \x00 after init and every command
 -2           close stderr file descriptor (silent warning messages)
 -a [arch]    set asm.arch
 -A           run 'aaa' command to analyze all referenced code
 -b [bits]    set asm.bits
 -B [baddr]   set base address for PIE binaries
 -c 'cmd..'   execute radare command
 -C           file is host:port (alias for -c+=http://%s/cmd/)
 -d           debug the executable 'file' or running process 'pid'
 -D [backend] enable debug mode (e cfg.debug=true)
 -e k=v       evaluate config var
 -f           block size = file size
 -F [binplug] force to use that rbin plugin
 -h, -hh      show help message, -hh for long
 -H ([var])   display variable
 -i [file]    run script file
 -I [file]    run script file before the file is opened
 -j           use json for -v, -L and maybe others
 -k [OS/kern] set asm.os (linux, macos, w32, netbsd, ...)
 -l [lib]     load plugin file
 -L           list supported IO plugins
 -m [addr]    map file at given address (loadaddr)
 -M           do not demangle symbol names
 -n, -nn      do not load RBin info (-nn only load bin structures)
 -N           do not load user settings and scripts
 -NN          do not load any script or plugin
 -q           quiet mode (no prompt) and quit after -i
 -qq          quit after running all -c and -i
 -Q           quiet mode (no prompt) and quit faster (quickLeak=true)
 -p [prj]     use project, list if no arg, load if no file
 -P [file]    apply rapatch file and quit
 -r [rarun2]  specify rarun2 profile to load (same as -e dbg.profile=X)
 -R [rr2rule] specify custom rarun2 directive
 -s [addr]    initial seek
 -S           start r2 in sandbox mode
 -T           do not compute file hashes
 -u           set bin.filter=false to get raw sym/sec/cls names
 -v, -V       show radare2 version (-V show lib versions)
 -w           open file in write mode
 -x           open without exec-flag (asm.emu will not work), See io.exec
 -X           same as -e bin.usextr=false (useful for dyldcache)
 -z, -zz      do not load strings or load them even in raw
```

***

**r2agent**

Radare2 remoting manager TODO

```
root@kali:~# r2agent -h
Usage: r2agent [-adhs] [-p port]
  -a        listen for everyone (localhost by default)
  -d        run in daemon mode (background)
  -h        show this help message
  -s        run in sandbox mode
  -u        enable http Authorization access
  -t        user:password authentication file
  -p [port] specify listening port (defaults to 8080)
```

***

**r2pm**

Radare2 package manager

```
root@kali:~# r2pm -h
Usage: r2pm [init|update|cmd] [...]
Commands:
 -I,info                     information about repository and installed packages
 -i,install <pkgname>        install or update package in your home (pkgname=all)
 -gi,global-install <pkg>    install or update package system-wide
 -gu,global-uninstall <pkg>  uninstall pkg from systemdir
 -U,upgrade                  r2pm -U (upgrade all outdated plugins)
 -u,uninstall <pkgname>      r2pm -u baleful (-uu to force)
 -l,list                     list installed pkgs
 -r,run [cmd ...args]        run shell command with R2PM_BINDIR in PATH
 -s,search [<keyword>]       search in database
 -t,test FX,XX,BR BID        check in Travis regressions
 -v,version                  show version
 -h,help                     show this message
 -H variable                 show value of given variable
 -c,clean ([git/dir])        clear source cache (GITDIR)
 -ci (pkgname)               clean install of given package
 -cp                         clean the user's home plugin directory
 -d,doc [pkgname]            show documentation for given package
 -w <pkgname>                what/where is installed
 init | update ..            initialize/update database
 cd [git/dir]                cd into given git (see 'r2pm ls')
 ls                          ls all cloned git repos in GITDIR
 purge                       self destroy all r2 installations
 cache                       cache contents of r2 -H to make r2pm r2-independent
Environment:
 SUDO=sudo                   use this tool as sudo
 R2PM_PLUGDIR=/root/.local/share/radare2/plugins
 R2PM_BINDIR=/root/.local/share/radare2/prefix/bin
 R2PM_OFFLINE=0              disabled by default, avoid init/update calls if set to !=0
 R2PM_DBDIR=/root/.local/share/radare2/r2pm/db
 R2PM_GITDIR=/root/.local/share/radare2/r2pm/git
 R2PM_GITSKIP=
```

***

**r2r**

```
root@kali:~# r2r -h
Usage: r2r [-qvVnL] [-j threads] [test file/dir | @test-type]
 -h           print this help
 -v           show version
 -q           quiet
 -V           verbose
 -i           interactive mode
 -u           do not git pull/clone test/bins
 -n           do nothing (don't run any test, just load/parse them)
 -L           log mode (better printing for CI, logfiles, etc.)
 -F [dir]     run fuzz tests (open and default analysis) on all files in the given dir
 -j [threads] how many threads to use for running tests concurrently (default is 8)
 -r [radare2] path to radare2 executable (default is radare2)
 -m [rasm2]   path to rasm2 executable (default is rasm2)
 -f [file]    file to use for json tests (default is bins/elf/crackme0x00b)
 -C [dir]     chdir before running r2r (default follows executable symlink + test/new
 -t [seconds] timeout per test (default is 960)
 -o [file]    output test run information in JSON format to file
 -s [ignore]  Set R2R_SKIP_(xxx)=1 to skip running those tests

R2R_SKIP_ARCHOS=1  # do not run the arch-os-specific tests
R2R_SKIP_JSON=1    # do not run the JSON tests
R2R_SKIP_FUZZ=1    # do not run the rasm2 tests
R2R_SKIP_UNIT=1    # do not run the rasm2 tests
R2R_SKIP_CMD=1     # do not run the rasm2 tests
R2R_SKIP_ASM=1     # do not run the rasm2 tests

Supported test types: @asm @json @unit @fuzz @arch @cmds
OS/Arch for archos tests: linux-x64
```

***

**rabin2**

Binary program info extractor

```
root@kali:~# rabin2 -h
Usage: rabin2 [-AcdeEghHiIjlLMqrRsSUvVxzZ] [-@ at] [-a arch] [-b bits] [-B addr]
              [-C F:C:D] [-f str] [-m addr] [-n str] [-N m:M] [-P[-P] pdb]
              [-o str] [-O str] [-k query] [-D lang symname] file
 -@ [addr]       show section, symbol or import at addr
 -A              list sub-binaries and their arch-bits pairs
 -a [arch]       set arch (x86, arm, .. or <arch>_<bits>)
 -b [bits]       set bits (32, 64 ...)
 -B [addr]       override base address (pie bins)
 -c              list classes
 -cc             list classes in header format
 -C [fmt:C:D]    create [elf,mach0,pe] with Code and Data hexpairs (see -a)
 -d              show debug/dwarf information
 -D lang name    demangle symbol name (-D all for bin.demangle=true)
 -e              entrypoint
 -ee             constructor/destructor entrypoints
 -E              globally exportable symbols
 -f [str]        select sub-bin named str
 -F [binfmt]     force to use that bin plugin (ignore header check)
 -g              same as -SMZIHVResizcld -SS -SSS -ee (show all info)
 -G [addr]       load address . offset to header
 -h              this help message
 -H              header fields
 -i              imports (symbols imported from libraries)
 -I              binary info
 -j              output in json
 -k [sdb-query]  run sdb query. for example: '*'
 -K [algo]       calculate checksums (md5, sha1, ..)
 -l              linked libraries
 -L [plugin]     list supported bin plugins or plugin details
 -m [addr]       show source line at addr
 -M              main (show address of main symbol)
 -n [str]        show section, symbol or import named str
 -N [min:max]    force min:max number of chars per string (see -z and -zz)
 -o [str]        output file/folder for write operations (out by default)
 -O [str]        write/extract operations (-O help)
 -p              show physical addresses
 -P              show debug/pdb information
 -PP             download pdb file for binary
 -q              be quiet, just show fewer data
 -qq             show less info (no offset/size for -z for ex.)
 -Q              show load address used by dlopen (non-aslr libs)
 -r              radare output
 -R              relocations
 -s              symbols
 -S              sections
 -SS             segments
 -SSS            sections mapping to segments
 -t              display file hashes
 -T              display file signature
 -u              unfiltered (no rename duplicated symbols/sections)
 -U              resoUrces
 -v              display version and quit
 -V              Show binary version information
 -w              display try/catch blocks
 -x              extract bins contained in file
 -X [fmt] [f] .. package in fat or zip the given files and bins contained in file
 -z              strings (from data section)
 -zz             strings (from raw bins [e bin.rawstr=1])
 -zzz            dump raw strings to stdout (for huge files)
 -Z              guess size of binary program
Environment:
 RABIN2_CHARSET:   e cfg.charset      # set default value charset for -z strings
 RABIN2_DEBASE64:  e bin.debase64     # try to debase64 all strings
 RABIN2_DEMANGLE=0:e bin.demangle     # do not demangle symbols
 RABIN2_DMNGLRCMD: e bin.demanglercmd # try to purge false positives
 RABIN2_LANG:      e bin.lang         # assume lang for demangling
 RABIN2_MAXSTRBUF: e bin.maxstrbuf    # specify maximum buffer size
 RABIN2_NOPLUGINS: 1|0|               # do not load shared plugins (speedup loading)
 RABIN2_PDBSERVER: e pdb.server       # use alternative PDB server
 RABIN2_PREFIX:    e bin.prefix       # prefix symbols/sections/relocs with a specific string
 RABIN2_STRFILTER: e bin.str.filter   # r2 -qc 'e bin.str.filter=??' -
 RABIN2_STRPURGE:  e bin.str.purge    # try to purge false positives
 RABIN2_SYMSTORE:  e pdb.symstore     # path to downstream symbol store
 RABIN2_SWIFTLIB:  1|0|               # load Swift libsto demangle (default: true)
```

***

**radare2**

Advanced command-line hexadecimal editor, disassembler and debugger

```
root@kali:~# radare2 -h
Usage: r2 [-ACdfLMnNqStuvwzX] [-P patch] [-p prj] [-a arch] [-b bits] [-i file]
          [-s addr] [-B baddr] [-m maddr] [-c cmd] [-e k=v] file|pid|-|--|=
 --           run radare2 without opening any file
 -            same as 'r2 malloc://512'
 =            read file from stdin (use -i and -c to run cmds)
 -=           perform !=! command to run all commands remotely
 -0           print \x00 after init and every command
 -2           close stderr file descriptor (silent warning messages)
 -a [arch]    set asm.arch
 -A           run 'aaa' command to analyze all referenced code
 -b [bits]    set asm.bits
 -B [baddr]   set base address for PIE binaries
 -c 'cmd..'   execute radare command
 -C           file is host:port (alias for -c+=http://%s/cmd/)
 -d           debug the executable 'file' or running process 'pid'
 -D [backend] enable debug mode (e cfg.debug=true)
 -e k=v       evaluate config var
 -f           block size = file size
 -F [binplug] force to use that rbin plugin
 -h, -hh      show help message, -hh for long
 -H ([var])   display variable
 -i [file]    run script file
 -I [file]    run script file before the file is opened
 -j           use json for -v, -L and maybe others
 -k [OS/kern] set asm.os (linux, macos, w32, netbsd, ...)
 -l [lib]     load plugin file
 -L           list supported IO plugins
 -m [addr]    map file at given address (loadaddr)
 -M           do not demangle symbol names
 -n, -nn      do not load RBin info (-nn only load bin structures)
 -N           do not load user settings and scripts
 -NN          do not load any script or plugin
 -q           quiet mode (no prompt) and quit after -i
 -qq          quit after running all -c and -i
 -Q           quiet mode (no prompt) and quit faster (quickLeak=true)
 -p [prj]     use project, list if no arg, load if no file
 -P [file]    apply rapatch file and quit
 -r [rarun2]  specify rarun2 profile to load (same as -e dbg.profile=X)
 -R [rr2rule] specify custom rarun2 directive
 -s [addr]    initial seek
 -S           start r2 in sandbox mode
 -T           do not compute file hashes
 -u           set bin.filter=false to get raw sym/sec/cls names
 -v, -V       show radare2 version (-V show lib versions)
 -w           open file in write mode
 -x           open without exec-flag (asm.emu will not work), See io.exec
 -X           same as -e bin.usextr=false (useful for dyldcache)
 -z, -zz      do not load strings or load them even in raw
```

***

**radiff2**

Unified binary diffing utility

```
root@kali:~# radiff2 -h
Usage: radiff2 [-abBcCdeGhijnrOpqsSxuUvVzZ] [-A[A]] [-g sym] [-m graph_mode][-t %] [file] [file]
  -a [arch]  specify architecture plugin to use (x86, arm, ..)
  -A [-A]    run aaa or aaaa after loading each binary (see -C)
  -b [bits]  specify register size for arch (16 (thumb), 32, 64, ..)
  -B         output in binary diff (GDIFF)
  -c         count of changes
  -C         graphdiff code (columns: off-A, match-ratio, off-B) (see -A)
  -d         use delta diffing
  -D         show disasm instead of hexpairs
  -e [k=v]   set eval config var value for all RCore instances
  -g [sym|off1,off2]   graph diff of given symbol, or between two offsets
  -G [cmd]   run an r2 command on every RCore instance created
  -i         diff imports of target files (see -u, -U and -z)
  -j         output in json format
  -n         print bare addresses only (diff.bare=1)
  -m [aditsjJ]  choose the graph output mode
  -O         code diffing with opcode bytes only
  -p         use physical addressing (io.va=0)
  -q         quiet mode (disable colors, reduce output)
  -r         output in radare commands
  -s         compute edit distance (no substitution, Eugene W. Myers' O(ND) diff algorithm)
  -ss        compute Levenshtein edit distance (substitution is allowed, O(N^2))
  -S [name]  sort code diff (name, namelen, addr, size, type, dist) (only for -C or -g)
  -t [0-100] set threshold for code diff (default is 70%)
  -x         show two column hexdump diffing
  -X         show two column hexII diffing
  -u         unified output (---+++)
  -U         unified output using system 'diff'
  -v         show version information
  -V         be verbose (current only for -s)
  -z         diff on extracted strings
  -Z         diff code comparing zignatures

Graph Output formats: (-m [mode])
  <blank/a>  Ascii art
  s          r2 commands
  d          Graphviz dot
  g          Graph Modelling Language (gml)
  j          json
  J          json with disarm
  k          SDB key-value
  t          Tiny ascii art
  i          Interactive ascii art
```

***

**rafind2**

Advanced command-line hexadecimal editor

```
root@kali:~# rafind2 -h
Usage: rafind2 [-mXnzZhqv] [-a align] [-b sz] [-f/t from/to] [-[e|s|S] str] [-x hex] -|file|dir ..
 -a [align] only accept aligned hits
 -b [size]  set block size
 -c         disable colourful output (mainly for for -X)
 -e [regex] search for regex matches (can be used multiple times)
 -f [from]  start searching from address 'from'
 -F [file]  read the contents of the file and use it as keyword
 -h         show this help
 -i         identify filetype (r2 -nqcpm file)
 -j         output in JSON
 -L         List all io plugins (same as r2 for now)
 -m         magic search, file-type carver
 -M [str]   set a binary mask to be applied on keywords
 -n         do not stop on read errors
 -r         print using radare commands
 -s [str]   search for a string (more than one string can be passed)
 -S [str]   search for a wide string (more than one string can be passed).
 -t [to]    stop search at address 'to'
 -q         quiet: fewer output do not show headings or filenames.
 -v         print version and exit
 -x [hex]   search for hexpair string (909090) (can be used multiple times)
 -X         show hexdump of search results
 -z         search for zero-terminated strings
 -Z         show string found on each search hit
```

***

**ragg2**

Radare2 frontend for r\_egg, compile programs into tiny binaries for x86-32/64 and arm.

```
root@kali:~# ragg2 -h
Usage: ragg2 [-FOLsrxhvz] [-a arch] [-b bits] [-k os] [-o file] [-I path]
             [-i sc] [-E enc] [-B hex] [-c k=v] [-C file] [-p pad] [-q off]
             [-S string] [-f fmt] [-nN dword] [-dDw off:hex] [-e expr] file|f.asm|-
 -a [arch]       select architecture (x86, mips, arm)
 -b [bits]       register size (32, 64, ..)
 -B [hexpairs]   append some hexpair bytes
 -c [k=v]        set configuration options
 -C [file]       append contents of file
 -d [off:dword]  patch dword (4 bytes) at given offset
 -D [off:qword]  patch qword (8 bytes) at given offset
 -e [egg-expr]   take egg program from string instead of file
 -E [encoder]    use specific encoder. see -L
 -f [format]     output format (raw, c, pe, elf, mach0, python, javascript)
 -F              output native format (osx=mach0, linux=elf, ..)
 -h              show this help
 -i [shellcode]  include shellcode plugin, uses options. see -L
 -I [path]       add include path
 -k [os]         operating system's kernel (linux,bsd,osx,w32)
 -L              list all plugins (shellcodes and encoders)
 -n [dword]      append 32bit number (4 bytes)
 -N [dword]      append 64bit number (8 bytes)
 -o [file]       output file
 -O              use default output file (filename without extension or a.out)
 -p [padding]    add padding after compilation (padding=n10s32)
                 ntas : begin nop, trap, 'a', sequence
                 NTAS : same as above, but at the end
 -P [size]       prepend debruijn pattern
 -q [fragment]   debruijn pattern offset
 -r              show raw bytes instead of hexpairs
 -s              show assembler
 -S [string]     append a string
 -v              show version
 -w [off:hex]    patch hexpairs at given offset
 -x              execute
 -X [hexpairs]   execute rop chain, using the stack provided
 -z              output in C string syntax
```

***

**rahash2**

Block based hashing utility

```
root@kali:~# rahash2 -h
Usage: rahash2 [-BhjkLqrv] [-b S] [-a A] [-c H] [-E A] [-s S] [-f O] [-t O] [file] ...
 -a algo     comma separated list of algorithms (default is 'sha256')
 -b bsize    specify the size of the block (instead of full file)
 -B          show per-block hash
 -c hash     compare with this hash
 -e          swap endian (use little endian)
 -E algo     encrypt. Use -S to set key and -I to set IV
 -D algo     decrypt. Use -S to set key and -I to set IV
 -f from     start hashing at given address
 -i num      repeat hash N iterations
 -I iv       use give initialization vector (IV) (hexa or s:string)
 -j          output in json
 -S seed     use given seed (hexa or s:string) use ^ to prefix (key for -E)
             (- will slurp the key from stdin, the @ prefix points to a file
 -k          show hash using the openssh's randomkey algorithm
 -q          run in quiet mode (-qq to show only the hash)
 -L          list all available algorithms (see -a)
 -r          output radare commands
 -s string   hash this string instead of files
 -t to       stop hashing at given address
 -x hexstr   hash this hexpair string instead of files
 -v          show version information
```

***

**rarun2**

Radare2 utility to run programs in exotic environments

```
root@kali:~# rarun2 -h
Usage: rarun2 -v|-t|script.rr2 [directive ..]
program=/bin/ls
arg1=/bin
# arg2=hello
# arg3="hello\nworld"
# arg4=:048490184058104849
# arg5=:!ragg2 -p n50 -d 10:0x8048123
# 
# arg7=@300@ABCD # 300 chars filled with ABCD pattern
# system=r2 -
# daemon=false
# aslr=no
setenv=FOO=BAR
# unsetenv=FOO
# clearenv=true
# envfile=environ.txt
timeout=3
# timeoutsig=SIGTERM # or 15
# connect=localhost:8080
# listen=8080
# pty=false
# fork=true
# bits=32
# pid=0
# pidfile=/tmp/foo.pid
# #sleep=0
# #maxfd=0
# #execve=false
# #maxproc=0
# #maxstack=0
# #core=false
# #stdio=blah.txt
# #stderr=foo.txt
# stdout=foo.txt
# stdin=input.txt # or !program to redirect input from another program
# input=input.txt
# chdir=/
# chroot=/mnt/chroot
# libpath=$PWD:/tmp/lib
# r2preload=yes
# preload=/lib/libfoo.so
# setuid=2000
# seteuid=2000
# setgid=2001
# setegid=2001
# nice=5
```

***

**rasign2**

```
root@kali:~# rasign2 -h
Usage: rasign2 [options] [file]
 -a [-a]          add extra 'a' to analysis command
 -A               make signatures from all .o files in the provided .a file
 -f               interpret the file as a FLIRT .sig file and dump signatures
 -h               help menu
 -j               show signatures in json
 -o sigs.sdb      add signatures to file, create if it does not exist
 -q               quiet mode
 -r               show output in radare commands
 -S               perform operation on sdb signature file ('-o -' to save to same file)
 -s signspace     save all signatures under this signspace
 -c               add collision signatures before writing file
 -v               show version information
 -m               merge/overwrite signatures with same name
Examples:
  rasign2 -o libc.sdb libc.so.6
```

***

**rasm2**

Radare2 assembler and disassembler tool

```
root@kali:~# rasm2 -h
Usage: rasm2 [-ACdDehLBvw] [-a arch] [-b bits] [-o addr] [-s syntax]
             [-f file] [-F fil:ter] [-i skip] [-l len] 'code'|hex|-
 -a [arch]    Set architecture to assemble/disassemble (see -L)
 -A           Show Analysis information from given hexpairs
 -b [bits]    Set cpu register size (8, 16, 32, 64) (RASM2_BITS)
 -B           Binary input/output (-l is mandatory for binary input)
 -c [cpu]     Select specific CPU (depends on arch)
 -C           Output in C format
 -d, -D       Disassemble from hexpair bytes (-D show hexpairs)
 -e           Use big endian instead of little endian
 -E           Display ESIL expression (same input as in -d)
 -f [file]    Read data from file
 -F [in:out]  Specify input and/or output filters (att2intel, x86.pseudo, ...)
 -h, -hh      Show this help, -hh for long
 -i [len]     ignore/skip N bytes of the input buffer
 -j           output in json format
 -k [kernel]  Select operating system (linux, windows, darwin, ..)
 -l [len]     Input/Output length
 -L           List RAsm plugins: (a=asm, d=disasm, A=analyze, e=ESIL)
 -LL          List RAnal plugins
 -o,-@ [addr] Set start address for code (default 0)
 -O [file]    Output file name (rasm2 -Bf a.asm -O a)
 -p           Run SPP over input for assembly
 -q           quiet mode
 -r           output in radare commands
 -s [syntax]  Select syntax (intel, att)
 -v           Show version information
 -x           Use hex dwords instead of hex pairs when assembling.
 -w           What's this instruction for? describe opcode
 If '-l' value is greater than output length, output is padded with nops
 If the last argument is '-' reads from stdin
Environment:
 RASM2_NOPLUGINS   do not load shared plugins (speedup loading)
 RASM2_ARCH        same as rasm2 -a
 RASM2_BITS        same as rasm2 -b
 R2_DEBUG          if defined, show error messages and crash signal
 R2_DEBUG_ASSERT=1 lldb -- r2 to get proper backtrace of the runtime assert
```

***

**ravc2**

Radare version control

```
root@kali:~# ravc2 -h
Usage: ravc2 [action] [file ...]
 init            initialize repository in current directory
 add [file ..]   add files to the current repository
 checkout [name] checkout given branch name
 log             list commits in current branch
 branch          list all available branches
 commit [a] [m] [f] perform a commit with the added files
 branch [name]   change to another branch
Environment:
 RAVC2_USER=[name] Override cfg.user value to author commit.
Examples:
  ravc2 init
  man ravc2
```

***

**rax2**

Radare base converter

```
root@kali:~# rax2 -h
Usage: rax2 [options] [expr ...]
  =[base]                      ;  rax2 =10 0x46 -> output in base 10
  int     ->  hex              ;  rax2 10
  hex     ->  int              ;  rax2 0xa
  -int    ->  hex              ;  rax2 -77
  -hex    ->  int              ;  rax2 0xffffffb3
  int     ->  bin              ;  rax2 b30
  int     ->  ternary          ;  rax2 t42
  bin     ->  int              ;  rax2 1010d
  ternary ->  int              ;  rax2 1010dt
  float   ->  hex              ;  rax2 3.33f
  hex     ->  float            ;  rax2 Fx40551ed8
  oct     ->  hex              ;  rax2 35o
  hex     ->  oct              ;  rax2 Ox12 (O is a letter)
  bin     ->  hex              ;  rax2 1100011b
  hex     ->  bin              ;  rax2 Bx63
  ternary ->  hex              ;  rax2 212t
  hex     ->  ternary          ;  rax2 Tx23
  raw     ->  hex              ;  rax2 -S < /binfile
  hex     ->  raw              ;  rax2 -s 414141
  -l                           ;  append newline to output (for -E/-D/-r/..
  -a      show ascii table     ;  rax2 -a
  -b      bin -> str           ;  rax2 -b 01000101 01110110
  -B      str -> bin           ;  rax2 -B hello
  -d      force integer        ;  rax2 -d 3 -> 3 instead of 0x3
  -e      swap endianness      ;  rax2 -e 0x33
  -D      base64 decode        ;
  -E      base64 encode        ;
  -f      floating point       ;  rax2 -f 6.3+2.1
  -F      stdin slurp code hex ;  rax2 -F < shellcode.[c/py/js]
  -h      help                 ;  rax2 -h
  -i      dump as C byte array ;  rax2 -i < bytes
  -I      IP address <-> LONG  ;  rax2 -I 3530468537
  -k      keep base            ;  rax2 -k 33+3 -> 36
  -K      randomart            ;  rax2 -K 0x34 1020304050
  -L      bin -> hex(bignum)   ;  rax2 -L 111111111 # 0x1ff
  -n      binary number        ;  rax2 -n 0x1234 # 34120000
  -o      octalstr -> raw      ;  rax2 -o \162 \62 # r2
  -N      binary number        ;  rax2 -N 0x1234 # \x34\x12\x00\x00
  -r      r2 style output      ;  rax2 -r 0x1234
  -s      hexstr -> raw        ;  rax2 -s 43 4a 50
  -S      raw -> hexstr        ;  rax2 -S < /bin/ls > ls.hex
  -t      tstamp -> str        ;  rax2 -t 1234567890
  -x      hash string          ;  rax2 -x linux osx
  -u      units                ;  rax2 -u 389289238 # 317.0M
  -w      signed word          ;  rax2 -w 16 0xffff
  -v      version              ;  rax2 -v
```

***

Updated on: 2023-Mar-08\


***
