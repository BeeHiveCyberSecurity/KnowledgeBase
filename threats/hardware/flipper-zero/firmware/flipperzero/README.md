---
description: The official firmware shipped with the Flipper Zero device.
---

# 🐬 flipperzero



## Flipper Zero Firmware

* [Flipper Zero Official Website](https://flipperzero.one). A simple way to explain to your friends what Flipper Zero can do.
* [Flipper Zero Firmware Update](https://update.flipperzero.one). Improvements for your dolphin: latest firmware releases, upgrade tools for PC and mobile devices.
* [User Documentation](https://docs.flipperzero.one). Learn more about your dolphin: specs, usage guides, and anything you want to ask.

## Contributing

Our main goal is to build a healthy and sustainable community around Flipper, so we're open to any new ideas and contributions. We also have some rules and taboos here, so please read this page and our Code of Conduct carefully.

### I need help

The best place to search for answers is Flipper's [User Documentation](https://docs.flipperzero.one). If you can't find the answer there, check their [Discord Server](https://flipp.dev/discord) or their [Forum](https://forum.flipperzero.one/).

### I want to report an issue

If you've found an issue and want to report it, please check their [Issues](https://github.com/flipperdevices/flipperzero-firmware/issues) page. Make sure the description contains information about the firmware version you're using, your platform, and a clear explanation of the steps to reproduce the issue.

### I want to contribute code

Before opening a PR, please confirm that your changes must be contained in the firmware. Many ideas can easily be implemented as external applications and published in the Flipper Application Catalog (coming soon). If you are unsure, reach out to Flipper on the [Discord Server](https://flipp.dev/discord) or the [Issues](https://github.com/flipperdevices/flipperzero-firmware/issues) page, and they'll help you find the right place for your code.

Finally, open a [Pull Request](https://github.com/flipperdevices/flipperzero-firmware/pulls) and make sure that CI/CD statuses are all green.

## Development

Flipper Zero Firmware is written in C, with some bits and pieces written in C++ and armv7m assembly languages. An intermediate level of C knowledge is recommended for comfortable programming. C, C++, and armv7m assembly languages are supported for Flipper applications.

### Requirements

Supported development platforms:

* Windows 10+ with PowerShell and Git (x86\_64)
* macOS 12+ with Command Line tools (x86\_64, arm64)
* Ubuntu 20.04+ with build-essential and Git (x86\_64)

Supported in-circuit debuggers (optional but highly recommended):

* [Flipper Zero Wi-Fi Development Board](https://shop.flipperzero.one/products/wifi-devboard)
* ST-Link
* J-Link

Flipper Build System will take care of all the other dependencies.

### Cloning source code

Make sure you have enough space and clone the source code:

```shell
git clone --recursive https://github.com/flipperdevices/flipperzero-firmware.git
```

### Building

Build firmware using Flipper Build Tool:

```shell
./fbt
```

### Flashing firmware using an in-circuit debugger

Connect your in-circuit debugger to your Flipper and flash firmware using Flipper Build Tool:

```shell
./fbt flash
```

### Flashing firmware using USB

Make sure your Flipper is on, and your firmware is functioning. Connect your Flipper with a USB cable and flash firmware using Flipper Build Tool:

```shell
./fbt flash_usb
```

### Documentation

* Flipper Build Tool - building, flashing, and debugging Flipper software
* Applications, Application Manifest - developing, building, deploying, and debugging Flipper applications
* Hardware combos and Un-bricking - recovering your Flipper from the most nasty situations
* Flipper File Formats - everything about how Flipper stores your data and how you can work with it
* Universal Remotes - contributing your infrared remote to the universal remote database
* Firmware Roadmap
* And much more in the documentation folder

## Project structure

* `applications` - applications and services used in firmware
* `assets` - assets used by applications and services
* `furi` - Furi Core: OS-level primitives and helpers
* `debug` - debug tool: GDB plugins, an SVD file, etc.
* `documentation` - documentation generation system configs and input files
* `firmware` - firmware source code
* `lib` - our and 3rd party libraries, drivers, etc.
* `scripts` - supplementary scripts and python libraries home

Also, see `ReadMe.md` files inside those directories for further details.

## Links

* Discord: [flipp.dev/discord](https://flipp.dev/discord)
* Website: [flipperzero.one](https://flipperzero.one)
* Forum: [forum.flipperzero.one](https://forum.flipperzero.one/)
* Kickstarter: [kickstarter.com](https://www.kickstarter.com/projects/flipper-devices/flipper-zero-tamagochi-for-hackers)
