# Multi-boot

### Always install Windows first[¶](broken-reference)

Windows does not detect other operating systems and does not feature a boot menu. When you install it, it overwrites your boot sequence and your computer then boots straight into Windows.

Linux Mint (and most Linux distributions) detects other operating systems and builds a menu from which you can choose which system to boot.

For this reason, if you want to dual-boot or multi-boot with Windows, it is easier and recommended to install Windows first, before you install Linux Mint.

### Fix the boot sequence[¶](broken-reference)

If Windows overwrites your boot sequence:

1. Boot Linux Mint in `live` mode (with your USB stick or DVD).
2. Open a terminal.
3. To list your partitions, type `lsblk -f` and press Enter.



Find the partition where Linux Mint is installed. On most systems this should be the only `ext4` partition.

In the screenshot above:

* `sdb` is the USB stick (recognizable by its `iso9660` type which corresponds to an ISO image).
* `sda` is the hard drive.
* `sda4` is the partition on the `sda` hard drive, where Linux Mint is installed.

To list partition sizes, type `lsblk`:



To list partition labels, type `blkid`:



3. Mount the Linux Mint partition and reinstall the grub menu with the following commands:

```
sudo mount /dev/sda4 /mnt
sudo grub-install --root-directory=/mnt /dev/sda
```

Warning

In the commands above, replace /dev/sda4 and /dev/sda with the appropriate names for your Linux Mint partition and your hard drive device.
