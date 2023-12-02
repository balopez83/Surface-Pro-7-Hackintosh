# Chapter 7: Secure Boot On with OpenCore
## This pages information has been heavily copied from user [@badstorm's Surface Pro 7 page here](https://github.com/badstorm/surface-pro-7-opencore/blob/master/SecureBoot.With.Grub.md) and may contain links to other sites and images outside my control. I take no credit for the content on this page. Full credit due to @badstorm and anyone else that assisted in the creationof these steps. 

## For clarity and ease of use, I have modified some of the wording and steps below to fit this Github repository and my EFI releases. Starting with release 3.0.0 I will include the most recent version of the precompiled and signed Grub within the EFI as well as the key. The steps below have been modified to include that information.

## If you don't want to follow these steps manually, you may skip to Step 3!



# Secure Boot with Grub

### Step 1: Get Precompiled Grub

**The latest version is automatically included in each release but if you would like to do this process manually or for another device you can follow this step manually.**

We need a version of Grub precompiled with the certificate used to sign the binary file. To accomplish this we will download **Super UEFIinSecureBoot Disk**. The latest releases can be found [here](https://github.com/ValdikSS/Super-UEFIinSecureBoot-Disk/releases).


### Step 2: Modifying the EFI

1. Extract the zip you just download which will expose an `"img"` file. 
2. You now need to mount the img or if you prefer you may extract it with software such as 7zip. 
3. Mount your EFI containing OpenCore, and go to `\EFI\BOOT\` and rename `"BOOTx64.efi"` to `"grubx64_real.efi"`. 
4. Copy all contents from the `"BOOT"` folder located in the `"img"` you downloaded EXCEPT the `"grubx64_real.efi"` file and paste and choose yes to overwrite the files in your OpenCore EFI under the `\EFI\BOOT\` directory if asked.
5. Copy the folder `grub` to your OpenCore EFI folder.
6. Copy the file `*ENROLL_THIS_KEY_IN_MOKMANAGER.cer*` at the root of your EFI partition


### Step 3: Add the Key and Boot

1. At this point whether you took the long manual way or just dropped the release EFI in your EFI partition, you can now reboot to your UEFI and enable `Secure Boot` making sure you select the option for `Microsoft and 3rd party keys`. 
2.Reboot and you should now get a blue screen with the *Access Denied* error. Press `OK`
3.Press any key to perform MOK management
4. Select `Enroll key from disk`
5. Select `Continue`
6. Select the disk where you put the `.cer` file. If using my EFI it is located at `\EFI\` on the EFI partition
7. Select `Yes` and then `Reboot`

![Illustrated Steps](https://camo.githubusercontent.com/47a5bd8e778cb6668e612cbd7299ed715af5a8cc27cd879b9cba0fa09b750ca1/68747470733a2f2f7777772e62756770726f6772616d6d65722e6d652f696d616765732f7365637572652d626f6f742d322e706e67)

### If you completed the steps correctly you should now be able to boot with Secure Boot turned On with OpenCore and be able to use Windows Bitlocker.
