# From Windows

This community-written page discusses practical differences between Windows and Ubuntu.

### Installing Programs <a href="#installing_programs" id="installing_programs"></a>

Windows software comes in .exe files, which you can download from the Internet or purchase from a store. Ubuntu software comes in _packages_, which are installed and updated through a centralized system, like a more powerful version of _Windows Update_ and _Add/Remove Programs_.

See the software installation guide for instructions on how to install new programs. Click on the Ubuntu Logo to find all your apps, programs, and shortcuts.

In the same way that Windows runs software only designed for Windows, applications must be made for Linux in order to run on Ubuntu. Most Linux software is available for free over the Internet. The following pages feature a small selection of popular applications available for free in Ubuntu:

#### Firewalls and Antivirus Software <a href="#firewalls_and_antivirus_software" id="firewalls_and_antivirus_software"></a>

Ubuntu's main firewall program is called _ufw_ ([click here to install gufw](apt:gufw)). There are currently very few Linux viruses in the wild, so Ubuntu doesn't come with antivirus software installed. See Antivirus for more information.

#### The Terminal <a href="#the_terminal" id="the_terminal"></a>

Linux includes a text-based interface like cmd.exe, called the _Terminal_. Many Linux guides ask you to run commands in the Terminal, which can be launched by typing _"Terminal"_ into the Dash. See Using the Terminal for more information.

#### Task Manager <a href="#task_manager" id="task_manager"></a>

Ubuntu's _System Monitor_ is the closest equivalent to the Task Manager in Windows.

| **In Unity**                  | You can launch the system monitor by typing _"System Monitor"_ into the Dash. |
| ----------------------------- | ----------------------------------------------------------------------------- |
| **In GNOME Classic/Fallback** | From the panel, click on _Applications>System Tools>System Monitor_           |

### Where To Put Your Files <a href="#where_to_put_your_files" id="where_to_put_your_files"></a>

Linux doesn't use drive letters, so there's no C: drive and no D: drive. You'll get used to the Linux filesystem gradually, but for now here are the most important locations:

| **/home/\<your user name>** | <p>This is your <em>home folder</em>, which is fairly similar to <em>My Documents</em> in Windows. You can access this folder by clicking <strong>Places</strong> > <strong>Home Folder</strong>.<br>Because this folder is used so often, many programs refer to it as "$HOME" or "~" ("tilde", pronounced "till-da". For example, saving a file as ~/my-file.txt is the same as saving it as /home/&#x3C;your user name>/my-file.txt</p> |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **/home**                   | <p>This folder contains everybody's home folders, and is fairly similar to <em>Documents and Settings</em> in Windows.<br>The main thing to remember is that despite the name, <strong>this is not </strong><em><strong>your</strong></em><strong> home folder</strong>. If somebody tells you to go to your home folder, they mean <em>/home/&#x3C;your user name></em>.</p>                                                              |
| **/media**                  | <p>This folder contains CD-ROMs, memory sticks, and other removable media.<br>Individual drives will also appear in the <strong>Places</strong> menu item and on your desktop.</p>                                                                                                                                                                                                                                                         |
| **/tmp**                    | This folder contains temporary files, and is cleaned out when you reboot.                                                                                                                                                                                                                                                                                                                                                                  |

#### Safely Removing Drives <a href="#safely_removing_drives" id="safely_removing_drives"></a>

When you are finished with a removable drive, right click on the drive's desktop icon and select **Unmount volume** or **Eject**, depending on what type of drive it is.

### Dual-Boot <a href="#dual-boot" id="dual-boot"></a>

When you are looking to switch to Ubuntu, one option that may make the transition a little easier is to set up a dual-boot. In a dual-boot system, a menu will appear during the boot process that lets you choose which OS to run. This means you can try out Ubuntu while also keeping your Windows installation.

#### Traditional <a href="#traditional" id="traditional"></a>

In a traditional dual-boot system system, Windows is installed alongside Ubuntu and each OS has its own partition. If Windows is already installed, this option does pose some risk. To allow each OS to have its own partition, you need to edit the partition and this can run the risk of potential data loss.

#### Wubi <a href="#wubi" id="wubi"></a>

If data loss is a concern for you, another option is to use Wubi. Wubi is a special installation that will install Ubuntu within Windows, similar to any other program. When installing Wubi, you specify how much of the hard drive to devote to Wubi. With no changes made to the partitions, the risk of data loss is removed.

### See Also <a href="#see_also" id="see_also"></a>

* The all-systems switching guide
* The [Ubuntu vs. Windows philosophy guide](../../../../.gitbook/assets/Philosophy)
* [Transferring Files and Settings](../../../../.gitbook/assets/TransferringFilesAndSettings)
* [Ext2fsd](http://sourceforge.net/projects/ext2fsd) lets you see your Linux drives from Windows [(EXT4 Support requested)](http://sourceforge.net/tracker/?func=detail\&aid=2720943\&group\_id=43775\&atid=437371)
* Configuring Ubuntu to work in a complex Windows network
* [Making Ubuntu feel more like Windows](../../../../.gitbook/assets/Configuring)
* [Russian translation](../../../../.gitbook/assets/FromWindowsRu)

***

