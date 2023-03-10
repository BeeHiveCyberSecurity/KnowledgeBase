# Linode

There are two options when it comes to deploying a Kali Linux Linode instance. We will quickly cover both and then explain how to go about setting up them.

* [Kali as a Distribution](broken-reference)
* [Kali from the Marketplace](broken-reference)

Keep in mind that both these options are free to create, with the only cost being the standard running cost of the instance. Now lets set up these systems!

[![Create](https://www.kali.org/docs/cloud/linode/linode-1.png)](https://www.kali.org/docs/cloud/linode/linode-1.png)

[Kali as a Distribution](broken-reference)

By creating a Linode instance and selecting Kali as the distribution, this will create a [bare-bones Kali](https://www.kali.org/docs/installation/barebone-kali/) install, with only [kali-linux-core](https://www.kali.org/docs/general-use/metapackages/) installed. This can be useful if there is only a selected amount of tools that are going to be used, so this allows finer control over the system. Plus this in turn also helps reduce operating cost!

[Kali as a Distribution Configuration](broken-reference)

We want to first select Kali Linux in the drop down for “Image”:

[![Drop-down](https://www.kali.org/docs/cloud/linode/distribution-02.png)](https://www.kali.org/docs/cloud/linode/distribution-02.png)

From there we customize based off of personal preference. Here is an example configuration:

[![Hardware](https://www.kali.org/docs/cloud/linode/linode-2.png)](https://www.kali.org/docs/cloud/linode/linode-2.png)

One very important field is “Root Password”. What we set here will determine the password we use during SSH _(unless you also select a public key)_. Once ready we can select “Create Linode” again and then wait for provisioning to complete.

[![Configuration](https://www.kali.org/docs/cloud/linode/linode-3.png)](https://www.kali.org/docs/cloud/linode/linode-3.png)

Once complete we can use the SSH Access command to connect to our instance:

[![running](https://www.kali.org/docs/cloud/linode/linode-4.png)](https://www.kali.org/docs/cloud/linode/linode-4.png)

***

[Kali Default Tools In Linode](broken-reference)

If you change your mind later and want the traditional set of tools which you commonly find with the desktop version of Kali Linux, they are always installable with our [metapackages](https://www.kali.org/docs/general-use/metapackages/). You just need to run the following:

```
:~$ sudo apt update && sudo apt install kali-linux-default -y
[...]
:~$
```

[Kali from the Marketplace](broken-reference)

The alternative option is to run [“Deploy This App”](https://www.linode.com/marketplace/apps/kali-linux/kali-linux/) from the Linode marketplace. This will create a Linode instance and, depending on the options selected during configuration, will install a Kali Linux instance with certain [metapackages](https://www.kali.org/docs/general-use/metapackages/) installed. Keep in mind this may take some time before Linode’s scripts run and installs everything. This option is good if you may not know ahead of time what may be needed or just want to have the familiar Kali Linux environment.

[Kali from the Marketplace Configuration](broken-reference)

When selecting “Create Linode” we will want to select “Marketplace” at the top of the webpage. From here, we can see Kali Linux listed as the third option (at the time of writing):

[![Marketplace](https://www.kali.org/docs/cloud/linode/linode-5.png)](https://www.kali.org/docs/cloud/linode/linode-5.png)

After selecting Kali Linux we will scroll down and notice some configuration options specific to Kali:

[![Settings](https://www.kali.org/docs/cloud/linode/linode-6.png)](https://www.kali.org/docs/cloud/linode/linode-6.png)

As mentioned previously, these will determine what [metapackages](https://www.kali.org/docs/general-use/metapackages/) are installed as well as will setup VNC access automatically. These options should be configured according to your needs to prevent too many resources being taken up:

[![Hardware](https://www.kali.org/docs/cloud/linode/linode-7.png)](https://www.kali.org/docs/cloud/linode/linode-7.png)

From here we will have standard Linode configuration settings:

[![Configuration](https://www.kali.org/docs/cloud/linode/linode-8.png)](https://www.kali.org/docs/cloud/linode/linode-8.png)

Lastly, select “Create Linode” and wait for provisioning to complete. As stated before, please allow some time for Linode’s scripts to run. When they have, you will be able to use the SSH Access command to connect to our instance.
