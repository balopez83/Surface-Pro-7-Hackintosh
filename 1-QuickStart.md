##  Chapter 1) Quick Start Install 
## (macOS will be primary OS and will overwrite your entire drive)

1. Create a bootable macOS installer on bootable USB from a macOS installer downloaded from the AppStore or using this [tutorial](https://internet-install.gitbook.io/macos-internet-install/).
2. Once install disk is created mount EFI partition and copy the OpenCore EFI folder to your Install Disk's EFI partition you just mounted.
3. Boot from your usb then install macOS on your SSD. WARNING, this will wipe your entire drive.
5. During first boot, after installing the OS, mount your EFI partition and copy over the OpenCore folder along with your BOOT folder found in the EFI folder on your install usb; you must copy/overwrite the same folders on the same partition located on your SSD.
6. Reboot and change BIOS bootloader order to have OpenCore bootloader as first entry. This should happen automatically after wiping the drive.
7. If your Bios/UEFI does not show OpenCore as an available option you will need to add it via the UEFI Shell. Open "Quirks and Fixes" and follow instructions for manually adding OpenCore to your bootloader list. Once added move to step 8.
8. Open your config.plist and generate a new serial number [Tutorial here](https://hackintosher.com/forums/thread/generate-your-own-hackintosh-serial-number-board-serial-number-uuid-mlb-rom-in-clover.306/)
9. Install any additional software and drivers if needed for your specific needs
10. Reboot and enjoy!
