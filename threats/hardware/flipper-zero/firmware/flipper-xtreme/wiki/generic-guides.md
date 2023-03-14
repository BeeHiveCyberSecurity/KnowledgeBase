# Generic Guides

## Introduction

### How it started

So, I basically made a Write-Up together with taimtam?#4621 of the most Modules and a FAQ for them if me or them can think of any questions. I recommend reading this guide to learn about each module if you want to know more about the functionality etc.. We also cover things about the Xtreme Firmware, since our opinion is that it's the best firmware currently out there for the flipper, so far we did not find any Firmware as well maintained and stable as this one.

**IMPORTANT:** If you have any questions or problems which are not covered in this guide, I would still love to hear about it and help you. Please join our discord server and ping one of the staff members (or me) or just message me directly: whois.hoeless#1682 Also, if there is something wrong in my guide please report it to me or give me feedback, I only can make this guide off of my current knowledge about the Flipper. (And I can't know everything under any circumstance so if you find anything that's wrong just report it..)

Here are some **Terms** which are commonly used on the server so you know what people talk about:

* XFW: Xtreme Firmware
* FW: Firmware
* FZ: Flipper Zero
* OFW: Offical Firmware (basically the default one)
* HID: Human Interface Device
* BT: Bluetooth

## Installation

Get the latest stable version of the XFW Github Releases: https://github.com/ClaraCrazy/Flipper-Xtreme/releases

**DO NOT DOWNLOAD THE SOURCE CODE ONLY THE RELEASES!!**

Now there is two options. The easy one or the easy no brainer one.

#### **The recommended method:**

Now use an application to unzip the file you just downloaded. (If you don't know how to unzip / use 7zip look into the 7zip section)

* \-> Extract to a Folder
* \-> Copy folder into update on the Flipper via qFlipper
* \-> delete the apps folder (SD Card/apps/)
* \-> on the main menu press **Arrow Down**, navigate to the update folder via the Browser, select the folder which you copied over, select update ->(Run in App)

#### Installation FAQ:

**Does the folder which I copy over have to have a specific name?**

> A: No, you can call it whatever.. you can copy the name of the .zip file or just invent something! Just don't copy the .zip archive.

\


**While it's flashing my screen and LED starts to blink, what do I do?**

> A: We have had this happen before, it's some bug which we haven't figured out yet, but it shouldn't affect the installation so just wait it out it should go away in a few seconds

\


**ERROR: Cannot find update directory, what do I do?**

> A: First off, if you use the "install from file" option on qFlipper, don't. Delete all the contents inside the updates folder, or if the folder does not exist at all, create it. From there just follow the install method. The problem is that qFlipper ain't flippin it, so ofc things don't work.

## Bad KB

#### Preparation-Phase:

Basically acts like a HID (HID = Human Interface Device) and pretends to be a keyboard. You can write your own files using the Ducky Script Language 1.0 [read up on it here](https://web.archive.org/web/20220816200129/http://github.com/hak5darren/USB-Rubber-Ducky/wiki/Duckyscript)

But Flipper Zero's Bad USB provides you with some additional commands and features, such as the ALT+Numpad input method, SysRq command, and more.. Read up yourself if you are interested [here](https://docs.flipperzero.one/bad-usb).

**DISCLAIMER:** The website will tell you that BadUSB only supports the US-Keyboard-Layout which is not true anymore! The Bad-USB was overwritten and now you can choose your own keyboard layout!! We'll get to that in a second. One really important mention would be that this section was written before we added the BadKB app in V41 which added Bad BLE (Bluetooth Low Energy), mostly everything stays the same except you can now decide wether you want to use USB or BLE as your connection method. Here is the dedicated Bad KB section. Read this first though as the setup stays the same.

Save your Ducky Scripts (.txt) to the /SD Card/badkb or make a folder or more than one inside the badusb folder to make it more manageable. If you work with a SD Card reader just create a folder like you would do in your OS. On the qFlipper head to SD Card/badkb/ and right click an empty space, you should be able to select New Folder. You can give it a descriptive name, that's up to you. If you don't want to write all those files yourself, you can check out UberGuidoZ's Github. If you don't know him he is the man who has everything for the Flipper. I will probably mention him a few more times in this guide. Get your scripts [here](https://github.com/UberGuidoZ/Flipper/tree/main/BadUSB)

I will warn you tho, look at the files which you want to use, in some of them you need to add a pastebin or dopbox link to download malware to the PC. So just edit the .txt files. Some might be for Linux but most are for Windows. I'm sure you will find something you like :)

#### Execution:

Open the BadKB app on your flipper, navigate to a payload (commonly used name for the BadKB file to be executed) and select it. Before you select the file, check that your Flipper is not connected to the PC yet.

Once you've selected the file you can press **Arrow Left** to go into the config to select a new Keyboard Layout or the connection method. (The BT part will be covered in the BT section as I mentioned before). This explains itself. Now you will have 2 options:

1. Connect the Flipper and press start
2. Press start and connect the Flipper
3. Just does what you would think and run the script when you press start.
4. on the other hand will run your selected script as soon as the Flipper gets connected.

#### Bad-KB FAQ:

**My flipper ran my scripts a few times but now when I connect it it doesn't run anymore**

> A: I encountered the same issue but I never really searched for the reason. My best guess is that windows is pissed off because you connect and disconnect a HID device all the time but a simple PC restart should get you going again. Usually not a big problem.

\


**The script I executed broke my windows, what do I do?**

> A: Maybe don't run a file called Windows wants the D (actual script name, you find it on Uber's Github) on your windows machine. If you aren't careful with what you do we can't help you.

## BadBT / KB

V41 added a new feature called BadBLE (Bluetooth Low Energy) which is supported by the flipper natively. It also renamed the BadUSB application to BadKB (Keyboard). The USB connection mode is left unchanged, it works the same as the old BadUSB application therefore the old BadUSB section will stay with no changes. If for some reason you need the pin while connecting, it now shows on the screen when the device tries to connect to the flipper via BT.

When selected a BadUSB ( now called BadKB ) script, you can press **Left Arrow** to go into the configuration.

#### Config:

* Connection: Select your connection mode. ( Default = USB ) \[ USB ] Standard BadUSB connection mode. See BadUSB section! \[ BT ] Newly added BT ( Bluetooth ) mode. Lets you run BadUSB scripts on any device supporting HID inputs via Bluetooth Low Energy Human Interface Devices. ( For not so smart folks: basically bluetooth keyboard )
* Remember: Toggle on or off whether devices should be allowed to reconnect to your flipper without re-pairing with the flipper
* Keyboard Layout: Lets you change your keyboard layout for the keyboard layout used in your country.
* BT device name: Lets you set the device's Bluetooth name. ( What shows up when selecting devices in your bluetooth settings: Like JBL, Dime Black, AirPodsPro, HandsFree, etc.. )
* BT MAC address: Lets you set your device's Bluetooth MAC address. If you want your device to be recognizes as a new device, you will need to change its MAC address. The phone ( or whatever you want it to pair with ) will think its a new device due to changing the MAC address. This option will only be shown if the Remember Option is turned off since Remember needs you to have the same MAC address all the time.

## iButton

I actually never used iButton because here where I live because I never encountered one so far. Your flipper has [spring loaded pogo pins](https://en.wikipedia.org/wiki/Pogo\_pin) on the back to connect it to the iButton / the iButton reader. From there you can copy the iButton. Supported iButtons protocols are these: Dallas Cryfal and Metakom. Using the pogo pins you can save and emulate them, read more about the usage etc. on [here](https://docs.flipperzero.one/ibutton)

**Add Manually** lets you, you've guessed it, add those protocols manually, just use the right protocol and enter the key. From there you can save and rename the key.

#### iButton-FAQ:

**Why does my iButton not work?**

> A: 3 common problems are that your iButton could be either using an unsupported Protocol (not Dallas, Cryfal or Metakom), your key could be wrong, or the iButton which you want to read is not an access control key.

\


**I don't know the key, can I still unlock a door using iButton?**

> A: Yes, most probably you can. Head on your flipper select: Applications -> Tools -> iButton Fuzzer. Load one of those files, select your time delay using Arrow left or right and press start. For more questions maybe head to community support!

## Infrared

#### Universal Remotes:

Just Universal remotes for TVs, AUdio, Projectors, Fans, etc.. Basically bruteforces (tries out a lot of different combinations) the signal. Should work for a lot of devices, but not all of them.

#### Learn New Remote:

Point the LED of the remote at the IR receiver of the Flipper (the balck window) and just press the button which you want to capture. From there you can rename it (hold the enter button on a letter to make the letter caps). Use the + to add a new button to your saved remote. Use Edit remote to change the name etc of the remote.

#### Saved Remotes:

Let's you view the content of /SD Card/infrared (the default place to save your remotes to)

#### Infrared-FAQ:

**My universal remote doesn't work here or doesn't work there or I want to control this or that but it's not in the Universal remotes and I don't have a remote for it**

> A: Use the IRDB. It contains thousands of remotes sorted by type (AC, TV, Fan..) and then by name (Samsung, Logitech..). Here is a [link](https://github.com/logickworkshop/Flipper-IRDB) just copy the contents to /SD Card/infrared (I recommend using a SD card reader for it.)

\


**I want to write my own .ir files, how do I do that?**

> A: This: [IRDB](https://github.com/RandomDebugError/irdb) Never used it myself but if you want to write your own .ir files, you can do your own research on the usage of the formats and idk what not. You should be good using irdb though, but it's always nice to have a few contributors :)

## GPIO

#### USB-UART Bridge:

I used the USB-UART Bridge to control the FZ Wifi Dev board from my phone (you can use it from PC using PuTTY, works the same way.. select serial then enter which COM Port your flipper currently is on and set the Baud rate, see Baud rate below.. please know how to use PuTTY 😭 ). Get an App called Serial USB terminal (Apple doen't have a Serial USB connection). On that App head to settings and set the Baud rate to 115200. Next on the Flipper, select GPIO -> USB-UART Bridge now press Arrow left to get to the config. keep the USB channel on 0 (CLI), under Baudrate set 115200 aswell. Keep the rest is it was (cuz idk what it does 💀). Now you should be able to connect your phone to your flipper and use the Wifi Dev board from there. Here is a nice [tutorial by Pen Ace](https://youtu.be/nEBZ4VeTj7I?t=559) on it

#### GPIO Manual Control:

You should know how to use GPIO if you want to use it. Else I don't think there is a reason behind why you would use GPIO. I never used it so far. I guess just read the [docs](https://docs.flipperzero.one/gpio-and-modules) on it

5V on GPIO: enable/disable +5V power supply to pin 1. Look here for [additional information](https://docs.flipperzero.one/gpio-and-modules#brgPY)

#### IMPORTANT

Basically you can fry your flipper, your dev board, your pc, or all of the above, if you plug dev board into flipper and also connect dev board to pc at same time. It gets DC from both ends and it probably will end up frying something one way or another. -Willy Wonka (the real one) spittin facts 13/02/2023.

## Sub-Ghz

I know, big topic, big scary.

#### Read:

* Frequency: Ranges from 300MHz up to 928MHz, basically an Amplitude going up and down (like a wave). Higher frequencies squish these waves together, whilst lower frequencies flatten them out. You can look up common frequency bands in your country. Or look at the Frequency Analyzer section.
* Modulation: Most important are AM & FM. AM (Amplitude Modulation) increases / decreases the strength of the signal. FM (Frequency Modulation) shifts the frequency of the signal. Pagers is used to read the signals sent by pagers, HND\_1 & HND\_2 are used to read Honda keyfobs specifically.
* Hopping: Hopping is used when you don't know what frequency your remote is working on. It 'hops' between different frequencies and stops as soon as it captures a signal. Can take longer and more tries, and might even make you loose the signal..
* Bin RAW: Attempts to capture a RAW signal without background noise (clean raw)
* Sound: Play a sound on capture.
* Lock Keyboard: Used that you can't exit the reading menu by accident, for example by pressing Left Arrow to get to the config.

#### Read RAW:

Read RAW is similar to the normal read, it will just pick up any raw signal. Important would be:

* RSSI Threshold: Select a threshold to start capturing a signal when it reaches a specific strength. Else you might have long files with the content being mostly noise.

#### Saved:

* Lets you select saved .sub files, and send their signals ( emulate them ).

#### Add Manually:

* Add specific Protocols on specific frequencies, lets you enter values ( in HEX ) and save the signals to emulate them later.

#### Frequency Analyzer:

Used if you don't know what frequency a remote operates on. Simply open it, I recommend setting the RSSI (all the way / most of the way) down so you ensure you capture all signals, and view the frequency as it been captured (without any content, only informs about the frequency and its strength using the RSSI bar at the bottom to display it).

#### Radio Settings:

New feature from Unleashed which we implemented

* Modue: Lets yoy select wether you want to use the internal or external cc1101.

#### Sub-Ghz FAQ:

**What's the maximum range?**

> A: 50m. But it's more likely to be between 10-35m, dependent on the reciever's capabilities..

\


**Why can't I unlock my car with my captured signal?**

> A: Rolling codes. There is a nice video linked in the Misc Tools section under Sub-Ghz Bruteforce explaining what Rolling codes are.

\


**I copied my car key signal out of range of my car and played it on the flipper when I was back in range and it worked! :D Actually nevermind my keys don't work anymore.. why?**

> You just successfully unsynchronised your key's rolling code with your car's rolling code. Now you probably need to head to your car's manufacturer to get it fixed (which I think is expensive).

## Sub-Ghz Remote

#### Usage:

Click on the file you want to use, for example fun\_eu.txt, now you can use the Arrow Keys and the enter key to send different signals saved on your flipper, without having to navigate to each file manually.

#### Files:

The files are located in /SD Card/subghz/unirf\
Save your files in text format (.txt) inside of that folder.

**Example fun\_eu.txt:**

```
UP: /ext/subghz/Restaurant_Pagers/LRS_Pagers/BruteForceRest.sub
DOWN: /ext/subghz/Restaurant_Pagers/Retekess_Pagers/T119/Retekess_T119_Bruteforce_Extended.sub
LEFT: /ext/subghz/Vehicles/Tesla/BEST_PORT_OPENER/433.92MHz_AM650_Better_Tesla_Charge_Port_Opener.sub
RIGHT: /ext/subghz/Vehicles/Tesla/BEST_PORT_OPENER/433.92MHz_AM270_Better_Tesla_Charge_Port_Opener.sub
OK: /ext/subghz/Handicap/ook650_315substack.sub
ULABEL: BruteLRS
DLABEL: BruteT119
LLABEL: Tesla650
RLABEL: Tesla270
OKLABEL: Handicap
```

**UP, DOWN, LEFT, RIGHT, OK** indicate the buttons which you assign the files to. Make sure the path and name of the file is correct. **ULABEL, DLABEL, LLABEL, RLABEL, OKLABEL** indicate the names for those files (the names you will see in the remote menu). The prefix before the keyword **LABEL** indicate what button it is assigned to. **U = UP, D = DOWN, L = LEFT**, etc..

#### Get pre-made files:

Again, UberGuidoZ got you covered! [here's a linkie](https://github.com/UberGuidoZ/Flipper/tree/main/unirf) Note that those only work if you add the corresponding .sub files, again, he has them.. [another linkie](https://github.com/UberGuidoZ/Flipper/tree/main/Sub-GHz) Add them to the correct path!

#### Sub-Ghz Remote FAQ:

**My flipper only sends 1 signal and doesn't stop :c**

> A: The main reasons could be:

* A bug, that it freezes (unlikely).
* The .sub file you play is pretty long and just takes some time.
* For some reason you spammed the button (it will send it as many times as you press it).

## Sub-Ghz Playlist

#### Usage:

Select the file (playlist) which you want to send. Change the amount of repeats by pressing Left Arrow or Right Arrow (pressing left while repeat is set to none makes it play for infinity aka until you stop it). Then just press enter to start.

#### Files:

The files are located in /SD Card/subghz/playlist Save your files in text format (.txt) inside of that folder.

**Example CVS\_playlist:**

```
# CVS Playlist
sub: /ext/subghz/Stores/CVS/Aisle_Eight.sub
sub: /ext/subghz/Stores/CVS/Aisle_Eighteen.sub
sub: /ext/subghz/Stores/CVS/Aisle_Eleven.sub
sub: /ext/subghz/Stores/CVS/Aisle_Fifteen.sub
sub: /ext/subghz/Stores/CVS/Aisle_Five.sub
sub: /ext/subghz/Stores/CVS/Aisle_Four.sub
sub: /ext/subghz/Stores/CVS/Aisle_Fourteen.sub
sub: /ext/subghz/Stores/CVS/Aisle_Nineteen.sub
sub: /ext/subghz/Stores/CVS/Aisle_One.sub
sub: /ext/subghz/Stores/CVS/Aisle_Seven.sub
sub: /ext/subghz/Stores/CVS/Aisle_Seventeen.sub
sub: /ext/subghz/Stores/CVS/Aisle_Six.sub
sub: /ext/subghz/Stores/CVS/Aisle_Sixteen.sub
sub: /ext/subghz/Stores/CVS/Aisle_Ten.sub
...
```

Basically just add sub-files by adding: sub: /path/to/sub/file.sub It will run each sub-file in order from top to bottom, so you can make a collection like here for CVS which includes in the original files 57 sub files.

#### Get pre-made files:

You know where this is going.. Hello [Uber's Git!](https://github.com/UberGuidoZ/Flipper/tree/main/subplaylist) .. again, add the files to the correct path else your playlist won't work!

## NFC

NFC (= Near Field Communication) is pretty simple tech. It has less range ( only up to 4cm) than RFID.

#### Read:

* Reads whatever is on the NFC Card / Emulator. Will also read the UID (= Unique IDentifier) of another nfc tag.

#### Detect Reader:

* Will be covered after I did some more research on it.

#### Saved:

* Lets you emulate saved .nfc files. Just select the one you want to emulate and press Emulate

#### NFC FAQ:

**I read a MIFARE Desfire card but I can't emulate it, why?**

> A: Desfire and some other card types have encryption and therefore can't be emulated.

\


**Can I read and emulate Credit cards for contactless payment?**

> A: Read maybe, emulate fuck no. You can read some info of the Card like the expiration date etc. but nothing crucial.

\


**I worked with the government / on of the fortune 500 companies and I used the flipper to emulate a door key. I got fired.. Why?**

> A: Maybe don't unlock doors at the government using a hacking tool.. Just saying, they don't need you to be a threat to their security.

## 125 kHz RFID

#### Read:

Hold an RFID tag to the bottom of the Flipper device to read it. Compared to NFC, RFID has a higher range and less encryption (or none) due to the lower frequency. So most of the tags you will read should be readable with no issues whatsoever! Don't move the card around or remove it else it won't be able to read it fully!

#### Saved:

* Lets you select and emulate your saved RFID tags. It is as simple as that!

#### Add Manually:

* Lets you select different protocols and enter data (hex format) to make them yourself, save and emulate them.

#### Extra Actions:

* Read ASK only (Animal,FDX)
* Read PSK only (Indala)
* Clear T5577 Password

#### 125 kHz RFID FAQ:

**It won't let me read this card! Why?**

> A:

* Probably a wrong protocol, supported protocols are: EM4100, H10301 and I40134.. [check this out](https://www.proxsource.com/resources/how-to-order-prox-cards/prox-card-options/prox-card-formats/)
* There are two easy ways to find your format code. Look at the label on your last box of cards – your format code will be listed there with your card information. Look at your access control software to see which formats it supports.
* Maybe its a NFC card and not RFID, it's often hard to check.. \[ To learn more about NFC / RFID, here is a Deep Dive into the topic: [NFC AND RFID](https://www.youtube.com/watch?v=wjbSBDCMuXs) ]

## Wifi Dev Board

#### DISCLAIMER:

This is only for the Flipper Dev Board, which comes with preinstalled bullshit Blackmagic Firmware. Really not worth using so we use this one by koko :>

**Step 1 - Get the binaries:**

Get the latest flipper.bin [here](https://github.com/justcallmekoko/ESP32Marauder/releases/)

**Step 2 - Get the flasher:**

Get [this .zip file](https://github.com/UberGuidoZ/Flipper/raw/main/Wifi\_DevBoard/FZ\_Marauder\_Flasher/FZ\_Marauder\_v2.0.zip) (I hope you know by now how to use 7zip..)

I would add another releases so you can always get the latest version but it was uploaded like this at the moment. (v2.0)

If you think (or just want to check) if an update or a newer version for the flasher is available [check here](https://github.com/UberGuidoZ/Flipper/tree/main/Wifi\_DevBoard/FZ\_Marauder\_Flasher)

**Step 3 - prepare the Dev Board:**

* Hold BOOT on the Dev Board while plugging it into your PC directly via USB (USB Type C)
* Delete the esp file in the new Marauder folder and replace it with the binary which you downloaded earlier.

**Step 4 - FLASH:**

Double click flash.bat then type 1 and hit enter!

**Step 5 - observe:**

If your cmd now goes **brrrrr** everthing should be flashing. As soon as your cmd asks you to close the window you can unplug your Wifi Dev Board and you are done!

## Esp32 Marauder

Before you can use the Marauder you need to flash the marauder binaries on your Wifi Dev Board. See the Wifi Dev Board section for help on how to flash. Once you are all set we can go over how to use the ESP32 Marauder:

* Plug your Wifi Dev Board into your flipper (there is only 1 correct way, else it won't fit).
* Navigate to Applications -> GPIO -> \[ESP32] WiFi Marauder

#### Scan:

* ap: Scan all access points in range of your flipper with your Wifi Dev Board
* station: coming soon

#### SSID:

* add rand: add random SSID to your list \[ ssid -a -g ]
* add name: name a SSID and add it to your list \[ ssid -a -n ]
* remove: remove SSID from your list \[ ssid -r \<index of SSID in list (see next section)> ] (A SSID is basically the WiFi name)

#### List:

* ap: List all scanned Access Points (number in front of the Access Point is the index) \[ list -a ]
* ssid: List all added SSIDs (number in front of the SSID is the index) \[ list -s ]
* station: List all scanned Stations (number in front of the Station is the index) \[ list -c ] (once you selected any of these by 1 or more indexes \[ see next section ] you can rerun the corresponding one and behind the selected indexes should be (selected) to ensure you have selected the right one)

#### Select:

* ap: Select one or more Access Points \[ select -a \<index of Aceess Point / keyword all to select all>
* ssid: Select one or more SSIDs \[ select -s \<index of SSID / keyword all to select all>
* station: Select one or more Stations \[ select -c \<index of Station / keyword all to select all>

#### Clear List:

* ap: Clears ALL of the Access Points in your list (to get them back another scan is required) \[ clearlist -a ]
* ssid: Clears ALL of the SSIDs in your list (to get them back you need to add them again) \[ clearlist -s ]
* station: Clears ALL of the Stations in your list (to get them back another scan is required) \[ clearlist -c ]

#### Attack:

* deauth: Sends deauthentication frames to all APs in your list ( basically tells the router to disconnect everyone in its network \[ you could call it WiFi kicker or something if you wanted to] ) \[ attack -t deauth ]
* probe: Floods all access points with probe Frames, if the WiFi doesn't recognize the attack it will respond to each probe Frame, basically participating in the Attack. This will clog up the WiFi and stress the network, making using the network less effective. \[ attack -t probe ]
* rickroll: Sends Rick Roll Beacons and calls them like the Never gonna give you up lyrics! Here is a nice video on my yt demonstrating this kind of useless but fun attack: https://www.youtube.com/watch?v=dQw4w9WgXcQ \[ attack -t rickroll ] **NOTE: the more Access points you have selected, the weaker the attack will be. Doesn't apply to rickroll since it's not using the selected APs**

#### Targeted Deauth:

* station: coming soon
* manual: coming soon Beacon Spam:
* ap list: Sends Beacon frames named after the APs in your AP list. Basically "copy" the network and spam it. (Doesn't give you WiFi over that network) \[ attack -t beacon -a ]
* ssid list: Sends Beacon frames named after the SSIDs in your SSID list. Basically just send custom named Beacon frames. \[ attack -t beacon -l ]
* random: Sends Beacon frames which are randomly named. Used to overflow devices' list of available networks with invalid access points \[ attack -t beacon -r ]

#### Sniff:

* beacon: Filters captured WiFi traffic to harvest AP beacons sent from surrounding APs. Returns info on: Source MAC, Source ESSID. \[ sniffbeacon ]
* deauth: Filters captured WiFi traffic to harvest deauths and disassociations beacons sent from surrounding APs and WiFi clients against any network or client. Returns info on: Source MAC, Destination MAC. \[ sniffdeauth ]
* esp: Sniff and display WiFi frames sent by a Source MAC known to be from a manufacturer called Espressif. Typically sent from smart home IoT lights, plugs or Clara's favourite toys. \[ sniffesp ]
* pmkid: Sniffs and displays captured pmkid/eapol frames sent during WiFi authentication sessions. Unlike other sniffing functions, the raw frame data is displayed on screen to be copied and saved elsewhere. ( You need to set the channel manually, no channel hopping like the pwnagotchi does for example.. -> see next section..) \[ sniffpmkid ]
* probe: Filters captured WiFi traffic to harvest probe requests sent from surrounding clients against any network. Returns info on: Source MAC, Destination ESSID. \[ sniffprobe ]
* pwn: Sniffs beacon frames sent by the pwnagotchi. A pwnagotchi sends beacon frames to advertise its presence to other pwnagotchis which contains info about itself. I think pwnagotchis are cute.. \[ sniffpwn ]
* raw: coming soon
* bt: not sure if supported.. \[ sniffbt ]
* skim: not sure if supported.. \[ sniffskim ]

#### Sniff PMKID on channel:

select the channel on which PMKID should sniff on. Channel:

* get: get on what channel you are currently on. \[ channel ]
* set: set on what channel you want to operate. \[ channel -s \<channel\_num> ]

#### Settings:

* display: view your settings, use Arrow Down to scroll through them. \[ settings ]
* restore: creates default json file with default settings \[ settings -r ]
* ForcePMKID: forces PMKID \[ settings -s ForcePMKID \<enable/disable> ]
* ForceProbe: forces Probe \[ settings -s ForceProbe \<enable/disable> ]
* SavePCAP: Saves your PCAP \[ settings -s SavePCAP \<enable/disable> ]
* EnableLED: Enables the blinking LED on your Dev Board \[ settings -s EnableLED \<enable/disable> ] (default = OFF)
* other: lets you quickly enter settings yourself \[ settings -s ]

#### Update:

you can update using ota or a SD card, but I still recommend flashing it like shown in the Wifi Dev Board section

#### Reboot:

reboots the ESP32 Marauder

#### Help:

displays where you can get App support or write feedback to

## Misc Tools

In this section I will also mention and explain some Tools, which aren't main modules of the flipper, but are still useful to have heard of.

* \[ Applications -> Tools ]
* iButton Fuzzer: Basically a 'Bruteforce' of iButton codes. We use a different list of Values dependent on the Protocol. Default Lists: DS1990, Metakom, Cryfal. Just connect the flipper as described in the iButton section and start the fuzzer. With luck and the right protocol you might get to open a door that way!
* PicoPass Reader: coming soon
* RFID Fuzzer: Fuzz ('Bruteforce') a RFID system using the RFID Fuzzer, just select a list with values and press start. Default Lists: EM4100, HIDProx, PAC/Stanley. Custom list: H10301 (tries EVERY possible combination and can take up to 4 weeks to complete -> it's more for testing than for actually using it somewhere.) Uber again got ya covered: https://github.com/UberGuidoZ/Flipper/tree/main/RFID/H10301%20Bruteforce Unzip the file and copy it to the /SD Card/lfrfid/rfidfuzzer/
* Sub-Ghz Bruteforcer: Basically bruteforces its way through all the possible combinations of the different protocols with different amounts of bits and different frequencies. It's a huge topic actually and I might give it its own place on our modules but for now you'll find it here. The Sub-Ghz Bruteforcer is mostly used for garage doors and such things. Lets say you want to open your own garage door and you are in the EU = probably 433MHz and it might use CAME / NICE. Open the Protocol with the right frequency: you can just press start, each signal will be sent 3x to ensure it will be captured. If you found the right code and have a rough idea of at what place it is, you can hold Arrow Left or Arrow Right to skip forward and backwards. If you know the exact position of the working signal, you can just copy it manually from the file, save it and use it as a remote! Here is a nice video explaining [how bruteforcing Sub-Ghz signals actually works](https://www.youtube.com/watch?v=CNodxp9Jy4A), it's featuring a guy called samy, who reprogrammed a kid's toy to bruteforce Sub-Ghz signals: http://samy.pl/opensesame/
* CLI: 'How can I use the Sub-Ghz chat?? Where is it??', it's right here! The CLI lets you run commands like being in a serial connection with for example PuTTY or your phone. Type chat to use the Sub-Ghz chat function (nobody will probably answer anyways..) or type any other command to use it just like in putty etc.
* \[ Applications -> Misc ]
* Basically just a lot of different little things to play with. Most of them are pretty useless, you can take a look at it though, most of that stuff needs no explanation.
* \[ Applications -> GPIO ]
* So far I only used it for the ESP32 Wifi Marauder, so I might add more stuff as I get feedback and dms from people wanting to contribute. The ESP32 Wifi Marauder has its own section.

## Xtreme Firmware

With the new V40 update of the Xtreme Firmware, we got introduced to a lot of changes in the animation system, aswell as a new Application called Xtreme Settings.

You can find the Xtreme Settings by pressing the **Arrow Up** in the menu. Or by selecting the Xtreme Settings app from the main menu.

### Graphics:

**Asset Pack:**

* SFW: Change all graphics to the default flipper animations (SFW)
* NSFW: Change all graphics to Clara's NSFW animations
* WatchDogs: Change all graphics to Willy's WD animations
* Other: Other animations which you installed via our [Asset pack feature](https://github.com/ClaraCrazy/Flipper-Xtreme/wiki/Asset-Packs)

**Anim Speed:**

* Change the speed of your animations from 25% up to 300%. Default = 100%

**Cycle Anims:**

* Lets you cycle through the animations without having to hold the enter button in the menu. Options: OFF (infinity), 30S, 1M, 5M, 10M 15M, 30M, 1H, 2H, 6H, 12H, 24H and customisable in Meta.txt (uses the Meta for the current animation. to change the duration, change it in the Meta of the animation). Default = Meta.txt

**Unlock Anims:**

* Acts like an unlock all -> Unlock all animations without a lvl requirement, bypasses the mood requirement aswell. Default = OFF

### Status Bar:

**Battery Icon:**

* Customize the style of your battery. Options: OFF (disable battery), Bar, %, Inv. %, Retro3, Retro5, Bar %.

**Status Icons:**

* Lets you toggle on and off the Icons for SD and BT

**Bar Borders:**

* Lets you toggle on and off the Bar Borders

**Bar Background:**

* Lets you toggle on and off the Bar Background

### Protocols:

**BadKB Mode:**

* Lets you default between USB and BT for the Bad KB app ( you can still change the mode in the config of the the Bad KB app, this is just the defualt for when you open it. )

**BadBT Remember:**

* Toggle on or off whether devices should be allowed to reconnect to your flipper without re-pairing with the flipper

**SubGHz Frequencies:**

Allows you to add custom frequencies to Sub-GHz!

**Static Frequencies:**

* Static Freq: Shows what custom frequency is selected ( needed for the Delete button below )
* Delete Static Freq: Deletes the current selected custom frequency ( look at the Static Freq list above )
* Add Static Freq: Lets you add a custom static frequency.

**Hopper Frequencies:**

* Hopper Freq: Shows what custom frequency is selected ( needed for the Delete button below )
* Delete Hopper Freq: Deletes the current selected custom frequency ( look at the Hopper Freq list above )
* Add Hopper Freq: Lets you add a custom hopper frequency.

**SubGhz Extend:**

* Lets you set 'dangerous' frequencies. Just kidding, they say that for legal bullshit, both antenna and the chip are built to be able to operate at these frequencies. It's just that the default one's are for legal public usage.

**SubGhz Bypass:**

* Lets you bypass your country's frequency restrictions. Unlocks all 'safe' / semi legal frequencies

#### Dolphin

**XP Level:**

* Lets you set your own XP level. Lvl 1 - 30. **Lvl 30 = Max Lvl.**

**Butthurt Timer:**

* Lets you set the Butthurt time (interval) in which the flipper's mood will change due to you not actively using it. Options: OFF, 30 minutes, 1 hour, 2 hours, 4 hours, 6 hours, 8 hours, 12 hours, 24 hours, 48 hours. Default = 12 hours

#### Misc

**Sort Dirs First:**

* Forces your flipper to sort dirs before files and put the dirs above the files

**Change Device Name**

* Changes the name of your flipper

#### Experimental Options:

**Dark Mode:**

* Inverts all the colors on your flipper forcing it to make a "darkmode"

**Left Handed:**

* Flips the screen of the flipper and inverts all inputs

## Flipper Keyboard

The keyboard on the flipper is used to handle certain inputs on the flipper itself ( to give a file a name while saving or changing your flippers name, ... ) and since we have reworked some parts of the keyboard I would just go over the changes in here so people recognize the changes and don't get confused.

**Hold enter on a key:**

* Holding enter on a key will change the capitalisation to the opposite of the displayed capitalisation

**Hold backspace key:**

* Holding the backspace key finally keeps on deleting so you don't have to spam-click it

**Secondary symbol keyboard:**

* On the bottom left of the keyboard is a button to switch to a secondary keyboard with symbols.

## 7zip

Download 7zip from their [offical website](https://www.7-zip.org/). Install it. Use it. ( How is this hard?? literally just google.. )

## Expectations

What to expect from a flipper zero

When buying a flipper, don't expect to have access to the world, or be able to steal credit cards or stupid shit like that. the flipper zero is a toy with benefits, like Clara!! The flipper zero is a portable pen-testing tool, not a hacker device or real-life watchdogs. pen testing is short for penetration testing, pen-testing is used to find vulnerabilities in computer systems, this is to identify weak spots in defenses that attackers can take advantage of, most likely the reason you bought the flipper in the first place.

there are a few things that immediately made the flipper important to me. the customizability, if you know how to code then the FZ has infinite possibilities on top of that adding stuff to the GPIO makes it even more capable

if you come in with high expectations you will be severely disappointed, is it worth 170$ to turn off a projector or make an intercom at CVS go crazy? No? then don't get it.

## Keybinds

### On the main menu:

#### Short press:

* **Short select:** Opens the module menu
* **Short arrow left:** Open the clock
* **Short arrow right:** Shows the passport with lvls, etc..
* **Short arrow up:** Shows the quick accessibility menu
* **Short arrow down:** Opens the (file) Browser

#### Long press:

* **Long select:** Skips the current animation
* **Long arrow left:** Locks the flipper
* **Long arrow right:** Battery status & About info
* **Long arrow up:** Open primary favourite app
* **Long arrow down:** Open secondary favourte app
