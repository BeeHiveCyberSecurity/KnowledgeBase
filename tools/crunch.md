---
description: >-
  Crunch is a fast and flexible open-source tool for generating custom wordlists
  used for password cracking and security testing on various platforms.
---

# 📔 crunch

Crunch is a powerful security tool that enables users to generate custom wordlists for password cracking and other security-related purposes. This open-source software is a popular choice among cybersecurity professionals and ethical hackers alike, as it offers a wide range of customizable options and settings to suit any use case.

With Crunch, users can generate wordlists based on specific parameters, such as length, character set, and pattern, making it an invaluable tool for password auditing and penetration testing. Whether you're looking to crack a password for an individual account or an entire network, Crunch provides a quick and efficient way to generate targeted wordlists that can greatly improve your chances of success.

One of the key benefits of Crunch is its flexibility and ease of use. The software is designed to be highly customizable, with a variety of command-line options that allow users to fine-tune their wordlist generation process. Users can specify the minimum and maximum length of the words in the list, as well as the character set to use (such as numbers, letters, or special characters). Additionally, Crunch supports the use of custom character sets and patterns, making it easy to create wordlists tailored to specific needs.

Another standout feature of Crunch is its speed and efficiency. The software is highly optimized for performance, allowing users to generate wordlists quickly and efficiently. This can be especially valuable when dealing with large datasets or complex password cracking scenarios, as it can save valuable time and resources.

Crunch is also a highly versatile tool that can be used in a variety of security-related contexts. For example, it can be used to generate wordlists for brute-force attacks, dictionary attacks, and other types of password cracking scenarios. Additionally, it can be used for fuzzing, data analysis, and other security testing purposes.

In terms of compatibility, Crunch is designed to be platform-independent, meaning it can be used on a wide range of operating systems, including Linux, macOS, and Windows. The software is also open-source, meaning users have access to the source code and can modify it to suit their needs.

Overall, Crunch is a powerful and flexible security tool that is widely used in the cybersecurity community. Its ability to generate custom wordlists quickly and efficiently makes it an invaluable asset for anyone looking to improve their password cracking or security testing capabilities. Whether you're a cybersecurity professional or an ethical hacker, Crunch is a must-have tool in your arsenal.

### crunch Usage Example <a href="#crunch-usage-example" id="crunch-usage-example"></a>

Generate a dictionary file containing words with a minimum and maximum length of 6 (`6 6`) using the given characters (`0123456789abcdef`), saving the output to a file (`-0 6chars.txt`):

```
:~# crunch 6 6 0123456789abcdef -o 6chars.txt
Crunch will now generate the following amount of data: 117440512 bytes
112 MB
0 GB
0 TB
0 PB
Crunch will now generate the following number of lines: 16777216
```

***

\


### Packages and Binaries:

#### crunch <a href="#crunch" id="crunch"></a>

Crunch is a wordlist generator where you can specify a standard character set or any set of characters to be used in generating the wordlists. The wordlists are created through combination and permutation of a set of characters. You can determine the amount of characters and list size.

This program supports numbers and symbols, upper and lower case characters separately and Unicode.

**Installed size:** `83 KB`\
**How to install:** `sudo apt install crunch`

<details>

<summary>Dependencies:</summary>

* libc6

</details>

**crunch**

Generate wordlists from a character set

```
:~# crunch -h
crunch version 3.6

Crunch can create a wordlist based on criteria you specify.  The output from crunch can be sent to the screen, file, or to another program.

Usage: crunch <min> <max> [options]
where min and max are numbers

Please refer to the man page for instructions and examples on how to use crunch.
```

***

Updated on: 2022-Nov-16\


***
