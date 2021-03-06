# ViGEm Bus Driver

Windows kernel-mode driver emulating well-known USB game controllers. 

[![Build status](https://ci.appveyor.com/api/projects/status/rv74ufluwib52dq2?svg=true
)](https://ci.appveyor.com/project/nefarius/indicium-supra) [![Discord](https://img.shields.io/discord/346756263763378176.svg)](https://discord.gg/QTJpBX5)  [![Website](https://img.shields.io/website-up-down-green-red/https/vigem.org.svg?label=ViGEm.org)](https://vigem.org/) [![PayPal Donate](https://img.shields.io/badge/paypal-donate-blue.svg)](<https://paypal.me/NefariusMaximus>) [![Support on Patreon](https://img.shields.io/badge/patreon-donate-orange.svg)](<https://www.patreon.com/nefarius>) [![GitHub followers](https://img.shields.io/github/followers/nefarius.svg?style=social&label=Follow)](https://github.com/nefarius) [![Twitter Follow](https://img.shields.io/twitter/follow/nefariusmaximus.svg?style=social&label=Follow)](https://twitter.com/nefariusmaximus)

## About
**Disclaimer:** this project is for software developers. To make it do something useful you'll also need a [feeder application](<https://vigem.org/wiki/vigem-feeder/>).  

The `ViGEmBus` driver and `ViGEmClient` libraries represent the core of the Virtual Gamepad Emulation Framework (or `ViGEm` , for short). `ViGEm` aims for a 100% accurate [emulation](<https://en.wikipedia.org/wiki/Emulator>) of well-known gaming peripherals as pure software-based devices at kernel level. As it mimics "the real thing" games and other processes require no additional modification whatsoever to detect `ViGEm`-based devices (no Proxy-DLLs or API-Hooking) and simply work out of the box. While the (now obsolete) [Scarlett.Crush Productions Virtual Bus Driver](<https://github.com/nefarius/ScpVBus>) is the spiritual father of this project, `ViGEm` has been designed and written from the ground up utilizing Microsoft's [Kernel-Mode Driver Framework](https://en.wikipedia.org/wiki/Kernel-Mode_Driver_Framework).

### Emulated devices
Currently supports emulation of the following USB Gamepads:
- [Microsoft Xbox 360 Controller](https://en.wikipedia.org/wiki/Xbox_360_controller)
- [Sony DualShock 4 Controller](https://en.wikipedia.org/wiki/DualShock#DualShock_4)

## Use cases
A few examples of the most common use cases for `ViGEm` are:
 * You have an unsupported input device you'd like to use within games without modifying said game.
 * You want the freedom to use a different controller of your choice in [PS4 Remote Play](<https://remoteplay.dl.playstation.net/remoteplay/>).
 * You encountered a game not compatible with [x360ce](<https://www.x360ce.com/>).
 * You want to extend the reach of your input device (like send traffic to a different machine over a network).
 * You want to test/benchmark your game and need a replay mechanism for your user inputs.
 * You want to work around player slot assignment order issues in `XInput`.

## Supported Systems
The driver is built for Windows 7/8/8.1/10 (x86 and amd64).

## How to build

### Prerequisites 
 - Visual Studio **2017** ([Community Edition](https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15) is just fine)
 - [WDK for Windows 10, version 1803](https://developer.microsoft.com/en-us/windows/hardware/windows-driver-kit)

 You can either build directly within Visual Studio or in PowerShell by running the build script:
 
 ```
 .\build.ps1 -configuration release
 ```
 
 Do bear in mind that you'll need to sign the driver to use it without [test mode](<https://technet.microsoft.com/en-us/ff553484(v=vs.96)>).

## Installation
To grab the latest signed binaries for use or redistribution [follow the installation instructions](<https://vigem.org/wiki/vigem-bus-driver-installation/>).

### Necessary preparations for Windows 7
Before installing the bus driver on Windows 7 (x86 or x64) the following 3rd party software has to be installed:
 * [Xbox 360 Accessories Software 1.2](https://www.microsoft.com/accessories/en-us/products/gaming/xbox-360-controller-for-windows/52a-00004#techspecs-connect) (contains the missing device drivers)
 * [Microsoft Security Advisory 3033929 Update](https://technet.microsoft.com/en-us/library/security/3033929) has to be installed to support the drivers signature. Download links:
   * [Security Update for Windows 7 (KB3033929)](https://www.microsoft.com/en-us/download/details.aspx?id=46078)
   * [Security Update for Windows 7 for x64-based Systems (KB3033929)](https://www.microsoft.com/en-us/download/details.aspx?id=46148)

## Sponsors
 - [3dRudder](https://www.3drudder.com/)
 - [Wohlfeil.IT e.U.](https://wohlfeil.it/)
 - [Parsec](https://parsecgaming.com/)
 - [Rainway, Inc](https://rainway.io/)

## Known users of ViGEm
 - [3dRudder](https://www.3drudder.com/)
 - [Parsec](https://parsecgaming.com/)
 - [GloSC](https://github.com/Alia5/GloSC)
 - [WhiteKnight](https://autohotkey.com/boards/viewtopic.php?t=34890)
 - [InputMapper](https://inputmapper.com/)
 - [Oculus VR, LLC.](https://www.oculus.com/)
 - [Rainway, Inc](https://rainway.io/)
 - [WiimoteHook](https://forum.cemu.info/showthread.php/140-WiimoteHook-Nintendo-Wii-Remote-with-Motion-Rumble-and-Nunchuk-support)
