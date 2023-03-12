# Technology

### Computer Languages[¶](broken-reference)

We use a variety of computer languages in Linux Mint.

You don’t need to know them all and you don’t need to know them well. It really depends on which project you want to work and what you want to achieve.

Here are the languages we use the most.

#### Python

Scripts which run in terminals or in the backgrounds are usually either written in [Bash](https://en.wikipedia.org/wiki/Bash\_\(Unix\_shell\)) or in [Python](https://www.python.org/).

Some software applications and most configuration tools are also written in Python.

The advantage of Python is that it is easy to learn and fast to develop with.

#### C

Many software applications and most libraries are written in [C](https://en.wikipedia.org/wiki/C\_\(programming\_language\)).

The C language is low-level, hard to master and tedious to develop with, but it gives fast performance and it’s the most supported language in Linux (everything is accessible from C).

#### Javascript

The graphical elements of Cinnamon, as well as Cinnamon applets, desklets and extensions are written in [Javascript](https://en.wikipedia.org/wiki/JavaScript).

#### Vala

[Vala](https://wiki.gnome.org/Projects/Vala) is used in Slick Greeter (the login screen).

### GNOME Toolkit and libraries

All our user interfaces use [GTK3](https://developer.gnome.org/gtk3/stable/) toolkit.

Our development relies heavily on the [GNOME libraries](https://developer.gnome.org/), in particular we use Gio, GLib, GObject and dconf a lot.

In C we access these libraries directly.

In Python and Javascript we access them via [GObject Introspection](https://gi.readthedocs.io/en/latest/).

### Tools

#### Development environment

To write and edit code, you can use anything you want. Some people prefer lightweight editors while others prefer full-fledge IDEs. It’s a matter of taste. Development is all about fun, so what matters the most is that you love the tools you use.

If you’re not sure what to use, have a look around and try a few editors/IDE until you find your favorite one.

Many developers within the team use [Sublime](https://www.sublimetext.com/).

```
apt update
apt install sublime-text
```

If you install Sublime, also install its [Package Control](https://packagecontrol.io/installation) and then use it to install the _GitGutter_ and _TrailingSpaces_ extensions.

[Visual Studio Code](https://code.visualstudio.com/) is also very popular within the team.

You can also check out [Atom](https://atom.io/), [Brackets](http://brackets.io/) and [Geany](https://www.geany.org/).

And if you want a complete IDE, there’s also [Eclipse](https://www.eclipse.org/) and [Netbeans](https://netbeans.apache.org/).

#### Version control

There’s less choice when it comes to version control because we’re all using git and nothing else. All our code is version-controlled with it.

That being said, you don’t necessarily have to use the git command line.

Here are a few tools you can use to make using git easier.

_gitk_ is ugly and looks dated (it was developed in Tcl/Tk) but it’s very useful to quickly look at the commit history, to create branches and to cherry pick.

You can install it from the repositories:

```
apt update
apt install gitk
cd ~/Sandbox/
git clone https://github.com/linuxmint/mintsystem.git
cd mintsystem
gitk
```

From a project directory, simply type _gitk_ to see the history of commits. You can also specify a branch name to see that branch instead, or a subdirectory to only see the history of a particular directory.

_gitg_ is very similar and it looks better (it’s using Gtk), but its feature set is slightly different.

```
apt update
apt install gitg
cd ~/Sandbox/
git clone https://github.com/linuxmint/mintsystem.git
cd mintsystem
gitg
```

From the repository you can also look at _git-cola_ and _git-gui_.

If you’re looking for a more complete solution, have a look at [Gitkraken](https://www.gitkraken.com/).

And last but not least, check the plugins and features available in your IDE/editor. Visual Studio Code, Atom and Sublime in particular come with a lot of support for Git and Github.

#### Glade

We can write our user interfaces in programming language, or we can use Glade and draw them with the mouse.

[Glade](https://glade.gnome.org/) is a tool to design and edit GTK user interfaces and save them in XML (in a .glade or .ui file).

```
apt update
apt install glade
```

Once a user interface is saved, we simply tell our program to open that file and we can access the widgets from it programmatically.

Many of our projects separate the code from the user interface.

#### devhelp

Devhelp shows the reference manuals for the development libraries installed on your computer. For most libraries, the documentation is included in their _-dev_ or _-doc_ package (for instance, if you’re working with GTK3, make sure to install _libgtk-3-dev_ and _libgtk-3-doc_).

```
apt update
apt install devhelp
```

You can launch DevHelp from the applications menu and use it to browse or search the libraries reference manuals. You’ll often need to check the syntax or the arguments of a particular function. It’s nice to be able to get the information locally without having to search online.

#### d-feet

Some programs use DBus to communicate with others. We use d-feet to browse and troubleshoot DBus.

```
apt update
apt install d-feet
```

With d-feet you can quickly find a service on DBus, browse its interface and even call some of its functions manually.

#### meld

Meld is a visual diff tool. It shows the differences between two files and it’s great at it.

```
apt update
apt install meld
```

#### Other cool tools

Most of our configuration is stored in dconf and we use gsettings (from the command line) to look at it or modify it. If you want to do it graphically, you can install dconf-editor.

awf is useful to test widgets when working on GTK themes.

```
apt update
apt install awf dconf-editor
```
