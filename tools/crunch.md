---
description: >-
  Crunch is a command-line tool that generates custom wordlists based on
  specified criteria such as character sets, length, and patterns.
---

# 📔 crunch

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
