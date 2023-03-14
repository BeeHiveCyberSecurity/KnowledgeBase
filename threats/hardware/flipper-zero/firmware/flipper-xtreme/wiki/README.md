# Wiki

## Welcome to the Flipper-Xtreme wiki!

This is the Homepage of our Wiki, here you will find some basic info on what the Flipper Zero is, what Xtreme Firmware is, an FAQ section, what apps we include and a few words from the Devs. Check out the sidebar for more detailed information! The documentation you find in this wiki is either made by us, or by the OFW team / UL team / the community at large and then adapted by us, we wanted to have an organized place for most documentation, so credit and a huge thanks goes to the original authors/contributors!

If you have any questions, please join our [Discord](https://discord.gg/flipper-xtreme) and we will be more than happy to answer each and every one of your questions!

\


## Flipper Zero

Flipper Zero is a portable Tamagotchi-like multi-functional device developed for interaction with access control systems. The device is able to read, copy, and emulate radio-frequency tags, radio remotes, and digital access keys. [Wikipedia](https://en.wikipedia.org/wiki/Flipper\_Zero)

\


## XFW / Xtreme Firmware

XFW, also known as Xtreme, is the Firmware written by us. Its a relatively new Firmware that has already gained over two thousand users in the first three weeks of its existence. This is due to the fact that it includes virtually all possible applications, receives constant updates that are based on what the community wants, has no restrictions unlike most other Firmware for the Flipper Zero and because the developers try their best to create a thriving community.

For a full in-depth info on what the Firmware can do, please check the [Readme](https://github.com/ClaraCrazy/Flipper-Xtreme#xfw---xtreme-firmware-for-the-flipper-zero)

\


## FAQ:

**1)** How do I access Xtreme Firmware features and settings?

> From the Home screen (the one with the animations) hit the `Arrow UP` button, go into `Xtreme Settings`, and customize to your heart's content!

**2)** How do I enable **NSFW** mode / unlock higher level animations?

> Open the Xtreme Settings app (more info above), and its gonna be right there for you to change.

**3)** Is it possible to set my Dolphin level?

> Of course! To set a custom level, simply open the Xtreme Settings app and modify the level to your liking!

**4)** I get an error saying "furi\_version mismatch" when loading an app, how do I fix that?

> Open qFlipper, go to `SD` and delete the `Apps` folder. Then launch the latest update again. This folder houses all the .fap files, which do not update to the correct API versions by default if old ones are present (Thanks flipper devs). If the issue persists, its our fault and please open a ticket!

**5)** After a while, my Slut stops to level up, why is that?

> We added max daily limits to make sure you aren't just cheating your way to level 30. Please note that turning off your Flipper will stop the timer, so you will still be limited the next day! We recommend not turning Flipper off.

**6)** I really like the firmware, can I help?

> You can donate on the links you find on the GitHub releases, preferably the Patreon. You can spend time in our server to help others with issues, you can contribute to the project by making PRs on GitHub and most importantly, you can simply spread the word!

**7)** I dont like the animations, and dont want to switch to another FW, how do I change them?

> You can use Asset Packs! This is an exclusive feature of our firmware that allows you to load custom animations and icons without recompiling the firmware. You can read more info on this on the homepage (ReadMe) and here in the wiki, in the File Formats section.

**8)** After an Update / Randomly one day, qFlipper says something like _permission denied_.. Whats going on?

> Windows is going on... Essentially, either two devices use your COM port qFlipper expects, or Windows assigned your Flipper a completely different COM port. This is partially documented here: [https://forum.flipperzero.one/t/qflipper-not-recognizing-device-2-devices-on-one-com-port-while-bluetooth-on-windows-is-turned-on/1910](https://forum.flipperzero.one/t/qflipper-not-recognizing-device-2-devices-on-one-com-port-while-bluetooth-on-windows-is-turned-on/1910), let us know if you require help with this

\


## Included Apps:

<details>

<summary>Games</summary>

* [Arkanoid](https://github.com/DarkFlippers/unleashed-firmware/tree/dev/applications/plugins/arkanoid)
* [Asteroids](https://github.com/SimplyMinimal/FlipperZero-Asteroids)
* [BlackJack](https://github.com/teeebor/flipper\_games)
* [DOOM](https://github.com/p4nic4ttack/doom-flipper-zero/)
* [Flappy Bird](https://github.com/DroomOne/flipperzero-firmware/tree/dev/applications/flappy\_bird)
* [Pong](https://github.com/nmrr/flipperzero-pong)
* [Game 15](https://github.com/x27/flipperzero-game15)
* [2048](https://github.com/eugene-kirzhanov/flipper-zero-2048-game)
* [Game of Life](https://github.com/tgxn/flipperzero-firmware/blob/dev/applications/game\_of\_life/game\_of\_life.c)
* Heap Defence - Author Unknown
* [Mandelbrot Set](https://github.com/Possibly-Matt/flipperzero-firmware-wPlugins)
* [Minesweeper](https://github.com/panki27/minesweeper)
* Multi Dice - In-house
* [Snake Game](https://github.com/flipperdevices/flipperzero-firmware/tree/dev/applications/plugins/snake\_game)
* [Solitaire](https://github.com/teeebor/flipper\_games)
* [Tamagotchi](https://github.com/DroomOne/flipperzero-tamagotch-p1)
* Tanks
* [Tetris](https://github.com/jeffplang/flipperzero-firmware/tree/tetris\_game/applications/tetris\_game)
* [Tic Tac Toe](https://github.com/gotnull/flipperzero-firmware-wPlugins/tree/420/applications/plugins/tictactoe\_game)
* [Video Poker](https://github.com/PixlEmly/flipperzero-firmware-testing/blob/420/applications/VideoPoker/poker.c)
* [Yatzee](https://github.com/emfleak/flipperzero-yatzee)
* Zombiez

</details>

<details>

<summary>GPIO</summary>

* [\[BMI160\] Air Mouse](https://github.com/ginkage/FlippAirMouse/)
* [\[RC2014\] ColecoVision](https://github.com/ezod/flipperzero-rc2014-coleco)
* [\[GPIO\] DAP Link](https://github.com/flipperdevices/flipperzero-firmware/pull/1897)
* [\[GPIO\] Flashlight](https://github.com/xMasterX/flipper-flashlight)
* \[GPIO] Geiger Counter
* [\[GPIO\] Reader (Aurelic)](https://github.com/aureli1c/flipperzero\_GPIO\_read)
* [\[GPIO\] Reader (biotinker)](https://github.com/biotinker/flipperzero-gpioreader)
* [\[GPIO\] Sentry Safe](https://github.com/H4ckd4ddy/flipperzero-sentry-safe-plugin)
* \[GPIO] Timelapse
* [\[NMEA\] GPS](https://github.com/ezod/flipperzero-gps)
* [\[HC-SR\] Dist. Sensor](https://github.com/Sanqui/flipperzero-firmware/tree/59656ca5fb644e0d4484259986b86a0b963f323d/applications/hc\_sr04)
* [\[GPIO\] i2c Tools](https://github.com/NaejEL/flipperzero-i2ctools)
* [\[BH1750\] Lightmeter](https://github.com/oleksiikutuzov/flipperzero-lightmeter)
* [\[NRF24\] Mouse Jacker](https://github.com/mothball187/flipperzero-nrf24/tree/main/mousejacker)
* [\[NRF24\] Scanner](https://github.com/vad7/nrf24scan)
* [\[NRF24\] Sniffer](https://github.com/mothball187/flipperzero-nrf24/tree/main/nrfsniff)
* \[GPIO] Signal Generator
* \[SPI] Mem Manager
* \[SWD] Probe
* [\[UART\] Echo](https://github.com/flipperdevices/flipperzero-firmware/pull/831)
* \[UART] Terminal
* \[GPIO] Unitemp
* [\[GPIO\] Wii EC Analyser](https://github.com/csBlueChip/FlipperZero\_WiiEC)

</details>

<details>

<summary>Misc</summary>

* [Barcode Generator](https://github.com/McAzzaMan/flipperzero-firmware/tree/UPC-A\_Barcode\_Generator/applications/barcode\_generator)
* Brainfuck
* [Caesar Cipher](https://github.com/panki27/caesar-cipher)
* Calculator - In house / notIntense
* [Countdown Timer](https://github.com/0w0mewo/fpz\_cntdown\_timer)
* [Counter](https://github.com/Krulknul/dolphin-counter)
* [Hex Viewer](https://github.com/QtRoS/flipper-zero-hex-viewer)
* [Morse Code](https://github.com/DarkFlippers/unleashed-firmware/pull/144)
* [Multi Converter](https://github.com/theisolinearchip/flipperzero\_stuff/tree/main/applications/multi\_converter)
* Nightstand Clock
* Orgasmotron
* [Paint](https://github.com/n-o-T-I-n-s-a-n-e)
* Rubik's Cube Scrambler
* [Text Viewer](https://github.com/kowalski7cc/flipper-zero-text-viewer)
* [Authenticator](https://github.com/akopachov/flipper-zero\_authenticator)
* [USB HID Autofire](https://github.com/pbek/usb\_hid\_autofire)

</details>

<details>

<summary>Music</summary>

* [BPM Tapper](https://github.com/panki27/bpm-tapper)
* [Metronome](https://github.com/panki27/Metronome)
* Music Beeper - Author Unknown
* [Music Player](https://github.com/flipperdevices/flipperzero-firmware/pull/1189)
* [Ocarina](https://github.com/invalidna-me/flipperzero-ocarina)
* [SAM (Software Automatic Mouth)](https://github.com/ctoth/SAM)
* [Tuning Fork](https://github.com/besya/flipperzero-tuning-fork)
* Wav Player - In house
* [Zero Tracker](https://github.com/DrZlo13/flipper-zero-music-tracker)

</details>

<details>

<summary>Sub-GHz</summary>

* [POCSAG Pager](https://github.com/xMasterX/flipper-pager)
* [ProtoView](https://github.com/antirez/protoview)
* [Spectrum Analyzer](https://github.com/jolcese/flipperzero-firmware/tree/spectrum/applications/spectrum\_analyzer)
* [Sub-GHz Bruteforcer](https://github.com/derskythe/flipperzero-subbrute/tree/master)
* Sub-GHz Playlist
* Weather Station

</details>

<details>

<summary>Tools</summary>

* [CLI (subghz chat)](https://github.com/ranchordo/flipperzero-cli-bridge)
* [Dolphin Backup & Restorer](https://github.com/flipperdevices/flipperzero-firmware/pull/1384)
* [DTMF Dolphin](https://github.com/litui/dtmf\_dolphin)
* Pomodoro Timer
* [Bluetooth Remote](https://github.com/flipperdevices/flipperzero-firmware/pull/1330)
* [USB Remote](https://github.com/flipperdevices/flipperzero-firmware/pull/1330)
* [iButton Fuzzer](https://github.com/DarkFlippers/unleashed-firmware)
* [NFC Magic](https://github.com/flipperdevices/flipperzero-firmware/pull/1966)
* [Password Generator](https://github.com/anakod/flipper\_passgen)
* [PicoPass](https://github.com/flipperdevices/flipperzero-firmware/pull/1366)
* QR Code
* [RFID Fuzzer](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/pull/245)

</details>

<details>

<summary>WiFi</summary>

* [\[ESP32\] WiFi Marauder](https://github.com/0xchocolate/flipperzero-firmware-with-wifi-marauder-companion)
* [\[ESP8266\] Deauther](https://github.com/Timmotools/flipperzero\_esp8266\_deautherv2)
* [\[ESP8266\] IFTTT Virtual Button](https://github.com/Ferrazzi/FlipperZero\_IFTTT\_Virtual\_Button)
* \[ESP8266] WiFi (Deauther) v2
* \[WiFi] Scanner

</details>

> **Thank you to the authors!**

The Flipper and its community wouldn't be as rich as it is without your contributions and support. Thank you for all you have done.

\


## Our words:

* A huge thank you, obviously. This FW turned from a joke to a massive project with over 1k Users in **a week**. You guys are just mad, lol. We got many things planned and are working on them every day. We are always open to suggestions and interested in implementing what the community wants, so make sure to let us know.
* Working on this is a lot of fun! This will keep being in development for a very long time, and unlike other "developers", we actually focus on adding new functionality and providing a stable experience for our userbase. We don't ever put our Firmware behind a PayWall, and we not only tolerate criticism, we ask for it. Be honest if you dislike something. We don't know if you don't tell us. That's the only way we can work on making it better.
