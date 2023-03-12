# Setup

This chapter explains how to get your computer set up.

### Create a Sandbox[¶](broken-reference)

When you build projects it produces .deb packages in their parent directory, so it’s a good idea to create a directory for all your development needs, in which you’ll have subdirectories for each project, or each group of projects. This keeps things tidy and well organized in your computer so it becomes easier to search for code across different projects.

We commonly call our main development directory “Sandbox” and place it in our home folder.

```
mkdir ~/Sandbox
```

Of course, you can call your “Sandbox” whatever you want and place it anywhere you want as well.

### Install mint-dev-tools

Install the _mint-dev-tools_ package from the Linux Mint repositories.

```
apt update
apt install mint-dev-tools --install-recommends
```

It contains useful tools to help you compile and develop Linux Mint projects.
