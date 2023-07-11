---
description: >-
  Flipper Zero is a hacker's multitool device that can interact with various
  wireless protocols, debug circuits, emulate cards, and more.
---

# 🐬 Flipper Zero

Flipper Zero is a portable multi-tool for pentesters and geeks in a toy-like body. It loves hacking digital stuff, such as radio protocols, access control systems, hardware and more. It's fully open-source and customizable, so you can extend it in whatever way you like.

### Multi-tool Device for Geeks

<div align="left">

<img src="https://static.tildacdn.com/tild3663-6632-4639-b161-323265356566/back.png" alt="Flipper Zero in hand">

</div>

The idea of Flipper Zero is to combine all the hardware tools you'd need for exploration and development on the go. Flipper was inspired by pwnagotchi project, but unlike other DIY boards, Flipper is designed with the convenience of everyday usage in mind — it has a robust case, handy buttons, and shape, so there are no dirty PCBs or scratchy pins. Flipper turns your projects into a game, reminding you that development should always be fun.

Flipper Zero is a tiny piece of hardware with a curious personality of a cyber-dolphin. It can interact with digital systems in real life and grow while you use it. Explore any kind of access control system, RFID, radio protocols, and debug hardware using GPIO pins.

![Flipper Zero top side GPIO pins](https://static.tildacdn.com/tild3562-6637-4332-b564-663465326132/gpio.jpg)

![Flipper Zero back side USB Type-C port](https://static.tildacdn.com/tild3565-3361-4331-a665-646466663434/usb.jpg)

![Flipper Zero specification](https://static.tildacdn.com/tild3130-3536-4036-b633-343837383536/front.jpg)

* 1.4" monochrome LCD display
* 128x64px ultra-low power, Sunlight-readable display
* 5-Button directional pad for menu navigation

Flipper Zero is completely autonomous and can be controlled from a 5-Position directional pad without additional devices, such as computers or smartphones. Common scripts and functions are available from the menu.

For more control, you can connect to Flipper via USB. Instead of a TFT/IPS/OLED, we decided to build in a cool old-school LCD screen, which is perfectly visible in sunlight and has an ultra-low power consumption of 400nA with the backlight turned off.

### GPIO pins

\
3.3V logic level\
(5V tolerant)

USB Type-C\
Power and battery charging\
Firmware update

This is the operating range for a wide class of wireless devices and access control systems, such as garage door remotes, boom barriers, IoT sensors and remote keyless systems.

Flipper has an integrated 433MHz antenna, and a CC1101 chip, which makes it a powerful transceiver capable of **up to 50 meters range**.

CC1101 is a universal transceiver designed for very low-power wireless applications. It supports various types of digital modulations such as 2-FSK, 4-FSK, GFSK and MSK, as well as OOK and flexible ASK shaping. You can perform any digital communication in your applications such as connecting to IoT devices and access control systems.

Oh, and one more thing — Flipper uses 433 MHz to communicate with other Flippers out there, so you can make some cyber-dolphin friends :)

![Flipper Zero CC1101 radio chipset](https://static.tildacdn.com/tild6438-6261-4336-b330-656665336164/fpr\_web\_antenna.jpg)

### Low-frequency proximity cards

This type of card is widely used in old access control systems around the world. It's pretty dumb, stores only an N-byte ID and has no authentication mechanism, allowing it to be read, cloned and emulated by anyone. A 125 kHz antenna is located on the bottom of Flipper — it can read EM-4100 and HID Prox cards, save them to memory to emulate later.

You can also emulate cards by entering their IDs manually.\
Moreover, Flipper owners can exchange card IDs remotely.

![Flipper Zero EM4100 emulator](https://static.tildacdn.com/tild6564-3865-4939-b862-316566633931/noroot.png)

![Flipper Zero 125 khz proximity card reader and emulator](https://static.tildacdn.com/tild3232-3735-4866-a536-373437626133/card-reading.png)

### High-frequency proximity cards

Flipper Zero has a built-in NFC module (13.56 MHz). Along with the 125kHz module, it turns Flipper into an ultimate RFID device operating in both Low Frequency (LF) and High Frequency (HF) ranges. The NFC module supports all the major standards.

It works pretty much the same as the 125 kHz module, allowing you to interact with NFC-enabled devices — read, write and emulate HF tags.

![Flipper Zero 125 khz proximity card reader and emulator](https://static.tildacdn.com/tild3264-6439-4635-a537-663534626139/nfc.png)

Flipper Zero has a built-in Bluetooth Low Energy module. As with other Flipper wireless features, we will be providing an open source library for adding Flipper support to community-made apps.

Full BLE support allows Flipper Zero to act as both a host and a peripheral device, allowing you to connect your Flipper to 3rd-party devices and a smartphone simultaneously.

Our mobile developers are designing official iOS and Android apps to let you unleash Flipper's potential with a larger screen and greater control.

![Flipper Zero 125 khz proximity card reader and emulator](https://static.tildacdn.com/tild6436-3763-4138-b864-633630356535/ble.png)

The infrared transmitter can transmit signals to control electronics such as TVs, air conditioners, stereo systems and more.

Flipper has a built-in library of common TV vendor command sequences for power and volume control. This library is constantly updated by Flipper community users uploading new signals to Flipper’s IR Remote database.

Flipper Zero also has an IR receiver that can receive signals and save them to the library, so you can store any of your existing remotes to transmit commands later, and upload to the public IR Remote database to share with other Flipper users.

### Infrared learning feature

![Flipper Zero bad usb attack toolkit](https://static.tildacdn.com/tild3139-3163-4538-b437-643239623131/fpr\_web\_1.jpg)

There is lots of heavy data Flipper has to store: remotes codes, signal databases, dictionaries, image assets, logs and more. All this data can be stored on an SD card, as well as user plugins.

The SD slot will have a push-push type connector, so the card will be reliably secured inside and won't stick out.\
Flipper Zero will support any FAT32 formatted microSD card to store your assets so you’ll never have to worry the memory will run out. The card is not required for Flipper Zero to operate and is not included.

External storage for apps and data

Tool for Hardware Exploration

![Flipper Zero — Tool for Hardware Hacking](https://static.tildacdn.com/tild6366-3339-4664-a366-656137633963/oscilloscope.jpg)

Flipper Zero is a versatile tool for hardware exploration, firmware flashing, debugging, and fuzzing. It can be connected to any piece of hardware using GPIO to control it with buttons, run your own code and print debug messages to the LCD display. It can also be used as a regular USB to UART/SPI/I2C/etc adapter.

**SPI/UART/I2C to USB converter**\


Communicate with any hardware from your desktop application.

Flash any kind of SPI memory, such as EEPROM.

Test any protocols and signals.

Built-in 5V and 3.3V power pins. Control from built-in buttons and display, no PC required.

Flipper Zero has a built-in 1-Wire connector to read iButton (aka DS1990A, Touch Memory or Dallas key) contact keys. This old technology is still widely used around the world. It uses the 1-Wire protocol that doesn't have any authentication. Flipper can easily read these keys, store IDs to the memory, write IDs to blank keys and emulate the key itself.

Flipper Zero has a unique contact pad design on the corner — its shape works as a reader and a probe to connect to iButton sockets at the same time. This mode is also handy for silently intercepting the 1-Wire data line.

![Flipper Zero ibutton 1-wire reader](https://static.tildacdn.com/tild6361-6631-4664-b139-306331336132/fpr-001\_light\_web\_bo.png)

![Flipper Zero iButton emulator](https://static.tildacdn.com/tild3234-3739-4433-b735-353564373761/P1020756.jpg)

1-Wire keys (Touch Memory)

![Flipper Zero technical specification and scheme](https://static.tildacdn.com/tild3634-6361-4032-b033-383966383966/explosion-singed-200.png)

![Flipper Zero technical specification and scheme](https://static.tildacdn.com/tild3563-3861-4230-a461-346433366163/explosion-singed-200.png)

## MCU (Microcontroller unit)

Model: STM32WB55RG\
ARM Cortex-M4 32-bit 64 MHz (application processor)\
ARM Cortex-M0+ 32 MHz (network processor)\
Flash: 1024 KB\
SRAM: 256 KB

LCD Monochrome\
Resolution: 128x64 px\
Controller: ST7565R\
Interface: SPI\
Diagonal Size: 1.4“

Chip: TI CC1101\
TX Power: 0 dBm max\
**Frequency bands (depends on your region):**\
● 315 MHz\
● 433 MHz\
● 868 MHz\
● 915 MHz

Frequency: 100-2500 Hz\
Sound Output: 87 dB\
Type: Coin

LiPo 2000 mA⋅h\
7 days approximately

Size: 100 x 40 x 25 mm\
Weight: 102 grams\
Body materials: PC, ABS, PMMA\
Operating temperature: 0 \~ 40 °C

3.3 CMOS Level\
Input 5V tolerant\
Up to 20 mA per digital pin

TX Power: 0 dBm max\
RX Sensitivity: -96 dBm\
Data rate: 2 Mbps

TX/RX range: 800-950 nm\
TX power: 300 mW

Frequency: 13.56 MHz\
**Supported cards:**\
● ISO-14443A/B\
● NXP Mifare® Classic®, Ultralight®, DESFire® etc.\
● FeliCa™\
● NFC Forum protocols

Frequency: 125 kHz\
Modulation: AM, PSK, FSK\
**Supported cards:**\
● EM400x, EM410x, EM420x\
● HIDProx, Indala

Force value: 30 N\
Speed: 13500 rpm

Up to 64GB MicroSDHC\
Read/Write speed: up to 5 Mbit/s

5-button joystick\
Back button\
Reboot — Back+Left buttons for 2 seconds

1x USB 2.0 port, type C\
USB device\
Charging

Operate modes: Reader/Writer/Emulator\
**Supported protocols:**\
● Dallas DS1990A\
● CYFRAL

![](https://static.tildacdn.com/tild6234-3264-4862-a630-666536366663/Flipper\_Zero\_GPIO\_Pi.jpg)
