---
description: >-
  GDB is an open-source debugger used to find and fix errors in programs written
  in C, C++, Fortran, and other languages, with powerful features and plugins.
---

# 🐛 gdb

GDB, or the GNU Project Debugger, is a software tool used for debugging programs written in C, C++, Fortran, and other programming languages. It is an open-source debugger that is included in most Unix-like operating systems, such as Linux, and is widely used by developers to find and fix errors in their code.

GDB provides a command-line interface that allows developers to interact with their programs at a low level. It can be used to set breakpoints, examine the state of a program, and step through code line by line. GDB also provides features such as memory and register inspection, which can be invaluable when tracking down memory leaks and other low-level issues.

One of the most powerful features of GDB is its ability to attach to a running process. This allows developers to inspect a program while it is executing, making it possible to find bugs that may not be reproducible in a test environment. GDB can also be used to profile a program's performance, allowing developers to identify bottlenecks and optimize their code.

GDB supports a wide range of debugging features, including conditional breakpoints, watchpoints, and signals. Conditional breakpoints allow developers to stop execution when a particular condition is met, while watchpoints allow them to monitor changes to a specific variable or memory address. Signals can be used to catch and handle exceptions, allowing developers to gracefully handle errors in their code.

In addition to its core features, GDB also has a number of extensions and plugins that can be used to enhance its capabilities. For example, the Python extension allows developers to write scripts that interact with GDB, while the reverse debugging plugin makes it possible to step backwards through a program's execution.

While GDB can be a powerful tool for developers, it can also be somewhat daunting to use, particularly for those who are new to debugging. However, there are many resources available online that can help developers learn how to use GDB effectively, including tutorials, blog posts, and forums where they can ask questions and get advice from more experienced developers.

In summary, GDB is an essential tool for developers who need to debug programs written in C, C++, Fortran, and other programming languages. Its ability to attach to a running process and inspect its state in real-time makes it an invaluable tool for finding and fixing bugs, while its wide range of features and extensions provide developers with the flexibility they need to solve even the most complex problems.

### Packages and Binaries:

#### gdb <a href="#gdb" id="gdb"></a>

GDB is a source-level debugger, capable of breaking programs at any specific line, displaying variable values, and determining where errors occurred. Currently, gdb supports C, C++, D, Objective-C, Fortran, Java, OpenCL C, Pascal, assembly, Modula-2, Go, and Ada. A must-have for any serious programmer.

**Installed size:** `11.35 MB`\
**How to install:** `sudo apt install gdb`

<details>

<summary>Dependencies:</summary>

* libbabeltrace1
* libc6
* libdebuginfod1
* libexpat1
* libgcc-s1
* libgmp10
* libipt2
* liblzma5
* libmpfr6
* libncursesw6
* libpython3.11
* libreadline8
* libsource-highlight4v5
* libstdc++6
* libtinfo6
* libxxhash0
* libzstd1
* zlib1g

</details>

**gcore**

Generate core files for running processes

```
:~# gcore -h
usage:  gcore [-a] [-o prefix] pid1 [pid2...pidN]
```

***

**gcore**

Generate core files for running processes

```
:~# gcore -h
usage:  gcore [-a] [-o prefix] pid1 [pid2...pidN]
```

***

**gdb**

```
:~# gdb -h
This is the GNU debugger.  Usage:

    gdb [options] [executable-file [core-file or process-id]]
    gdb [options] --args executable-file [inferior-arguments ...]

Selection of debuggee and its files:

  --args             Arguments after executable-file are passed to inferior.
  --core=COREFILE    Analyze the core dump COREFILE.
  --exec=EXECFILE    Use EXECFILE as the executable.
  --pid=PID          Attach to running process PID.
  --directory=DIR    Search for source files in DIR.
  --se=FILE          Use FILE as symbol file and executable file.
  --symbols=SYMFILE  Read symbols from SYMFILE.
  --readnow          Fully read symbol files on first access.
  --readnever        Do not read symbol files.
  --write            Set writing into executable and core files.

Initial commands and command files:

  --command=FILE, -x Execute GDB commands from FILE.
  --init-command=FILE, -ix
		     Like -x but execute commands before loading inferior.
  --eval-command=COMMAND, -ex
		     Execute a single GDB command.
		     May be used multiple times and in conjunction
		     with --command.
  --init-eval-command=COMMAND, -iex
		     Like -ex but before loading inferior.
  --nh               Do not read ~/.gdbinit.
  --nx               Do not read any .gdbinit files in any directory.

Output and user interface control:

  --fullname         Output information used by emacs-GDB interface.
  --interpreter=INTERP
		     Select a specific interpreter / user interface.
  --tty=TTY          Use TTY for input/output by the program being debugged.
  -w                 Use the GUI interface.
  --nw               Do not use the GUI interface.
  --tui              Use a terminal user interface.
  -q, --quiet, --silent
		     Do not print version number on startup.

Operating modes:

  --batch            Exit after processing options.
  --batch-silent     Like --batch, but suppress all gdb stdout output.
  --return-child-result
		     GDB exit code will be the child's exit code.
  --configuration    Print details about GDB configuration and then exit.
  --help             Print this message and then exit.
  --version          Print version information and then exit.

Remote debugging options:

  -b BAUDRATE        Set serial port baud rate used for remote debugging.
  -l TIMEOUT         Set timeout in seconds for remote debugging.

Other options:

  --cd=DIR           Change current directory to DIR.
  --data-directory=DIR, -D
		     Set GDB's data-directory to DIR.

At startup, GDB reads the following early init files and executes their
commands:
   None found.

At startup, GDB reads the following init files and executes their commands:
   * system-wide init files: /etc/gdb/gdbinit

For more information, type "help" from within GDB, or consult the
GDB manual (available as on-line info or a printed manual).

Report bugs to <https://www.gnu.org/software/gdb/bugs/>.

You can ask GDB-related questions on the GDB users mailing list
() or on GDB's IRC channel (#gdb on Freenode).
```

***

**gdb**

```
:~# gdb -h
This is the GNU debugger.  Usage:

    gdb [options] [executable-file [core-file or process-id]]
    gdb [options] --args executable-file [inferior-arguments ...]

Selection of debuggee and its files:

  --args             Arguments after executable-file are passed to inferior.
  --core=COREFILE    Analyze the core dump COREFILE.
  --exec=EXECFILE    Use EXECFILE as the executable.
  --pid=PID          Attach to running process PID.
  --directory=DIR    Search for source files in DIR.
  --se=FILE          Use FILE as symbol file and executable file.
  --symbols=SYMFILE  Read symbols from SYMFILE.
  --readnow          Fully read symbol files on first access.
  --readnever        Do not read symbol files.
  --write            Set writing into executable and core files.

Initial commands and command files:

  --command=FILE, -x Execute GDB commands from FILE.
  --init-command=FILE, -ix
		     Like -x but execute commands before loading inferior.
  --eval-command=COMMAND, -ex
		     Execute a single GDB command.
		     May be used multiple times and in conjunction
		     with --command.
  --init-eval-command=COMMAND, -iex
		     Like -ex but before loading inferior.
  --nh               Do not read ~/.gdbinit.
  --nx               Do not read any .gdbinit files in any directory.

Output and user interface control:

  --fullname         Output information used by emacs-GDB interface.
  --interpreter=INTERP
		     Select a specific interpreter / user interface.
  --tty=TTY          Use TTY for input/output by the program being debugged.
  -w                 Use the GUI interface.
  --nw               Do not use the GUI interface.
  --tui              Use a terminal user interface.
  -q, --quiet, --silent
		     Do not print version number on startup.

Operating modes:

  --batch            Exit after processing options.
  --batch-silent     Like --batch, but suppress all gdb stdout output.
  --return-child-result
		     GDB exit code will be the child's exit code.
  --configuration    Print details about GDB configuration and then exit.
  --help             Print this message and then exit.
  --version          Print version information and then exit.

Remote debugging options:

  -b BAUDRATE        Set serial port baud rate used for remote debugging.
  -l TIMEOUT         Set timeout in seconds for remote debugging.

Other options:

  --cd=DIR           Change current directory to DIR.
  --data-directory=DIR, -D
		     Set GDB's data-directory to DIR.

At startup, GDB reads the following early init files and executes their
commands:
   None found.

At startup, GDB reads the following init files and executes their commands:
   * system-wide init files: /etc/gdb/gdbinit

For more information, type "help" from within GDB, or consult the
GDB manual (available as on-line info or a printed manual).

Report bugs to <https://www.gnu.org/software/gdb/bugs/>.

You can ask GDB-related questions on the GDB users mailing list
() or on GDB's IRC channel (#gdb on Freenode).
```

***

**gdb-add-index**

***

**gdbtui**

```
:~# gdbtui -h
This is the GNU debugger.  Usage:

    gdb [options] [executable-file [core-file or process-id]]
    gdb [options] --args executable-file [inferior-arguments ...]

Selection of debuggee and its files:

  --args             Arguments after executable-file are passed to inferior.
  --core=COREFILE    Analyze the core dump COREFILE.
  --exec=EXECFILE    Use EXECFILE as the executable.
  --pid=PID          Attach to running process PID.
  --directory=DIR    Search for source files in DIR.
  --se=FILE          Use FILE as symbol file and executable file.
  --symbols=SYMFILE  Read symbols from SYMFILE.
  --readnow          Fully read symbol files on first access.
  --readnever        Do not read symbol files.
  --write            Set writing into executable and core files.

Initial commands and command files:

  --command=FILE, -x Execute GDB commands from FILE.
  --init-command=FILE, -ix
		     Like -x but execute commands before loading inferior.
  --eval-command=COMMAND, -ex
		     Execute a single GDB command.
		     May be used multiple times and in conjunction
		     with --command.
  --init-eval-command=COMMAND, -iex
		     Like -ex but before loading inferior.
  --nh               Do not read ~/.gdbinit.
  --nx               Do not read any .gdbinit files in any directory.

Output and user interface control:

  --fullname         Output information used by emacs-GDB interface.
  --interpreter=INTERP
		     Select a specific interpreter / user interface.
  --tty=TTY          Use TTY for input/output by the program being debugged.
  -w                 Use the GUI interface.
  --nw               Do not use the GUI interface.
  --tui              Use a terminal user interface.
  -q, --quiet, --silent
		     Do not print version number on startup.

Operating modes:

  --batch            Exit after processing options.
  --batch-silent     Like --batch, but suppress all gdb stdout output.
  --return-child-result
		     GDB exit code will be the child's exit code.
  --configuration    Print details about GDB configuration and then exit.
  --help             Print this message and then exit.
  --version          Print version information and then exit.

Remote debugging options:

  -b BAUDRATE        Set serial port baud rate used for remote debugging.
  -l TIMEOUT         Set timeout in seconds for remote debugging.

Other options:

  --cd=DIR           Change current directory to DIR.
  --data-directory=DIR, -D
		     Set GDB's data-directory to DIR.

At startup, GDB reads the following early init files and executes their
commands:
   None found.

At startup, GDB reads the following init files and executes their commands:
   * system-wide init files: /etc/gdb/gdbinit

For more information, type "help" from within GDB, or consult the
GDB manual (available as on-line info or a printed manual).

Report bugs to <https://www.gnu.org/software/gdb/bugs/>.

You can ask GDB-related questions on the GDB users mailing list
() or on GDB's IRC channel (#gdb on Freenode).
```

***

#### gdb-minimal <a href="#gdb-minimal" id="gdb-minimal"></a>

GDB is a source-level debugger, capable of breaking programs at any specific line, displaying variable values, and determining where errors occurred. Currently, gdb supports C, C++, D, Objective-C, Fortran, Java, OpenCL C, Pascal, assembly, Modula-2, Go, and Ada. A must-have for any serious programmer.

This package contains a minimal version of GDB with optional features disabled.

**Installed size:** `9.67 MB`\
**How to install:** `sudo apt install gdb-minimal`

<details>

<summary>Dependencies:</summary>

* libc6
* libdebuginfod1
* libexpat1
* libgcc-s1
* libgmp10
* libipt2
* liblzma5
* libreadline8
* libstdc++6
* libtinfo6
* libxxhash0
* libzstd1
* zlib1g

</details>

**gcore**

Generate core files for running processes

```
:~# gcore -h
usage:  gcore [-a] [-o prefix] pid1 [pid2...pidN]
```

***

**gdb**

```
:~# gdb -h
This is the GNU debugger.  Usage:

    gdb [options] [executable-file [core-file or process-id]]
    gdb [options] --args executable-file [inferior-arguments ...]

Selection of debuggee and its files:

  --args             Arguments after executable-file are passed to inferior.
  --core=COREFILE    Analyze the core dump COREFILE.
  --exec=EXECFILE    Use EXECFILE as the executable.
  --pid=PID          Attach to running process PID.
  --directory=DIR    Search for source files in DIR.
  --se=FILE          Use FILE as symbol file and executable file.
  --symbols=SYMFILE  Read symbols from SYMFILE.
  --readnow          Fully read symbol files on first access.
  --readnever        Do not read symbol files.
  --write            Set writing into executable and core files.

Initial commands and command files:

  --command=FILE, -x Execute GDB commands from FILE.
  --init-command=FILE, -ix
		     Like -x but execute commands before loading inferior.
  --eval-command=COMMAND, -ex
		     Execute a single GDB command.
		     May be used multiple times and in conjunction
		     with --command.
  --init-eval-command=COMMAND, -iex
		     Like -ex but before loading inferior.
  --nh               Do not read ~/.gdbinit.
  --nx               Do not read any .gdbinit files in any directory.

Output and user interface control:

  --fullname         Output information used by emacs-GDB interface.
  --interpreter=INTERP
		     Select a specific interpreter / user interface.
  --tty=TTY          Use TTY for input/output by the program being debugged.
  -w                 Use the GUI interface.
  --nw               Do not use the GUI interface.
  --tui              Use a terminal user interface.
  -q, --quiet, --silent
		     Do not print version number on startup.

Operating modes:

  --batch            Exit after processing options.
  --batch-silent     Like --batch, but suppress all gdb stdout output.
  --return-child-result
		     GDB exit code will be the child's exit code.
  --configuration    Print details about GDB configuration and then exit.
  --help             Print this message and then exit.
  --version          Print version information and then exit.

Remote debugging options:

  -b BAUDRATE        Set serial port baud rate used for remote debugging.
  -l TIMEOUT         Set timeout in seconds for remote debugging.

Other options:

  --cd=DIR           Change current directory to DIR.
  --data-directory=DIR, -D
		     Set GDB's data-directory to DIR.

At startup, GDB reads the following early init files and executes their
commands:
   None found.

At startup, GDB reads the following init files and executes their commands:
   * system-wide init files: /etc/gdb/gdbinit

For more information, type "help" from within GDB, or consult the
GDB manual (available as on-line info or a printed manual).

Report bugs to <https://www.gnu.org/software/gdb/bugs/>.

You can ask GDB-related questions on the GDB users mailing list
() or on GDB's IRC channel (#gdb on Freenode).
```

***

#### gdb-multiarch <a href="#gdb-multiarch" id="gdb-multiarch"></a>

GDB is a source-level debugger, capable of breaking programs at any specific line, displaying variable values, and determining where errors occurred. Currently, gdb supports C, C++, D, Objective-C, Fortran, Java, OpenCL C, Pascal, assembly, Modula-2, Go, and Ada. A must-have for any serious programmer.

This package contains a version of GDB which supports multiple target architectures.

**Installed size:** `17.75 MB`\
**How to install:** `sudo apt install gdb-multiarch`

<details>

<summary>Dependencies:</summary>

* gdb
* libbabeltrace1
* libc6
* libdebuginfod1
* libexpat1
* libgcc-s1
* libgmp10
* libipt2
* liblzma5
* libmpfr6
* libncursesw6
* libpython3.11
* libreadline8
* libsource-highlight4v5
* libstdc++6
* libtinfo6
* libxxhash0
* libzstd1
* zlib1g

</details>

**gdb-multiarch**

```
:~# gdb-multiarch -h
This is the GNU debugger.  Usage:

    gdb [options] [executable-file [core-file or process-id]]
    gdb [options] --args executable-file [inferior-arguments ...]

Selection of debuggee and its files:

  --args             Arguments after executable-file are passed to inferior.
  --core=COREFILE    Analyze the core dump COREFILE.
  --exec=EXECFILE    Use EXECFILE as the executable.
  --pid=PID          Attach to running process PID.
  --directory=DIR    Search for source files in DIR.
  --se=FILE          Use FILE as symbol file and executable file.
  --symbols=SYMFILE  Read symbols from SYMFILE.
  --readnow          Fully read symbol files on first access.
  --readnever        Do not read symbol files.
  --write            Set writing into executable and core files.

Initial commands and command files:

  --command=FILE, -x Execute GDB commands from FILE.
  --init-command=FILE, -ix
		     Like -x but execute commands before loading inferior.
  --eval-command=COMMAND, -ex
		     Execute a single GDB command.
		     May be used multiple times and in conjunction
		     with --command.
  --init-eval-command=COMMAND, -iex
		     Like -ex but before loading inferior.
  --nh               Do not read ~/.gdbinit.
  --nx               Do not read any .gdbinit files in any directory.

Output and user interface control:

  --fullname         Output information used by emacs-GDB interface.
  --interpreter=INTERP
		     Select a specific interpreter / user interface.
  --tty=TTY          Use TTY for input/output by the program being debugged.
  -w                 Use the GUI interface.
  --nw               Do not use the GUI interface.
  --tui              Use a terminal user interface.
  -q, --quiet, --silent
		     Do not print version number on startup.

Operating modes:

  --batch            Exit after processing options.
  --batch-silent     Like --batch, but suppress all gdb stdout output.
  --return-child-result
		     GDB exit code will be the child's exit code.
  --configuration    Print details about GDB configuration and then exit.
  --help             Print this message and then exit.
  --version          Print version information and then exit.

Remote debugging options:

  -b BAUDRATE        Set serial port baud rate used for remote debugging.
  -l TIMEOUT         Set timeout in seconds for remote debugging.

Other options:

  --cd=DIR           Change current directory to DIR.
  --data-directory=DIR, -D
		     Set GDB's data-directory to DIR.

At startup, GDB reads the following early init files and executes their
commands:
   None found.

At startup, GDB reads the following init files and executes their commands:
   * system-wide init files: /etc/gdb/gdbinit

For more information, type "help" from within GDB, or consult the
GDB manual (available as on-line info or a printed manual).

Report bugs to <https://www.gnu.org/software/gdb/bugs/>.

You can ask GDB-related questions on the GDB users mailing list
() or on GDB's IRC channel (#gdb on Freenode).
```

***

#### gdb-source <a href="#gdb-source" id="gdb-source"></a>

GDB is a source-level debugger, capable of breaking programs at any specific line, displaying variable values, and determining where errors occurred. Currently, gdb supports C, C++, D, Objective-C, Fortran, Java, OpenCL C, Pascal, assembly, Modula-2, Go, and Ada. A must-have for any serious programmer.

This package contains the sources and patches which are needed to build GDB.

**Installed size:** `22.87 MB`\
**How to install:** `sudo apt install gdb-source`

***

#### gdbserver <a href="#gdbserver" id="gdbserver"></a>

GDB is a source-level debugger, capable of breaking programs at any specific line, displaying variable values, and determining where errors occurred. Currently, gdb supports C, C++, D, Objective-C, Fortran, Java, OpenCL C, Pascal, assembly, Modula-2, Go, and Ada. A must-have for any serious programmer.

This package contains gdbserver. Install this to debug remotely from another system where GDB is installed.

**Installed size:** `818 KB`\
**How to install:** `sudo apt install gdbserver`

<details>

<summary>Dependencies:</summary>

* libc6
* libgcc-s1
* libstdc++6

</details>

**gdbserver**

```
:~# gdbserver --help
Usage:	gdbserver [OPTIONS] COMM PROG [ARGS ...]
	gdbserver [OPTIONS] --attach COMM PID
	gdbserver [OPTIONS] --multi COMM

COMM may either be a tty device (for serial debugging),
HOST:PORT to listen for a TCP connection, or '-' or 'stdio' to use 
stdin/stdout of gdbserver.
PROG is the executable program.  ARGS are arguments passed to inferior.
PID is the process ID to attach to, when --attach is specified.

Operating modes:

  --attach              Attach to running process PID.
  --multi               Start server without a specific program, and
                        only quit when explicitly commanded.
  --once                Exit after the first connection has closed.
  --help                Print this message and then exit.
  --version             Display version information and exit.

Other options:

  --wrapper WRAPPER --  Run WRAPPER to start new programs.
  --disable-randomization
                        Run PROG with address space randomization disabled.
  --no-disable-randomization
                        Don't disable address space randomization when
                        starting PROG.
  --startup-with-shell
                        Start PROG using a shell.  I.e., execs a shell that
                        then execs PROG.  (default)
  --no-startup-with-shell
                        Exec PROG directly instead of using a shell.
                        Disables argument globbing and variable substitution
                        on UNIX-like systems.

Debug options:

  --debug               Enable general debugging output.
  --debug-format=OPT1[,OPT2,...]
                        Specify extra content in debugging output.
                          Options:
                            all
                            none
                            timestamp
  --remote-debug        Enable remote protocol debugging output.
  --event-loop-debug    Enable event loop debugging output.
  --disable-packet=OPT1[,OPT2,...]
                        Disable support for RSP packets or features.
                          Options:
                            vCont, T, Tthread, qC, qfThreadInfo and 
                            threads (disable all threading packets).

For more information, consult the GDB manual (available as on-line 
info or a printed manual).
Report bugs to "<http://www.gnu.org/software/gdb/bugs/>".
```

***

Updated on: 2023-Mar-08\


***
