---
description: >-
  libnfc is a library for Near Field Communication. It abstracts the low-level
  details of communicating with the devices away behind an easy-to-use
  high-level API.
---

# 🔏 libnfc

Libnfc is a free and open-source software library that provides a convenient and secure way to communicate with Near Field Communication (NFC) devices. NFC technology is widely used in various applications such as contactless payment systems, access control systems, public transportation, and electronic ticketing. Libnfc enables developers to easily build applications that interact with NFC devices without needing to understand the low-level details of NFC protocol.

Libnfc is designed to work with various NFC readers and tags, including ISO/IEC 14443 Type A/B, MIFARE, FeliCa, and NFC Forum Type 2 and 4 tags. The library supports a wide range of platforms, including Linux, Windows, and macOS, and is written in the C programming language.

One of the key features of libnfc is its support for secure communication with NFC devices. The library includes support for several cryptographic protocols, including DES, 3DES, and AES, which can be used to encrypt and decrypt data exchanged with NFC devices. This ensures that sensitive data, such as credit card numbers and personal identification information, remains secure and confidential.

In addition to security features, libnfc also provides developers with a simple and easy-to-use API for working with NFC devices. The library includes functions for reading and writing data to NFC tags, as well as for performing other common tasks such as authentication and key management.

Libnfc is also highly customizable, allowing developers to configure the library to work with specific NFC readers and tags. This enables developers to optimize their applications for specific use cases and to ensure that they work seamlessly with the NFC devices they are targeting.

One potential limitation of libnfc is that it requires a certain level of technical expertise to use effectively. Developers need to have a good understanding of the NFC protocol and cryptography to make the most of the library's features. However, there is a large and active community of developers who use and contribute to libnfc, so there are many resources available for those who need help.

Overall, libnfc is an excellent tool for developers who need to work with NFC devices. Its support for secure communication, customizable features, and easy-to-use API make it a powerful and flexible tool for building applications that interact with NFC devices.

#### libnfc-bin <a href="#libnfc-bin" id="libnfc-bin"></a>

Supports most hardware based on the NXP PN531, PN532 or PN533 controller chips.

This package contains some utils that come along with libnfc, for development or debugging purposes (including nfc-list, nfc-mfclassic, nfc-mfultralight, etc).

**Installed size:** `206 KB`\
**How to install:** `sudo apt install libnfc-bin`

<details>

<summary>Dependencies:</summary>

* libc6
* libnfc6

</details>

**nfc-barcode**

NFC Barcode (Tag-Talks-First) reader

```
:~# nfc-barcode -h
Usage: nfc-barcode [OPTIONS]
Options:
	-h	Help. Print this message.
	-q	Verbose mode.
```

***

**nfc-emulate-forum-tag4**

NFC Forum tag type 4 emulation command line demonstration tool

```
:~# nfc-emulate-forum-tag4 -h
usage: nfc-emulate-forum-tag4 [-1] [infile [outfile]]
      -1: force Tag Type 4 v1.0 (default is v2.0)
```

***

**nfc-jewel**

Jewel command line tool

```
:~# man nfc-jewel
nfc-jewel(1)                     NFC Utilities                    nfc-jewel(1)

NAME
       nfc-jewel - Jewel command line tool

SYNOPSIS
       nfc-jewel r|w DUMP

DESCRIPTION
       nfc-jewel  is  a Jewel tool that allows one to read or write a tag data
       to/from a DUMP file.

       Jewel tag by Broadcom, previously Innovision, uses a binary  Dump  file
       to store data for all sectors.

       Be  cautious that some parts of a Jewel memory can be written only once
       and some parts are used as lock bits, so please read the tag documenta-
       tion before experimenting too much!

OPTIONS
       r | w Perform read from ( r ) or write to ( w ) card.

       DUMP   JeWel Dump (JWD) used to write (card to JWD) or (JWD to card)

BUGS
       Please report any bugs on the libnfc issue tracker at:
       https://github.com/nfc-tools/libnfc/issues

LICENCE
       libnfc  is licensed under the GNU Lesser General Public License (LGPL),
       version 3.
       libnfc-utils and libnfc-examples are covered by the  the  BSD  2-Clause
       license.

AUTHORS
       Roel Verdult <>,
       Romuald Conty <>.

       This manual page was written by Romuald Conty <>.  It
       is licensed under the terms of the GNU GPL (version 2 or later).

libnfc                           Feb 02, 2014                     nfc-jewel(1)
```

***

**nfc-list**

List NFC targets

```
:~# nfc-list -h
nfc-list uses libnfc 1.8.0
usage: nfc-list [-v] [-t X]
  -v	 verbose display
  -t X	 poll only for types according to bitfield X:
	   1: ISO14443A
	   2: Felica (212 kbps)
	   4: Felica (424 kbps)
	   8: ISO14443B
	  16: ISO14443B'
	  32: ISO14443B-2 ST SRx
	  64: ISO14443B-2 ASK CTx
	 128: ISO14443B iClass
	 256: ISO14443A-3 Jewel
	 512: ISO14443A-2 NFC Barcode
	So 1023 (default) polls for all types.
	Note that if 16, 32, 64 or 128 then 8 is selected too.
```

***

**nfc-mfclassic**

MIFARE Classic command line tool

```
:~# nfc-mfclassic -h
Usage: nfc-mfclassic f|r|R|w|W a|b u|U<01ab23cd> <dump.mfd> [<keys.mfd> [f]]
  f|r|R|w|W     - Perform format (f) or read from (r) or unlocked read from (R) or write to (w) or unlocked write to (W) card
                  *** format will reset all keys to FFFFFFFFFFFF and all data to 00 and all ACLs to default
                  *** unlocked read does not require authentication and will reveal A and B keys
                  *** note that unlocked write will attempt to overwrite block 0 including UID
                  *** unlocking only works with special Mifare 1K cards (Chinese clones)
  a|A|b|B       - Use A or B keys for action; Halt on errors (a|b) or tolerate errors (A|B)
  u|U           - Use any (u) uid or supply a uid specifically as U01ab23cd.
  <dump.mfd>    - MiFare Dump (MFD) used to write (card to MFD) or (MFD to card)
  <keys.mfd>    - MiFare Dump (MFD) that contain the keys (optional)
  f             - Force using the keyfile even if UID does not match (optional)
Examples: 

  Read card to file, using key A:

    nfc-mfclassic r a u mycard.mfd

  Write file to blank card, using key A:

    nfc-mfclassic w a u mycard.mfd

  Write new data and/or keys to previously written card, using key A:

    nfc-mfclassic w a u newdata.mfd mycard.mfd

  Format/wipe card (note two passes required to ensure writes for all ACL cases):

    nfc-mfclassic f A u dummy.mfd keyfile.mfd f
    nfc-mfclassic f B u dummy.mfd keyfile.mfd f

  Read card to file, using key A and uid 0x01 0xab 0x23 0xcd:

    nfc-mfclassic r a U01ab23cd mycard.mfd

```

***

**nfc-mfultralight**

MIFARE Ultralight command line tool

```
:~# nfc-mfultralight -h
Usage: nfc-mfultralight r|w <dump.mfd> [OPTIONS]
Arguments:
	r|w                 - Perform read or write
	<dump.mfd>          - MiFare Dump (MFD) used to write (card to MFD) or (MFD to card)
Options:
	--otp               - Don't prompt for OTP Bytes writing (Assume yes)
	--lock              - Don't prompt for Lock Bytes (OTP) writing (Assume yes)
	--dynlock           - Don't prompt for Dynamic Lock Bytes writing (Assume yes)
	--uid               - Don't prompt for UID writing (Assume yes)
	--full              - Assume full card write (UID + OTP + Lockbytes + Dynamic Lockbytes)
	--with-uid <UID>    - Specify UID to read/write from
	--pw <PWD>          - Specify 8 HEX digit PASSWORD for EV1
	--partial           - Allow source data size to be other than tag capacity
```

***

**nfc-read-forum-tag3**

Extract NDEF Message from a NFC Forum Tag Type 3

```
:~# nfc-read-forum-tag3 -h
usage: nfc-read-forum-tag3 [-q] -o FILE

Options:
  -o FILE    Extract NDEF message if available in FILE
  -o -       Extract NDEF message if available to stdout
  -q         Be quiet, don't display Attribute Block parsing info
```

***

**nfc-relay-picc**

Relay demonstration tool for ISO14443-4

```
:~# nfc-relay-picc -h
Usage: nfc-relay-picc [OPTIONS]
Options:
	-h	Help. Print this message.
	-q	Quiet mode. Suppress printing of relayed data (improves timing).
	-t	Target mode only (the one on reader side). Data expected from FD3 to FD4.
	-i	Initiator mode only (the one on tag side). Data expected from FD3 to FD4.
	-s	Swap roles of found devices.
	-n N	Adds a waiting time of N seconds (integer) in the relay to mimic long distance.
```

***

**nfc-scan-device**

Scan NFC devices

```
:~# nfc-scan-device -h
Usage: nfc-scan-device [OPTIONS]
Options:
	-h	Print this help message.
	-v	Set verbose display.
	-i	Allow intrusive scan.
```

***

#### libnfc-dev <a href="#libnfc-dev" id="libnfc-dev"></a>

libnfc is a library for Near Field Communication. It abstracts the low-level details of communicating with the devices away behind an easy-to-use high-level API. It supports most hardware based on the NXP PN531, PN532 or PN533 controller chips.

This package contains the header and development files needed to build programs and packages using libnfc.

**Installed size:** `361 KB`\
**How to install:** `sudo apt install libnfc-dev`

<details>

<summary>Dependencies:</summary>

* libnfc6
* libusb-dev

</details>

***

#### libnfc-examples <a href="#libnfc-examples" id="libnfc-examples"></a>

libnfc is a library for Near Field Communication. It abstracts the low-level details of communicating with the devices away behind an easy-to-use high-level API. It supports most hardware based on the NXP PN531, PN532 or PN533 controller chips.

Some examples are provided with libnfc for debugging and/or educational purposes (nfc-anticol, nfc-emulate, etc.).

**Installed size:** `184 KB`\
**How to install:** `sudo apt install libnfc-examples`

<details>

<summary>Dependencies:</summary>

* libc6
* libnfc6

</details>

**nfc-anticol**

Demonstration of NFC anti-collision command line tool based on libnfc

```
:~# nfc-anticol -h
Usage: nfc-anticol [OPTIONS]
Options:
	-h	Help. Print this message.
	-q	Quiet mode. Suppress output of READER and EMULATOR data (improves timing).
	-f	Force RATS.
	-t	Measure response time (in cycles).
```

***

**nfc-dep-initiator**

Demonstration tool to send/received data as D.E.P. initiator

```
:~# nfc-dep-initiator -h
Usage: nfc-dep-initiator
```

***

**nfc-dep-target**

Demonstration tool to send/received data as D.E.P. target

```
:~# nfc-dep-target -h
Usage: nfc-dep-target
```

***

**nfc-emulate-forum-tag2**

NFC Forum tag type 2 emulation command line demonstration tool

```
:~# man nfc-emulate-forum-tag2
NFC-EMULATE-FORUM-TAG2(1)   User's Reference Manual  NFC-EMULATE-FORUM-TAG2(1)

NAME
     nfc-emulate-forum-tag2 -- NFC Forum tag type 2 emulation command line
     demonstration tool

SYNOPSIS
     nfc-emulate-forum-tag2

DESCRIPTION
     nfc-emulate-forum-tag2 is a demonstration tool that emulates a NFC-Forum
     Tag Type 2 with NDEF content.

     Some devices compliant with NFC-Forum Tag Type 2 can be used with this
     example, in read mode only.

IMPORTANT
     This example has been developed using PN533 USB hardware as target and
     Google Nexus S phone as initiator.

     This is know to NOT work with Nokia 6212 Classic and could fail with sev-
     eral NFC Forum compliant devices due to the following reasons:

     - The emulated target has only a 4-byte UID while most devices assume a
     Tag Type 2 has always a 7-byte UID (as a real Mifare Ultralight tag);

     - The chip is emulating an ISO/IEC 14443-3 tag, without any hardware
     helper.  If the initiator have too strict timeouts for software-based em-
     ulation (which is usually the case), this example will fail.  This is not
     a bug and we can't do anything using this hardware (PN531/PN533).

     ACR122 devices (like touchatag, etc.) can be used by this example, but if
     something goes wrong, you will have to unplug/replug your device.  This
     is not a libnfc's bug, this problem is due to ACR122's internal MCU in
     front of NFC chip (PN532).

BUGS
     Please report any bugs on the libnfc issue tracker at:
     https://github.com/nfc-tools/libnfc/issues

LICENCE
     libnfc is licensed under the GNU Lesser General Public License (LGPL),
     version 3.  libnfc-utils and libnfc-examples are covered by the BSD
     2-Clause license.

AUTHORS
     Roel Verdult <>
     Romain Tartiere <>
     Romuald Conty <>

     This manual page was written by Romuald Conty.  It is licensed under the
     terms of the GNU GPL (version 2 or later).

                              September 19, 2012
```

***

**nfc-emulate-tag**

Simple tag emulation command line demonstration tool

```
:~# man nfc-emulate-tag
nfc-emulate-tag(1)             libnfc's examples            nfc-emulate-tag(1)

NAME
       nfc-emulate-tag - Simple tag emulation command line demonstration tool

SYNOPSIS
       nfc-emulate-tag

DESCRIPTION
       nfc-emulate-tag  is  a  simple tag emulation tool that demonstrates how
       emulation can be done using libnfc.

       Currently, this tool partially emulates a Mifare Mini: it  is  detected
       as Mifare Mini but internal MIFARE proprietary commands are not yet im-
       plemented.

       To be able to emulate a target, there are two main parts:
        - communication: handle modulation, anticollision, etc.
        - computation: process commands (input) and produce results (output).

       This demonstration tool proposes a logical structure to handle communi-
       cation and a simple function to deal with computation.

       To  improve  the target capabilities, we can now implement more allowed
       commands in a single function: target_io()

       Please note that, due to timing issues, it is very difficult to  imple-
       ment  an  ISO14443-4 tag this way: RATS request expects a quick ATS an-
       swer. By the way, even if you implement another kind of tag, timing is-
       sues  are  often the source of problems like CRC or parity errors.  The
       OmniKey CardMan 5321 is known to be very large on timings and is a good
       choice  if  you  want  to experiment with this emulator with a tolerant
       reader.

IMPORTANT
       ACR122 devices (like touchatag, etc.) can be used by this example (with
       probably  timing  issue), but if something goes wrong, you will have to
       unplug/replug your device. This is not a libnfc's bug, this problem  is
       due to ACR122's internal MCU in front of NFC chip (PN532).

BUGS
       Please report any bugs on the libnfc issue tracker at:
       https://github.com/nfc-tools/libnfc/issues

LICENCE
       libnfc  is licensed under the GNU Lesser General Public License (LGPL),
       version 3.
       libnfc-utils and libnfc-examples are covered by the  the  BSD  2-Clause
       license.

AUTHORS
       Romuald Conty <>

       This manual page was written by Romuald Conty <>.  It
       is licensed under the terms of the GNU GPL (version 2 or later).

libnfc                          October 8, 2010             nfc-emulate-tag(1)
```

***

**nfc-emulate-uid**

NFC target emulation command line tool based on libnfc

```
:~# nfc-emulate-uid -h
Usage: nfc-emulate-uid [OPTIONS] [UID]
Options:
	-h	Help. Print this message.
	-q	Quiet mode. Silent output: received and sent frames will not be shown (improves timing).

	[UID]	UID to emulate, specified as 8 HEX digits (default is DEADBEEF).
```

***

**nfc-mfsetuid**

MIFARE 1K special card UID setting and recovery tool

```
:~# nfc-mfsetuid -h
Usage: nfc-mfsetuid [OPTIONS] [UID|BLOCK0]
Options:
	-h	Help. Print this message.
	-f	Format. Delete all data (set to 0xFF) and reset ACLs to default.
	-q	Quiet mode. Suppress output of READER and CARD data (improves timing).

	Specify UID (4 HEX bytes) to set UID, or leave blank for default '01234567'.

	Specify BLOCK0 (16 HEX bytes) to set content of Block0. CRC (Byte 4) is recalculated an overwritten'.
	This utility can be used to recover cards that have been damaged by writing bad
	data (e.g. wrong BCC), thus making them non-selectable by most tools/readers.

	*** Note: this utility only works with special Mifare 1K cards (Chinese clones).

```

***

**nfc-poll**

Poll first available NFC target

```
:~# nfc-poll -h
nfc-poll uses libnfc 1.8.0
usage: nfc-poll [-v]
  -v	 verbose display
```

***

**nfc-relay**

Relay attack command line tool based on libnfc

```
:~# nfc-relay -h
Usage: nfc-relay [OPTIONS]
Options:
	-h	Help. Print this message.
	-q	Quiet mode. Suppress output of READER and EMULATOR data (improves timing).
```

***

#### libnfc-pn53x-examples <a href="#libnfc-pn53x-examples" id="libnfc-pn53x-examples"></a>

libnfc is a library for Near Field Communication. It abstracts the low-level details of communicating with the devices away behind an easy-to-use high-level API. It supports most hardware based on the NXP PN531, PN532 or PN533 controller chips.

Some PN53x-only examples are provided with libnfc for debugging and/or educational purposes (pn53x-sam, pn53x-tamashell, etc.).

**Installed size:** `84 KB`\
**How to install:** `sudo apt install libnfc-pn53x-examples`

<details>

<summary>Dependencies:</summary>

* libc6
* libnfc6

</details>

**pn53x-diagnose**

PN53x diagnose tool

```
:~# pn53x-diagnose -h
Usage: pn53x-diagnose
```

***

**pn53x-sam**

PN53x SAM communication demonstration tool

```
:~# man pn53x-sam
pn53x-sam(1)                   libnfc's examples                  pn53x-sam(1)

NAME
       pn53x-sam - PN53x SAM communication demonstration tool

SYNOPSIS
       pn53x-sam

DESCRIPTION
       pn53x-sam  is  a utility attempt to test a simple connection with a SAM
       (Secure Access Module) in several modes.

       To run this utility you must have a SAM (like the NXP's  P5CN072  chip)
       successfully connected to your PN53x chip.

       Warning: the SAM inside a Touchatag/ACR122U  is not hooked to the PN532
       but to the intermediate controller  so  pn53x-sam  won't  work  with  a
       Touchatag/ACR122U.

BUGS
       Please report any bugs on the libnfc issue tracker at:
       https://github.com/nfc-tools/libnfc/issues

LICENCE
       libnfc  is licensed under the GNU Lesser General Public License (LGPL),
       version 3.
       libnfc-utils and libnfc-examples are covered by the  the  BSD  2-Clause
       license.

AUTHORS
       Emanuele Bertoldi <>

       This     manual    page    was    written    by    Emanuele    Bertoldi
       <>.  It is licensed under the terms  of  the
       GNU GPL (version 2 or later).

libnfc                           June 15, 2010                    pn53x-sam(1)
```

***

**pn53x-tamashell**

PN53x TAMA communication demonstration shell

```
:~# man pn53x-tamashell
pn53x-tamashell(1)          General Commands Manual         pn53x-tamashell(1)

NAME
       pn53x-tamashell - PN53x TAMA communication demonstration shell

SYNOPSIS
       pn53x-tamashell [script]

DESCRIPTION
       pn53x-tamashell  is  a  simple  interactive tool to send so called TAMA
       commands and receive the answers.  TAMA refers to the command set  sup-
       ported  by the PN53x family.  Messages are binary and the shell expects
       hexadecimal   notation.    TAMA   commands   and   responses   prefixes
       (0xD4/0xD5), CRC and any framing above are handled transparently.

       You  can use the shell interactively (with readline support) or you can
       write your own script file consisting in commands  and  comments  (any-
       thing  that  starts with ";", "#" or "//").  Spaces are ignored and can
       be used for readability.

       Shebang is supported, simply start your script with:
        #!/usr/bin/env pn53x-tamashell

COMMANDS
       p N to introduce a pause of N milliseconds.

       q or Ctrl-d to quit.

EXAMPLES
       GetFirmware command is D4 02, so one has just to send the command "02":

        $ pn53x-tamashell
        Connected to NFC reader: SCM Micro/SCL3711-NFC&RW - PN533 v2.7 (0x07)
        > 02
        Tx: 02
        Rx: 33  02  07  07
        > 40
        Tx: 40
        Rx: Command Not Acceptable
        > q
        Bye!

       Same thing, with a script:

        $ pn53x-tamashell << EOF
        // This is a comment
        02 // GetFirmware
        40 // Command with missing arguments
        EOF

        Connected to NFC reader: SCM Micro/SCL3711-NFC&RW - PN533 v2.7 (0x07)
        > // This is a comment
        > 02 // GetFirmware
        Tx: 02
        Rx: 33  02  07  07
        > 40 // Command with missing arguments
        Tx: 40
        Rx: Command Not Acceptable
        > Bye!

OPTIONS
       script Script file with tama commands

BUGS
       Please report any bugs on the libnfc issue tracker at:
       https://github.com/nfc-tools/libnfc/issues

LICENCE
       libnfc is licensed under the GNU Lesser General Public License  (LGPL),
       version 3.
       libnfc-utils  and  libnfc-examples  are covered by the the BSD 2-Clause
       license.

       This manual page is licensed under the terms of the GNU GPL (version  2
       or later).

                              September 15, 2010            pn53x-tamashell(1)
```

***

#### libnfc6 <a href="#libnfc6" id="libnfc6"></a>

libnfc is a library for Near Field Communication. It abstracts the low-level details of communicating with the devices away behind an easy-to-use high-level API. It supports most hardware based on the NXP PN531, PN532 or PN533 controller chips.

This package contains the runtime library files needed to run software using libnfc.

**Installed size:** `201 KB`\
**How to install:** `sudo apt install libnfc6`

<details>

<summary>Dependencies:</summary>

* libc6
* libusb-0.1-4

</details>

***
