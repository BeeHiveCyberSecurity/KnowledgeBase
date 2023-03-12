# Partitioning

### Dedicated /home partition[¶](broken-reference)

In Linux, the `/home` directory is used to store user data and preferences.

This directory contains one subdirectoy for each user account. Say your username is `john`, your home directory is `/home/john`, your downloads are in `/home/john/Downloads`, your documents in `/home/john/Documents`, your Firefox bookmarks somewhere in `/home/john/.mozilla` and so on…

By giving `/home` its own dedicated partition, you separate the user data from the rest of the operating system.

The advantage is that you can wipe the operating system and replace it without affecting the user data.

When installing Linux Mint:

1. Assign the `/` mount point to the partition dedicated to the operating system, and tell the installer to format it.
2. Assign the `/home` mount point to the partition dedicated to the user data, and if it contains user data already, make sure to tell the installer **not to format it**.

Warning

This is not recommended for novice users. A misstep during the installation could wipe all your data. Always make backups, make sure to select the right partitions and to carefully review formatting options.

Note

A Linux Mint operating system takes about 15GB and grows as you install additional software. If you can spare the size, give it 100GB. Keep most of your free space for the home partition. User data (downloads, videos, pictures) takes a lot more space.
