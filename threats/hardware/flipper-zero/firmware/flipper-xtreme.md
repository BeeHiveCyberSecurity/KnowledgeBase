---
description: >-
  An authentic community-created firmware with risque features, occasionally
  explicit content, and some not-so-legal features. Use at own liability.
---

# 🐬 flipper-xtreme

### Feature-rich, stable, customizable

![](https://user-images.githubusercontent.com/55334727/215170306-051eeb8f-8f72-437f-8c2d-0e4be009bdad.png)

## [Intro](https://github.com/ClaraCrazy/Flipper-Xtreme#What-makes-it-special) | [Animations](https://github.com/ClaraCrazy/Flipper-Xtreme#Animations--Asset-Packs) | [Wiki](https://github.com/ClaraCrazy/Flipper-Xtreme/wiki) | [Changelog](https://github.com/ClaraCrazy/Flipper-Xtreme#list-of-changes) | [Known bugs](https://github.com/ClaraCrazy/Flipper-Xtreme/issues?q=is%3Aissue+is%3Aopen+label%3Arelease-pending) | [Install](https://github.com/ClaraCrazy/Flipper-Xtreme#Install) | [Build](https://github.com/ClaraCrazy/Flipper-Xtreme#build-it-yourself) | [Discord](https://discord.gg/flipper-xtreme)

This firmware is a complete overhaul of the [Official Firmware](https://github.com/flipperdevices/flipperzero-firmware), and also features lots of awesome code-bits from [Unleashed](https://github.com/DarkFlippers/unleashed-firmware).

## What makes it special?

We have spent many hours perfecting this code even further, and getting the most out of it.

The goal of this Firmware is to regularly bring out amazing updates based on what the community wants, with an actual understanding of whats going on. Fixing bugs that are regularly talked about, removing unstable / broken applications (.FAP) and actually using the level system that just sits abandoned everywhere else.\
\


* **Feature-rich: We include all commonly found apps in the firmware, as long as they work.**
* **Stable: Many hours have been spent rewriting core parts of the Flippers firmware as well as some of its apps to ensure stability. A task that was long needed on all Firmware, so we tackled it right away.**
* **Customizable: Dont like the Animations, want to turn on/off the Home screen icons (battery, SD card etc), change the flippers name or anything like that? You absolutely can. No need to mess with code or deal with weird manifest files. Its all done with an App.**

***

\


## Xtreme Settings:

We wrote a powerful yet easy-to-use application specifically for our Firmware, that gives you easy-access to all the fancy things we implemented:

![](https://user-images.githubusercontent.com/55334727/222941141-32e3ef23-1dad-473f-86ee-45bef66ebd77.gif)

<details>

<summary><code>Graphics:</code></summary>

Change the animation package (more on that below), the play speed of them, cycle duration and bypass level-bassed animations

</details>

<details>

<summary><code>Statusbar:</code></summary>

Modify the design of the statusbar seen on the main Screen. Toggle Icons, their background, the top line and modify the battery icon to your liking.

</details>

<details>

<summary><code>Protocols:</code></summary>

Here you can cycle between USB & Bluetooth mode for our Bad-Keyboard app, and toggle Subghz settings.

</details>

<details>

<summary><code>Dolphin:</code></summary>

Two simple yet sought after features: Simply change the level of your Flipper and disable / change the "Butthurt timer", aka. the time it takes for the Flipper to get sad when its not used.

</details>

<details>

<summary><code>Misc:</code></summary>

All the other options that dont fit elsewhere. Toggles for our custom dark mode & left-handed mode (yes, we thought about you :3 ), an option to change the Flippers name and a switch for file sorting.

</details>

## Animations / Asset Packs:

We created our own, new & improved Animation / Asset system, that we can finally reveal. It lets you to create and cycle through your own `Asset Packs` with only a few button presses, allowing you to easily load custom Animations and Icons like never before.

&#x20;You can easily create your own pack, or find some user made ones in the discord channel. Check [here](https://github.com/ClaraCrazy/Flipper-Xtreme/wiki/Asset-Packs) for a tutorial on creating your own. Essentially, we got our own `Anims` & `Icons` folders, inside each `Asset Pack`.\
\
&#x20;Once you have some packs, upload them to your Flipper in `SD/dolphin_custom` (if you did this right you should see `SD/dolphin_custom/PackName/Anims` and/or `SD/dolphin_custom/PackName/Icons`).\
\
&#x20;After installing the packs to Flipper, hit the `Arrow UP` button on the main menu and go to `Xtreme Settings`. Here choose which pack you want and tweak the other settings how you prefer, then press back to reboot and enjoy your new assets for all apps (e.g. Subghz scanning asset) & animations!\


<figure><img src="https://user-images.githubusercontent.com/55334727/214010675-9eddb8f5-1dd6-4cf4-a0ee-e37af8b6c933.PNG" alt=""><figcaption></figcaption></figure>

<figure><img src="https://user-images.githubusercontent.com/55334727/214016338-95a619c7-88d2-4db5-bb7a-75282d9082b8.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://user-images.githubusercontent.com/55334727/214013624-25dad48e-72ea-4a90-9060-66e137e0d61a.png" alt=""><figcaption></figcaption></figure>

***

\


## Bad Keyboard:

&#x20;BadUSB is a wonderful app, but it lacks bluetooth capabilities. Now some might argue that its useless as you will always need authentication from both sides, but what if I told you that we found a solution to this problem?\
\
Bad-KB allows you to toggle between USB and Bluetooth mode for your attacks. In Bluetooth mode it allows you to spoof the name & MAC of the device to whatever you want. Being a JBL speaker or a wireless razer keyboard is easily doable, allowing you to trick people so you can run your payloads without needing a cable at hand.

<figure><img src="https://user-images.githubusercontent.com/49810075/223855940-b8ee6770-4520-4bcc-a4cc-089196cf904b.png" alt=""><figcaption></figcaption></figure>

***

\


## Levels:

This Firmware has 30 levels, not just the basic 3 the official one has.

With this new system in place, it allows for some cool stuff like locking animations behind a certain level. This can be done fairly easy: The idle\_animations are tied to the level system. Specifically, the `Min level` variable of your manifest file is used here. Each level you reach, unlocks a new animation. The higher your level, the more animations people can see.

<details>

<summary>Our example</summary>

In our example case, this is used with the NSFW animation pack you can select in the Xtreme app. Dont worry, this is not used by default because I know not everyone likes to see my / anime tits and thats fine. Anyways.. each level gives a brand new background animation, they also become more and more lewd over time.

</details>

***

\


## List of changes:

Note: This repo is always updated with OFW & Unleashed. No need to mention all those here. We will only mention **our** changes that we can actually be credited for.

```txt
[Added]

- Xtreme App
- Asset Packs
- More UI options
- Bad-Keyboard App
- A new battery display-type
- Scrolling view for long file names in browser
- NSFW Animations tied to the level system. Read more above
- Folder handling for empty ones (Now indicate they are empty)

- Custom subghz presets
- Multiple NFC protocols
- Multiple Sub-Ghz protocols | Merged from Unleashed, thanks @xMasterX
- Subghz and IR signal replication via gpio | Credits to @ankris812

- New API Routes for Locale settings
```

```txt
[Updated]

- All Assets

- Tons of apps
- File browser
- Massive compiler re-do
- About 4k files to speed things up a lot
- Applications to now use the new Locale setting
```

```txt
[Fixed]

- Keyboard issues on first char
- Passport crash on high level
- SFW / Dummy_mode getting you XP
- Leveling system
- Mood system
```

```txt
[REMOVED]

- Unused Dummy Mode
- Broken apps (bad apple, chess, etc.)
- Tons of unused code from FAPs and system calls
```

***

\


## Install:

**This is the recommended install procedure. Please follow these steps EXACTLY and CAREFULLY to ensure you install correctly.** **This process will NOT delete any saved files and simply ensures the install goes smoothly.**\
\


* Download the latest release (.zip) from [The releases tab](https://github.com/ClaraCrazy/Flipper-Xtreme/releases/latest)
* Extract the archive. This is now your new Firmware folder
* Open [qFlipper](https://flipperzero.one/update), head to `SD/Update` and simply move the firmware folder there
* On the Flipper, hit the `Arrow Down` button, this will get you to the file menu. In there simply search for your updates folder
* Inside that folder, select the Firmware you just moved onto it, and run the file thats simply called `Update`
* Enjoy!

**If you have issues or crashes with that process, you can try to use `Settings > Storage > Factory Reset` then retry the install.** **Doing that will NOT remove your saved files, it will only forget some settings and paired devices.**

***

\


## Build it yourself:

```bash
To download the needed tools:
$ git clone --recursive https://github.com/ClaraCrazy/Flipper-Xtreme.git
$ cd Flipper-Xtreme/

To flash directly to the Flipper (Needs to be connected via USB, qFlipper closed)
$ ./fbt flash_usb

To just compile firmware
$ ./fbt updater_package

If building FAPS:
$ ./fbt fap_dist

If building image assets:
$ ./fbt resources icons dolphin_ext
```

***

## Stargazers over time

[![Stargazers over time](https://starchart.cc/ClaraCrazy/Flipper-Xtreme.svg)](https://starchart.cc/ClaraCrazy/Flipper-Xtreme)

***

## Contributors

[![Contributors](https://user-images.githubusercontent.com/55334727/212134625-21383102-02f3-453f-b1d7-8a9c65b27612.svg)](https://github.com/ClaraCrazy/Flipper-Xtreme/graphs/contributors)

***

## SAST Tools

This helps us a lot, thanks for the free license for this project!

[PVS-Studio](https://pvs-studio.com/en/pvs-studio/?utm\_source=github\&utm\_medium=organic\&utm\_campaign=open\_source) - static analyzer for C, C++, C#, and Java code.

***

"What we do for ourselves dies with us. What we do for others and the world remains and is immortal.” ― Albert Pine
