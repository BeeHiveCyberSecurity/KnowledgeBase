# Running Kali Linux as a Virtual Machine in Windows

As time moves on Antivirus and EDR programs are working to implement new capabilities to identify hacking tools. These hacking tools are usually signatured by Antivirus programs to protect the host operating system from being infected. Many of the tools, exploits, and resources that are contained in Kali Linux have been signatured by these Antivirus products. So how does signature based detection work?

An antivirus signature is a sequence of bytes that are contained within a program. The files on your host system are scanned and the antivirus program compares them against there database that contains these signatures to see if there is a match. When a match is identified the file is quarantined and removed from the host system.

Although the antivirus program is doing its job, there are some ways that we can protect our Kali Linux Virtual Machine from being quarantined by the host Antivirus Software. This process will focus on implementing these exclusions with Windows Security:

[Setting an Exclusion Folder in Windows Security](broken-reference)

This process will work on Windows 10 and Windows 11

In Windows you can stop Windows Security from alerting you or blocking your virtual machine by adding it to the exclusion list. To do this you need to go to the following:

1. Select “Start” > “Settings” > “Update & Security” > “Windows Security” > “Virus & threat protection”.

[![](<../../../.gitbook/assets/run kali vm windows 1.png>)](<../../../.gitbook/assets/run kali vm windows 1.png>)

2. Under “Virus & threat protection settings”, select “Manage settings”, and then under “Exclusions”, select “Add or remove exclusions”.

[![](<../../../.gitbook/assets/run kali vm windows 2.png>)](<../../../.gitbook/assets/run kali vm windows 2.png>)

3. Select “Add an exclusion”. A drop down menu will appear and then you can select files, folders, file types, or process. If you select the folder exclusion will apply to all subfolders within the folder as well.

[![](<../../../.gitbook/assets/run kali vm windows 3.png>)](<../../../.gitbook/assets/run kali vm windows 3.png>)

4. Select the folder you want to use that will contain the files needed to run your Kali Linux Virtual Machine. (In this situation I want to save my Kali Linux Virtual Machine in a folder that I made on my Desktop.)

[![](<../../../.gitbook/assets/run kali vm windows 4.png>)](<../../../.gitbook/assets/run kali vm windows 4.png>)

Now that the folder is set as an exclusion, Windows Security will not scan the folder that contains your Kali Linux Virtual Machine.

[References](broken-reference)

* [https://support.microsoft.com/en-us/windows/add-an-exclusion-to-windows-security-811816c0-4dfd-af4a-47e4-c301afe13b26](https://support.microsoft.com/en-us/windows/add-an-exclusion-to-windows-security-811816c0-4dfd-af4a-47e4-c301afe13b26)
