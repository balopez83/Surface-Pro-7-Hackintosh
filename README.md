# Surface-Pro-7-Hackintosh
This project aims to provide continued support running macOS on the Surface Pro 7
# This repo is still being built currently. You may see some items that may not directly reflect the SP7 as I am copying over relevant data from my other Surface Pro pages and updating for the SP7. Once complete I will upload the working SP7 EFI as the first release. 

EFI supports macOS version 10.15 through 14.

Star or watch this github repository to be notified of updates coming soon. 

If you see anything that could be added or changed don't hesitate to sumbit a request.


## *** NOTICE ***
- ### Touch is Technically supported in the posted EFI files however it requires [@Xiashangning's IPTSDaemon](https://github.com/Xiashangning/IPTSDaemon) in order to work. Please see the "Chapter 3" link below for instruction.
- ### If you have issues with random reboots at the user creation screen after install of macOS Big Sur and newer it is because you have chosen an incorrect config.plist file. Please ensure that you are using the correct one for your system.

 

## Supported Surface Specifications:

| Model: | Pro 7 |
|---|----------|
|CPU| 10th Gen: i3, i5, i7 |
|GPU| Intel UHD / Intel Iris Pro |
|RAM| 4/8/16 GB |
|SSD| 128GB/256GB/512GB/1TBs NVME |
|WiFi| Intel Wifi |
|Bluetooth| Intel Bluetooth |
|Batt| XX,000 mAH |
|USB| 1x USB-C |




## Instruction Guides

### [Chapter 1) Quick Start Install](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/1-QuickStart.md)
### [Chapter 2) BootCamp Install](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/2-BootCamp.md)
### [Chapter 3) Quirks & Fixes - Includes how to set up the Touch Screen](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/3-quirks%26fixes.md)
### [Chapter 4) Booting Other OS's with OpenCore](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/5-OtherOS%26OC.md)
### [Chapter 5) Enable Secure Boot with OpenCore/macOS](https://github.com/balopez83/Surface-Pro-7-Hackintosh/blob/main/7-SecureBootOn.md)


## What works 

- macOS Installer
- macOS Updates
- Fan
- USB
- Trackpad
- TouchScreen (Requires IPTSDaemon, "Chapter 3")
- Keyboard
- Audio
- Brightness Keys
- Power Management
- UEFI Secure Boot ON
- Surface Keyboard Hot Plug
- Surface Dock



## What doesn't work
- Accelerometer (unsupported device)
- Cameras (unsupported device)
- Hardware based DRM (Apple Issue)

## What will/should work after testing
- mDP/HDMI/USB-C video out (Not Tested)
- Dual Boot with Windows (Not Tested)
- Dual Boot with Linux (Not Tested)
- Dual Boot with chromeOS (Not Tested)
- FileVault (Not Tested)
- SD card (Not Tested)
- Volume Buttons (Not Tested)
- Power Button (Not Tested)
- Sleep/Hibernation (Not Tested)
- Recovery (Not Tested)
- Battery Status (Not Tested)
- Deep Sleep (macOS Hibernation 'Hibernatemode=25') (Not Tested)



## Credits
Special thanks to [@Xiashangning](https://github.com/Xiashangning) for the excellent work done on his BigSurface kext.
