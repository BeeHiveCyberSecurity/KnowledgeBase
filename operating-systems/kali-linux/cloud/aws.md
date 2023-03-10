# AWS

As of February 2023 the following is how to set up an AWS Kali instance. AWS’s interface is constantly being updated, and in the future may not be 100% accurate. Should this be the case, please file an [issue on our GitLab](https://gitlab.com/kalilinux/documentation/kali-docs/-/issues) and follow [Amazon’s tutorials](https://aws.amazon.com/ec2/getting-started/).

[Creating our AWS instance](broken-reference)

The first thing we do is create [AWS](https://portal.aws.amazon.com/billing/signup) account. Only once we see the following screen are we able to proceed with setting up our instance.

[![](<../../../.gitbook/assets/aws 1.png>)](<../../../.gitbook/assets/aws 1.png>)

From here we want to click on “Services” in the top left, hover over “Compute,” and click “EC2” like shown:

[![](<../../../.gitbook/assets/aws 2.png>)](<../../../.gitbook/assets/aws 2.png>)

From here we will see the following screen. On this screen we want to look for “AMI Catalog” on the left side as shown:

[![](<../../../.gitbook/assets/aws 3.png>)](<../../../.gitbook/assets/aws 3.png>)

From here we will click on “AWS Marketplace AMIs”:

[![](<../../../.gitbook/assets/aws 4.png>)](<../../../.gitbook/assets/aws 4.png>)

From here we will search for “kali”:

[![](<../../../.gitbook/assets/aws 6.png>)](<../../../.gitbook/assets/aws 6.png>)

We should see the following:

[![](<../../../.gitbook/assets/aws 7.png>)](<../../../.gitbook/assets/aws 7.png>)

From here we will hit “Select” on the official Kali Linux image. We should then see the following:

[![](<../../../.gitbook/assets/aws 8.png>)](<../../../.gitbook/assets/aws 8.png>)

While here lets take note of what “Usage” says:

[![](<../../../.gitbook/assets/aws 8b.png>)](<../../../.gitbook/assets/aws 8b.png>)

Looks like we will SSH into the `kali` account! That is good to remember. We now can select “Continue”:

[![](<../../../.gitbook/assets/aws 9.png>)](<../../../.gitbook/assets/aws 9.png>)

From here we scroll down a bit and see all of our options. We have already selected what we need for our purposes:

[![](<../../../.gitbook/assets/aws 10.png>)](<../../../.gitbook/assets/aws 10.png>)

We were sure to select “Create new key pair” so we could access this instance:

[![](<../../../.gitbook/assets/aws 11.png>)](<../../../.gitbook/assets/aws 11.png>)

If we scroll down more, we will see even more options. Again, we have already selected what we need for our purposes:

[![](<../../../.gitbook/assets/aws 12.png>)](<../../../.gitbook/assets/aws 12.png>)

By default the storage selected does not use magnetic storage. This will result in some costs. We are sure to change this to “standard” to prevent extra costs.

Once complete, we will select “Launch instance” and we will be faced with the following screen:

[![](<../../../.gitbook/assets/aws 14.png>)](<../../../.gitbook/assets/aws 14.png>)

From here we will select “Connect to instance” which will take us to the “Instances” tab. We can from here see information about our instance:

[![](<../../../.gitbook/assets/aws 15.png>)](<../../../.gitbook/assets/aws 15.png>)

If we right-click we can see the option to “Connect”:

[![](https://www.kali.org/docs/cloud/aws/aws-16.png)](https://www.kali.org/docs/cloud/aws/aws-16.png)

We select this and are faced with the following screen:

[![](https://www.kali.org/docs/cloud/aws/aws-17.png)](https://www.kali.org/docs/cloud/aws/aws-17.png)

[Connecting to the AWS instance](broken-reference)

After configuring the official Kali Linux image you can connect to the instance by using the `kali` user. After connecting, a password change through `sudo passwd kali` is possible if needed.

An example of the command used to connect:

```
:~$ ssh -i "keys.pem" 
```

[After connecting](broken-reference)[Metapackages](broken-reference)

After connection a user may realize that the image is quite sparse. This is to allow for customization and reduced image size. To get the default Kali tool set we can utilize [Kali’s metapackages](https://www.kali.org/docs/general-use/metapackages/). Alternatively, we can install specific tools as they are needed. The following command will utilize the `kali-linux-headless` metapackage and get us a nice and quick setup:

```
:~$ sudo apt update && sudo apt install -y kali-linux-headless
```

[Graphical User Interface (GUI)](broken-reference)

If someone would like to use a GUI, they can do this through SSH forwarding. We have two options, the first is to use `ssh -X` to forward X11 and use GUI applications one at a time, or we can use RDP and forward the traffic over SSH. To set up RDP, we will run the [RDP with Xfce](https://www.kali.org/docs/general-use/xfce-with-rdp/) script used for WSL. After this, we can tunnel with `ssh -N -L 3390:127.0.0.1:3390` and connect using any remote desktop client to `127.0.0.1:3390`.

[NVIDIA drivers](broken-reference)

Another common utility is to use GPUs for cracking. This can be done as well through the AWS instance, however we must be careful to install the NVIDIA packages after everything is [up-to-date](https://www.kali.org/docs/general-use/updating-kali/) and the proper Linux headers are installed:

```
:~$ sudo apt update
:~$
:~$ sudo apt full-upgrade -y
:~$
:~$ sudo apt install -y linux-headers-5.7.0-kali3-cloud-amd64
:~$
:~$ sudo reboot -f
```

Reconnect to the session:

```
:~$ sudo apt install -y nvidia-driver nvidia-cuda-toolkit
:~$
:~$ sudo reboot -f
```

Reconnect again.

For more information on [NVIDIA drivers, check here](https://www.kali.org/docs/general-use/install-nvidia-drivers-on-kali-linux/).
