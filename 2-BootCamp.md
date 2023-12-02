## Chapter 2) BootCamp Install 
## (Requires OpenCore: macOS as Primary OS, Windows as secondary)

PRE-WORK: 
- Create a Windows 10 iso file using the "Windows Media Creation Tool" within Windows OR google search Windows 10 iso file from Safari. Set aside, we will need this later.
- Format your entire SSD as GPT partition scheme with only an EFI partition and what will be your macOS partition. I recommend using a linux live USB and gparted for formating and partitioning your SSD. Set the EFI partition size as 200mb (recommend 300-500mb), the rest of the drive should be partitioned for macOS and you should use either NTFS or exFAT partioning.
- You MUST USE OPENCORE for your EFI. NO EXCEPTIONS, this will not work properly if you use Clover.

1. Install macOS from install disk to SSD using the entire drive. (Follow steps 1-2 & 5-9 from Chapter 1 titled "Quick Start Install")
* If you only want macOS and no other OS then you can stop here. Otherwise go to step 2.
2. Launch "Boot Camp Assistant" and "partition" your drive the way you would like. You must have your Windows iso copied over to your macOS install now. 
3. Boot Camp Assistant will ask you where your Windows iso is and will create a special partition with the Boot Camp files and Windows installer. After it has finished it will attempt to reboot to start the Windows install. IT WILL FAIL and thats ok.
4. Once the reboot into the Windows install fails you now need to do one of two things, either:
    
    a) Boot into your linux boot disk and mount the new drive called something like "OSXRECOVERY". Copy all files to an MBR partitioned FAT32 USB disk and proceed to step 5.
    
    b) "Create" a USB disk by booting back into macOS, opening Boot Camp Assistant, click on "Action" in the menu bar, and then click on "Download Windows Support Software". Mount your Windows iso and copy all files in the ISO to your MBR partitioned FAT32 USB disk and copy all files within the "WindowsSupport" folder to the root of your USB you just copied the Windows installer to. If you are asked if you would like to overwrite files click yes.
5. Open your Boot Camp Windows Installer USB you just created regardless of which method you used to create it. Delete all files in the folder "$WinPEDriver$" but DO NOT delete the folder.
6. Open the "BootCamp" folder on your install USB, then open your "Drivers" folder. Delete both "Broadcom" & "Intel" folders.
7. Restart and boot from your Boot Camp Windows installer USB. Follow the installation prompts. (If you get an error regarding the partitioning, simply reboot and try again. It usually works on the second try)
8. Your computer may reboot a few times before Windows has completed its install. I recommend removing the USB on its first reboot to avoid accidently starting the installer again.
9. After installation boot back into the UEFI/BIOS and select OpenCore as the primary boot option. Reboot and select Windows in the OpenCore boot menu if needed to boot back into Windows.
10. After installation you should reinsert your USB installer and run the BootCamp driver installation program. This will run with no problems and install drivers for all Apple products and also the BootCamp control panel to allow you to "Bless" drives just like on a real mac. This will not install any of the drivers that belong to a real mac which will cause conflicts on your hack.
10. Install any programs and make sure to install the WiFi, GoodixTouch, and Fingerprint drivers before updating Windows (see "Drivers" in Github). You may update Windows after those three are installed.
11. Once you are ready to boot back into macOS make sure you are still booting to OpenCore first and then select you macOS install.
12. Congratulations you are done. 

* Final Thoughts: Windows is now installed thinking its on a mac, if you accidently boot into Windows using your UEFI boot options you may get a notification that your Microsoft account requires an update or authentication. This is related to the computer now identifying differently and is related to the activation of Windows. Don't worry, you won't loose activation but it is annoying. I simply recommend always booting to Windows from OpenCore and you won't ever have to deal with this. Simply reboot into Windows using OpenCore and then re-authenticate when it pops up. You won't see it again until the next time you accidently boot direct to Windows from the UEFI.
* Installing other OS's: see Chapter titled "Other OS's and OpenCore"
