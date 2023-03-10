# The Basics of Troubleshooting

Troubleshooting Linux can be very confusing due to all of the moving parts. This doc will aim to cover as much as possible while still being understandable. If you believe something is missing or could be improved, please submit an issue to help to try and get this to be as complete as possible.

[Log files](broken-reference)

* `/var/log/` - Contains most log files might be needed to troubleshoot an issue
* `/var/log/syslog` - Contains messages from the kernel and other programs and services
* `/var/log/apt/history.log`, `/var/log/apt/term.log`, and `/var/log/dpkg.log` - All are files that will help to show where an error occurred during an package update
* `/var/log/auth.log` - Contains system authorization events
* `/var/log/dmesg` - Contains kernel ring buffer information
* `/var/log/message` - Contains system messages
* `/var/log/Xorg.0.log` - Contains log messages from X
* `/var/log/lightdm/lightdm.log` - Contains events from lightdm
* `/var/log/kern.log` - Contains kernel messages only
* `~/.xsession-errors` - Contains errors that occur within the Linux graphical environment from the X window session

Different programs may have log files in their own locations as well. Checking the man pages (`man package`) will likely provide the information needed to either find the file or find a different location that will contain the information you need.

[Commands and processes](broken-reference)

Anything mentioned should have their man page looked at for more details. Additionally, if there is an issue with a graphical tool that does not display an error try running it through the command line.

* [journalctl](https://manpages.debian.org/buster/systemd/journalctl.1.en.html) - Will show the contents of the systemd journal
* [dmesg](https://manpages.debian.org/buster/util-linux/dmesg.1.en.html) - Will show kernel events, allows to see errors
* [ip](https://manpages.debian.org/buster/iproute2/ip.8.en.html) - Network configuration
* [service](https://manpages.debian.org/buster/init-system-helpers/service.8.en.html) - runs a System V init script or upstart job
* [systemctl](https://manpages.debian.org/buster/systemd/systemctl.1.en.html) - Used to control the systemd system and service manager
* [df](https://manpages.debian.org/buster/coreutils/df.1.en.html) - See how much disk space is free, which may prevent certain things
* [top](https://manpages.debian.org/buster/procps/top.1.en.html) - See lots of information about the computer, can help to pinpoint CPU, memory, etc issues
* [dpkg](https://manpages.debian.org/buster/dpkg/dpkg.1.en.html) - Allows for troubleshooting of packages (along with normal functionality)
* [apt](https://manpages.debian.org/buster/apt/apt.8.en.html) - Also allows for troubleshooting of packages (along with normal functionality)
* [ps](https://manpages.debian.org/buster/procps/ps.1.en.html) and [kill](https://manpages.debian.org/buster/procps/kill.1.en.html) - Combo to find a process that may be causing problems and kill it
* [tail](https://manpages.debian.org/buster/coreutils/tail.1.en.html) (-f specifically) - lets you watch log files be written to in real time

[The most important tool](broken-reference)

Google.

Google will be the most important utility for almost all cases of troubleshooting. Utilizing log files and error outputs, somewhere on Google there will likely be a reason and a solution.
