# Adding Encrypted Persistence to a Kali Linux Live USB Drive

In this workshop, we will examine the various features available to us when booting Kali Linux from USB devices. We will explore features such as persistence, creating LUKS encrypted persistence stores, and even dabble in “LUKS Nuking” our USB drive. The default Kali Linux ISOs (from 1.0.7 onwards) support USB encrypted persistence.

**0x01 - Start by imaging the Kali ISO onto your USB drive (ours was /dev/sdb)**. Once done, you can inspect the USB partition structure using _parted /dev/sdb print_:

For ease of use, please use a root account. This can be done with “sudo su”.

```
:~$ dd if=kali-linux-2022.4-live-amd64.iso of=/dev/sdb conv=fsync bs=4M
```

**0x02 - Create and format an additional partition on the USB drive**. In our example, we create a persistent partition in the empty space above the Kali Live partitions:

```
:~$ fdisk /dev/sdb <<< $(printf "n\np\n\n\n\nw")
```

When fdisk completes, the new partition should have been created at `/dev/sdb3`; this can be verified with the command `lsblk`.

**0x03 - Encrypt the partition with LUKS:**

```
:~$ cryptsetup --verbose --verify-passphrase luksFormat /dev/sdb3
```

**0x04 - Open the encrypted partition:**

```
:~$ cryptsetup luksOpen /dev/sdb3 my_usb
```

**0x05 - Create an ext4 filesystem and label it**:

```
:~$ mkfs.ext4 -L persistence /dev/mapper/my_usb
:~$ e2label /dev/mapper/my_usb persistence
```

**0x06 - Mount the partition and create your persistence.conf so changes persist across reboots:**

```
:~$ mkdir -p /mnt/my_usb
:~$ mount /dev/mapper/my_usb /mnt/my_usb
:~$ echo "/ union" | sudo tee /mnt/my_usb/persistence.conf
:~$ umount /dev/mapper/my_usb
```

**0x07 - Close the encrypted partition:**

```
:~$ cryptsetup luksClose /dev/mapper/my_usb
```

Now your USB drive is ready to plug in and reboot into Live USB Encrypted Persistence mode.

[Multiple Persistence Stores](broken-reference)

At this point we should have the following partition structure:

```
:~$ parted /dev/sdb print
```

We can add additional persistence stores to the USB drive, both encrypted or not… and choose which persistence store we want to load, at boot time. Let’s create one more additional non-encrypted store. We’ll label and call it “work”.

**0x01 - Create an additional, 4th partition which will hold the “work” data**. We’ll give it another 5GB of space:

```
:~$ parted /dev/sdb
GNU Parted 2.3
Using /dev/sdb
Welcome to GNU Parted! Type 'help' to view a list of commands.
(parted) print
Model: SanDisk SanDisk Ultra (scsi)
Disk /dev/sdb: 31.6GB
Sector size (logical/physical): 512B/512B
Partition Table: msdos

Number  Start   End     Size    Type     File system  Flags
 1      32.8kB  2988MB  2988MB  primary               boot, hidden
 2      2988MB  3050MB  64.9MB  primary  fat16
 3      3050MB  10.0GB  6947MB  primary

(parted) mkpart primary 10000 15000
(parted) quit
Information: You may need to update /etc/fstab.
```

**0x02 - Format the fourth partition, label it “work”**:

```
:~$ mkfs.ext4 /dev/sdb4
:~$ e2label /dev/sdb4 work
```

**0x03 - Mount this new partition and create a persistence.conf in it:**

```
:~$ mkdir -p /mnt/usb
:~$ mount /dev/sdb4 /mnt/usb
:~$ echo "/ union" > /mnt/usb/persistence.conf
:~$ umount /mnt/usb
```

Boot the computer, and set it to boot from USB. When the boot menu appears, edit the persistence-label parameter to point to your preferred persistence store!

[Emergency Self Destruction of Data in Kali](broken-reference)

As penetration testers, we often need to travel with sensitive data stored on our laptops. Of course, we use full disk encryption wherever possible, including our Kali Linux machines, which tend to contain the most sensitive materials. Let’s configure a nuke password as a safety measure:

```
:~$ sudo apt install -y cryptsetup-nuke-password
:~$ dpkg-reconfigure cryptsetup-nuke-password
```

The configured nuke password will be stored in the initrd and will be usable with all encrypted partitions that you can unlock at boot time.

**Backup you LUKS keyslots and encrypt them:**

```
:~$ cryptsetup luksHeaderBackup --header-backup-file luksheader.back /dev/sdb3
:~$ openssl enc -e -aes-256-cbc -in luksheader.back -out luksheader.back.enc
```

Now boot into your encrypted store, and give the Nuke password, rather than the real decryption password. This will render any info on the encrypted store useless. Once this is done, verify that the data is indeed inacessible.

**Lets restore the data now**. We’ll decrypt our backup of the LUKS keyslots, and restore them to the encrypted partition:

```
:~$ openssl enc -d -aes-256-cbc -in luksheader.back.enc -out luksheader.back
:~$ cryptsetup luksHeaderRestore --header-backup-file luksheader.back /dev/sdb3
```

Our slots are now restored. All we have to do is simply reboot and provide our normal LUKS password and the system is back to its original state.
