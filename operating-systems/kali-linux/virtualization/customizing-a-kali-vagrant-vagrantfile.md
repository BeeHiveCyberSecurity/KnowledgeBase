# Customizing a Kali Vagrant Vagrantfile

Vagrant has a great feature when getting started where you create a Vagrantfile unique to the box you are trying to install. For example, Kali has this Vagrantfile when starting up a Kali Vagrant machine:

```
:~$ cat Vagrantfile | grep -v '#'

Vagrant.configure("2") do |config|

  config.vm.box = "kalilinux/rolling"








end
```

What we see here is that Vagrant is configuring to use ‘2’ and the ‘vm.box’ is Kali. Perfect! But what does that mean? Well, ‘2’ is actually just what version of Vagrant we are running (Vagrant 1.1 and newer) and ‘vm.box’ just says that we are using Kali. So what can we do with this? Well HashiCorp actually provides some pretty nice [documentation](https://www.vagrantup.com/docs/vagrantfile) on how to configure it and discusses all of the different configuration values, so we aren’t going to go through them all. Instead we will discuss some of them that will make Kali a better experience for you.

[Vagrantfile configuration to improve Kali](broken-reference)

We will not be discussing the actual description of the configuration option, as that is better explained by HashiCorp, but we will discuss how Kali may benefit from it.

* config.vm.base\_address - Setting the default IP address may be useful for quite a lot of circumstances, however it also is just helpful to know what your IP is when setting up reverse shells.
* config.vm.hostname - Set a new hostname so you don’t have the default one!
* config.vm.provider - It may be helpful to select which VM provider you want if you have multiple. Note that this can also be done with the command flag `--provider`.
* config.vm.provision - This [option](https://www.vagrantup.com/docs/provisioning) may be helpful for people who want to configure some type of option post Vagrant start up. For example, if we want to post-startup ensure that Kali is up-to-date and we have kali-linux-large installed, we can do that pretty easily.
* config.vm.usable\_port\_range - If we want to use a larger port range then this is a must know.
* config.ssh.forward\_x11 - This option may be helpful if you are wanting GUI access for a certain app.
