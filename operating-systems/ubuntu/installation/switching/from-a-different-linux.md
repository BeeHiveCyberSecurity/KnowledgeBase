# From a different Linux



This page discusses practical differences between Ubuntu and other Linux distributions. See also the all-systems switching guide. If you are switching from Mac OS X, see switching from OS X.

Ubuntu is based on Debian, so many tasks are the same in Ubuntu as they are in Debian.

### Installing Software <a href="#installing_software" id="installing_software"></a>

Like all Debian-based distributions, software is installed in Ubuntu with _APT_. This is similar to _yum_, which is used by RedHat-based distributions. If you prefer the command-line, you should install packages with apt-get. Alternatively, _System > Administration > Synaptic Package Manager_ is a graphical interface to APT.

See Installing Software for information on installing packages.

### Performing Administrative Tasks <a href="#performing_administrative_tasks" id="performing_administrative_tasks"></a>

In Ubuntu, you are recommended to run programs with sudo instead of logging in as root with su. Advantages of sudo include:

* You can't do anything really bad to your system unless you use sudo each time.
* You don't have to remember a root password - **sudo only needs your own account's password.**
* sudo remembers for a limited time that you used your password, so you won't have to enter your password every time you use it.

At first, only the user you create during installation will have access to sudo. To allow additional users to use sudo, add them to the _admin_ group.

#### Using Sudo <a href="#using_sudo" id="using_sudo"></a>

To run a command with root privileges, simply open a terminal and type:

```
sudo <command>
```

Replace \<command> with the command you wish to use. Sudo will ask for your **normal user password**; enter it and press _return_ to run the command.

Graphical equivalents to sudo include gksudo and kdesudo. When one of these programs runs, a dialog box will appear asking you to enter your **normal user password**. Enter your user password and click _Continue_ or press the enter button on your keyboard.

To run a proper root shell you can do the following:

```
sudo -i
```

This will ask for your normal user password, enter it and you will be at the root prompt.

### Command Line configuration (aliases and inputrc) <a href="#command_line_configuration_.28aliases_and_inputrc.29" id="command_line_configuration_.28aliases_and_inputrc.29"></a>

This section is written for Mandrake/Mandriva users, but probably applies generally.

#### Useful Shell aliases <a href="#useful_shell_aliases" id="useful_shell_aliases"></a>

Mandriva defines the following aliases in /etc/profile.d/alias.sh, which make the shell faster to use. They could also go in your \~/.bashrc:

| alias ls='ls -F --color=auto' | # make ls coloured, and append characters to denote filetype ( eg trailing / on directory names) |
| ----------------------------- | ------------------------------------------------------------------------------------------------ |
| alias l='ls'                  | # short for ls                                                                                   |
| alias l.='ls -d .\*'          | # show only hidden files                                                                         |
| alias la='ls -a'              | # list all files                                                                                 |
| alias ll='ls -l'              | # long format listing                                                                            |
| alias lsd='ls -d \*/'         | # list only directories                                                                          |
| alias lx='ls -X'              | # list, order by extension                                                                       |
| alias p='cd -'                | # previous directory                                                                             |
| alias s='cd ..'               | # short for cd ..                                                                                |
| alias cd..='cd ..'            | # allow omission of space in cd ..                                                               |
| alias rd='rmdir'              | # Remove a directory                                                                             |
| alias md='mkdir'              | # Make a directory                                                                               |

The following make cp, rm, and mv interactive by default, so you don't overwrite a file by mistake. Most people think this is useful, but some think it makes one careless, as one might come to rely upon the implicit -i, on some other system which doesn't have it.

| alias mv='mv -i' |
| ---------------- |
| alias rm='rm -i' |
| alias cp='cp -i' |

Note that these aliases _do not work_ when running a command as root using sudo. One workaround for this is to add alias sudo="sudo " to your .bashrc (note the extra space in the quotes). This will allow the first word after 'sudo' to be substituted if an alias exists.[1](broken-reference)

#### Tab Completion Enhancements <a href="#tab_completion_enhancements" id="tab_completion_enhancements"></a>

Mandriva defines the following in /etc/inputrc, which prints the list of options and then repeats the prompt where you were:

```
set show-all-if-ambiguous on
```

Putting this in /etc/inputrc or \~/.inputrc will add this function to Ubuntu.

### Music, Movies, DVD Playback and Java <a href="#music.2c_movies.2c_dvd_playback_and_java" id="music.2c_movies.2c_dvd_playback_and_java"></a>

Getting file formats restricted by patents or copyright such as movies and music to play on your Ubuntu system is simple (although not as simple as it could be). See RestrictedFormats. Java is simple too.

### Services, Chkconfig and Initscripts <a href="#services.2c_chkconfig_and_initscripts" id="services.2c_chkconfig_and_initscripts"></a>

Users of Red Hat and Mandriva will be used to configuring which services run by using chkconfig command. chkconfig is not available in Ubuntu, but you can install sysv-rc-conf instead.

To start and stop services, it's necessary to invoke the init.d script directly: /etc/init.d/ssh start rather than service sshd start. If you want to have the 'service' syntax back, add this to root's .bashrc:

```
function service (){ /etc/init.d/$@ ;}  
```

Since Intrepid, you can also install the following package: [_**sysvinit-utils**_](apt:sysvinit-utils), which provides the service command.

Ubuntu runs in runlevel 3 by default, whereas RedHat and Mandriva use runlevel 5 for graphics, and 3 for console. Ubuntu also has an _extra_ rcX.d directory, /etc/rcS.d, which runs at boot-up. Packages like udev are started from rcS.d. There are some helpful README files in the /etc/rcX.d directories.

### Environment Variables <a href="#environment_variables" id="environment_variables"></a>

See Environment Variables for a full guide to the use of environment variables in Ubuntu.

### Moving to Ubuntu from openSUSE <a href="#moving_to_ubuntu_from_opensuse" id="moving_to_ubuntu_from_opensuse"></a>

This section documents a few surprises that long-term openSUSE users may encounter when moving to Ubuntu. It was inspired by a recent transition from openSUSE 11.2 to Ubuntu 10.10.

#### Shell Scripts <a href="#shell_scripts" id="shell_scripts"></a>

Some of your tried and tested shell scripts may break in a surprising manner if the first line is #!/bin/sh and you have used features specific to the bash shell. It is tempting to change the first line to #!/bin/bash to get things working, but you may not have realised that that Ubuntu uses the **d**ash shell as the default shell. Should you wish to do things in the Ubuntu way, consider searching the web using the keyword **bashisms** to understand the differences, and fixing your scripts accordingly.

#### Editing Using vi <a href="#editing_using_vi" id="editing_using_vi"></a>

Experienced users, even those who normally use emacs or xemacs, find themselves using vi to configure things to suit their way of working during the first hour or two of a fresh installation. Ubuntu has a mechanism to choose a preferred editor, but it is frustrating during the first hours when all you want is a working version of vi that doesn't dump escape codes over your file when you use the arrow keys in insert mode, and when nano just looks weird.

The following code snippet, added to your .bashrc, should ease the transition until you figure out how Ubuntu does things.

```
# Voodoo for sudo.
alias rm='/bin/rm -i'
alias vi='/usr/bin/vim.tiny'
alias sudo='sudo '
alias visudo='EDITOR=/usr/bin/vim.tiny /usr/sbin/visudo'
```

#### Using sudo <a href="#using_sudo" id="using_sudo"></a>

Ubuntu is keen to encourage good practice regarding the preferred use of sudo. As always, it is dangerous to edit /etc/sudoers, even when using sudo visudo. Ubuntu would like you to make your changes in separate files inside the /etc/sudoers.d directory. This is fine, but it does not work out-of-the-box on Ubuntu 10.10 should you wish to use NOPASSWD. This is because the #includedir /etc/sudoers.d directive is found on the last-line-but-one of /etc/sudoers by default; moving it to the end makes NOPASSWD work as one expects.

### Documentation <a href="#documentation" id="documentation"></a>

There are a few good resources you can turn to if you need further help with Ubuntu, these include:

* [http://help.ubuntu.com](http://help.ubuntu.com/) - The main source of Ubuntu documentation
* [Forums](http://www.ubuntuforums.org/), [mailing lists](http://lists.ubuntu.com/) and IRC (irc.freenode.net - #ubuntu)
