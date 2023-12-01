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
|GPU| Intel HD 520 / Intel Iris Pro |
|RAM| 4/8/16 GB |
|SSD| 128GB/256GB/512GB/1TBs NVME |
|WiFi| Intel Wifi |
|Bluetooth| Intel Bluetooth |
|Batt| XX,000 mAH |
|USB| 1x USB-C |




## Instruction Guides

### [Chapter 1) Quick Start Install]()
### [Chapter 2) BootCamp Install]()
### [Chapter 3) Quirks & Fixes - Includes how to set up the Touch Screen]()
### [Chapter 4) Additional Drivers]()
### [Chapter 5) Booting Other OS's with OpenCore]()
### [Chapter 6) Enable Secure Boot with OpenCore/macOS]()


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
- mDP/HDMI/USB-C video out (Not Tested)
- Dual Boot with Windows 
- Dual Boot with Linux
- Dual Boot with chromeOS
- FileVault
- SD card
- Volume Buttons
- Power Button
- Sleep/Hibernation
- Recovery
- Battery Status
- Deep Sleep (macOS Hibernation 'Hibernatemode=25')



## Credits
Special thanks to [@Xiashangning](https://github.com/Xiashangning) for the excellent work done on his BigSurface kext.
