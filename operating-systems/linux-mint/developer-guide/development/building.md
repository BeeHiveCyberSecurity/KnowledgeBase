# Building

Once you’ve installed _mint-dev-tools_, building Linux Mint projects from source is extremely easy.

### Downloading the source code

Use _git clone_ to get the source from github.

For instance, to get the source for mintinstall type:

```
cd ~/Sandbox
git clone https://github.com/linuxmint/mintinstall.git
```

### Building a project for the first time

Use _mint-build_ to build a project for the first time.

_mint-build_ doesn’t just build the project, it also fetches and installs the build dependencies (i.e. the packages which are required for the build to succeed).

To build mintinstall you would type:

```
cd ~/Sandbox/mintinstall
mint-build
```

When the build is complete, the resulting binary .deb packages are located in the parent directory (in this example in _\~/Sandbox_).

### Building a project

If all the build dependencies are already installed for a particular project (this is done by _mint-build_ the first time you build a project), you can build faster by just calling _dpkg-buildpackage_.

To build mintinstall you would type:

```
cd ~/Sandbox/mintinstall
dpkg-buildpackage
```

### Respecting the build order

If new changes in the project you’re trying to build require new changes in another project you might need to build and install that other project first.

In general it’s a good idea to build _mint-common_ and _xapps_ first.
