## Chapter 5) Booting Other OS's with OpenCore

## Windows: 

Should be installed and booted from the OpenCore menu. OpenCore will automatically show Windows in the menu with no additional effort. 

## Linux: 

Linux based OS's require special steps for OpenCore to show Linux in the boot menu. If you have already installed Linux start at step 7:

  1. Install macOS and Windows prior to installing Linux.
  2. Prior to installing Linux you should backup your current EFI. This is important as Linux overwrites important files in the EFI.
  3. Create a partition to install Linux.
  4. Install Linux
  5. After Linux has installed and you reboot your computer Ubuntu will be the default OS. You may be able to change it to boot OpenCore. Because Linux overwrites some of the files in the ``\EFI\BOOT`` folder you should now restore your backed up EFI. When restoring files you can restore everything but make sure you don't overwrite the new Linux folder (the Linux folder likely is named after the flavor of Linux you installed. E.g. Ubuntu would have a folder Ubuntu)
  6. If you haven't already set OpenCore as your default boot option do that now.
  7. Restart your computer and when the OpenCore boot menu appears press the space bar. Then select the OpenShell.efi option.
  8. Once OpenShell loads you will see a map of all the drives and partitions on your computer. You must locate the partition that contains your Linux folder. If you installed linux to your SSD you likely will find this on ``FS0``, if you installed Linux to your SDcard it may be on ``FS6``. Confirm the location by navigating to the partition and searching for your Linux folder within the EFI folder. 
    
    Example steps:
    1. At root type: FS0 (if you suspect your linux EFI files are on the root SSD)
    2. Type Dir or LS and press enter. Hopefully you see a folder "EFI", if not try another partition if yes go to step 3
    3. Type CD EFI and press enter. 
    4. Type Dir or LS and press enter. You should see a folder named after the Linux install you just installed. If you see your linux folder move to step 9, if not keep looking.
 
  9. Once you have identified your correct EFI folder in the correct partition we need to dump the map and then load it into your OpenCore configurator. Type ``FS0`` and then type ``map > partition-map.text`` This will dump your partion map into the root EFI folder where it can be read and copied into your config file much easier. If you have an unusual partion map or if your Linux boot folder is located on a different drive or partition you may need to substitute ``FS0`` with another partion number
  10. Boot back into macOS; Mount your EFI partition; Open your ``partition-map.text`` file and open your ``config.xml`` file in the OpenCore folder. You may want to use OpenCore configurator for the next steps but be aware that you must use the correct version for the OpenCore version you are currently using. See the Release notes of the EFI version you are using to determine which OpenCore version is included in that release
  11. Open OpenCore Configurator or whatever editor you prefer; click the ``Misc`` tab and then click on ``entries``; Click the ``+`` icon to create a new entry.
  12. Copy the path from the ``partition-map.text`` file for your EFI partion containing the Linux boot folder. It will look similar to this: ``PciRoot(0x0)/Pci(0x17,0x0)/NVME(0x1,0xFFFF,0x0)/HD(1,GPT,12345678-1234-1234-1234-123456789123,0x100,0x1DD000)``; Paste the path into the path location of the custom entry; Add ``/\EFI\Ubuntu\grubx86.efi`` to the end of the partition path. Keep in mind you may have to change the Ubuntu folder name to whatever the name represents your linux boot folder.
  13. Add a name of your choice in the name location of your custom entry; Check the box to enable the entry.
  14. Save your config file and reboot. You should now have a new boot entry for your Linux install. You may want to adjust your Grub configuration to streamline your boot experience. If Grub and ultimately Linux does not boot you may need to review the previous steps and make sure you have put the right information in your config file. You can also find an example of custom entries by downloading an OpenCore release from its GitHub page. Examples may also be included in future EFI releases.
  
  
## chromeOS: 

I recommend installing to a Ultra High Speed SD card especially if using the "Brunch" method of installation. Once installed to the SD card it will show up in the OpenCore boot menu.

If you are going to install chromeOS on the internal SSD you should follow the Linux instructions for custom entries.
