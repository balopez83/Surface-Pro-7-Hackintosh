# Surface-Pro-7-Hackintosh
This project aims to provide continued support running macOS on the Surface Pro 7


Star or watch this github repository to be notified of updates coming soon. 

If you see anything that could be added or changed don't hesitate to sumbit a request.


# *** NOTICE ***
## It appears that the Hackintosh journey is coming to a close. Support for the key kexts that allow the Surface Pro 7 work, has ended resulting in the need for more and more workarounds to get things functional. Given this current state, I am moving this repo to an LTS support model until either Apple stops releasing Intel compatible OS's or no more support of the key kexts required to boot new versions are supported. If BigSurface.kext and the Intel Wifi drivers/kexts get updated, I will of course continue to update this repo. I will periodically update kexts and OpenCore as appropriate however there is no need to update with every release as no new features or fixes impact the Surface Pro 7. You should expect that any current issues will not be solved. 

- ### Touch works out of the box however if you would like multitouch support you will need to install [@Xiashangning's IPTSDaemon](https://github.com/Xiashangning/IPTSDaemon). Please see the "Chapter 3" link below for instruction.
- ### If you have issues with random reboots at the user creation screen after install of macOS Big Sur and newer it is because you have chosen an incorrect config.plist file. Please ensure that you are using the correct one for your system.

 

## Supported Surface Specifications:

| Model: | Pro 7 |
|---|----------|
|CPU| 10th Gen: (i3 unsupported), i5, i7 |
|GPU| Intel UHD (unsupported)/ Intel Iris Pro |
|RAM| 4/8/16 GB |
|SSD| 128GB/256GB/512GB/1TBs NVME |
|WiFi| Intel Wifi |
|Bluetooth| Intel Bluetooth |
|Batt| XX,000 mAH |
|USB| 1x USB-C |

## Supported Software:

- [X] macOS 10.15 Catalina (End of Life)
- [X] macOS 11 Big Sur (End of Life)
- [X] macOS 12 Monterey
- [X] macOS 13 Ventura
- [X] macOS 14 Sonoma
- [X] macOS 15 Sequoia (Missing Features)


## Instruction Guides

### [Chapter 1) Quick Start Install](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/1-QuickStart.md)
### [Chapter 2) BootCamp Install](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/2-BootCamp.md)
### [Chapter 3) Quirks & Fixes - Includes how to set up the Touch Screen](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/3-quirks%26fixes.md)
### [Chapter 4) Booting Other OS's with OpenCore](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/5-OtherOS%26OC.md)
### [Chapter 5) Enable Secure Boot with OpenCore/macOS](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/7-SecureBootOn.md)


## What works 
- Surface Pro i5 & i7 Supported (i3 Unsupported Graphics)
- macOS Installer
- macOS Updates
- Fan
- USB
- Trackpad
- TouchScreen (Requires IPTSDaemon for multitouch, "Chapter 3")
- Keyboard
- Audio
- Brightness Keys
- Power Management
- UEFI Secure Boot ON
- Surface Keyboard Hot Plug
- Intel Wifi
- Intel Bluetooth
- Battery Status
- Dual Boot with Windows
- Dual Boot with Linux
- Dual Boot with ChromeOS
- SD card
- Volume Buttons
- Power Button
- Recovery
- Surface Pen
- USB-C video out
- FileVault
- Sleep/Hibernation (Hibernatemode 25 only)
- Surface Dock

## What will/should work eventually
- Everything that can work, is already working :) 

## What doesn't work
- Accelerometer (unsupported device)
- Cameras (unsupported device)
- Hardware based DRM (Apple Issue)


## Credits
Special thanks to [@Xiashangning](https://github.com/Xiashangning) for the excellent work done on his BigSurface kext. @badstorm & @Xiashangning for the initial work they did in getting initial support for macOS on the Surface Pro 7 from which my work builds upon. 
