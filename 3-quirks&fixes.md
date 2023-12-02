## Chapter 3) Quirks & Fixes

## After installing macOS you may find several things that need to be resolved in order to have a true mac experience. Please use the following quirks & fixes to fix remaining issues. ***Touch Screen instruction can be found at number 5 below***

### 1. If you are missing OpenCore from your boot options boot your computer and press both the 'FN' AND 'F1' keys to load the boot list. Select the option to start the UEFI Shell. Once the shell loads type the following:
```
bcfg boot add 0 FS0:\EFI\OC\OpenCore.efi "OC"
```
Where "0" after add is where you assign boot order. "0" would be the first position. "OC" is the name of the boot option. You may name your boot option anything you want. "FS0" is the drive and partition where your OpenCore EFI files are located. If you are installing macOS to anything other than the built in SSD in the 1st partition EFI (standard configurtion) you will need to determine the correct path of your OpenCore Files. If you need more information regarding how to edit your UEFI boot options you can go [here](https://wiki.archlinux.org/index.php/Unified_Extensible_Firmware_Interface).


### 2. You can enable HiDPI mode which adds more resolution options to the list of available display resolutions.

Enter the following command in terminal post-installation then reboot:

```
sudo defaults write /Library/Preferences/com.apple.windowserver.plist DisplayResolutionEnabled -bool true
```


### 3. macOS sets "Force Click and Haptic Feedback" as enabled by default which causes unexpected behavior when clicking on the trackpad. You will need to turn off this function in order to have a trackpad that operates as expected. You can turn it off by going to:
``` 
System Preferences > Trackpad > Uncheck Force Click and Haptic Feedback
```

### 4. In order to get macOS Hibernation working you are required to change your hibernatemode and make other power management adjustments. Please open Terminal and enter the following commands. (If Hibernate doesn't work properly after entering the commands below, try switching Hibernatemode back to 0 and then again to 25)
```
sudo pmset autopoweroff 0
sudo pmset powernap 0
sudo pmset standby 0
sudo pmset proximitywake 0
sudo pmset tcpkeepalive 0
sudo pmset -a hibernatemode 25;
```

### 5. The Surface devices have issues with waking from sleep after a period of time. If you experience these issues you can try the following options ONE AT A TIME to resolve wake issues. These fixes should ONLY be used if you experience these issues and may need to be reaplied after updates.

The following commands should be entered into Terminal: 

A. Remove Power Management settings that may be corrupt. These will be regenerated to their defaults after reboot and you will need to reapply commands from number 4 above.
```
sudo rm /Library/Preferences/com.apple.PowerManagement.*
```
B. Make Wake Scheduling unwritable but still able to be read by macOS. This will clear scheduled wakes which can still be applied despite turing off wake schedules. macOS is stubborn when it comes to wake scheduling.
First we clear the com.apple.AutoWake.plist of all wake schedules:
```
sudo pmset sched cancelall
```
Next we make the file immutable meaning that it can only be read but not written:
```
sudo chflags schg /Library/Preferences/SystemConfiguration/com.apple.AutoWake.plist
```
If you need to reverse this you can enter:
```
sudo chflags noschg /Library/Preferences/SystemConfiguration/com.apple.AutoWake.plist
```

### 6. The Touch Screen is finaly usable on the Surface Pro 4-7, Surface Books, and the Surface Laptops. You must install a client that depends on "Brew", "FMT", and "INIH" being installed. In the future this may not be required but for now it works very well. Please use the following link whichincludes the client and all instructions. Issues related to the Touch Screen should be directed to @Xiashangning on his repository issue page.


      [Xiashangning IPTSDaemon](https://github.com/Xiashangning/IPTSDaemon)


### 7. Enabling Authenticated Restarts with FileVault 2. If you would like to avoid entering a password for FileVault when restarting you can enter the terminal command below. This will not bypass the requirement to enter a password when resuming from Hibernation or when Cold Booting and only turns off the requirement to enter a password when restarting from an already signed in system.

```
sudo fdesetup authrestart
```
