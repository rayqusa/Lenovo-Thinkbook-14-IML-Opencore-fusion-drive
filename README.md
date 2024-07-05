This is my First Github guide and code

## :star_struck: :star_struck: Now the EFI supports Ventura!!:star_struck: :star_struck:
<hr>

## Lenovo-Thinkbook-14-IML-Opencore-guide.
- Comet Lake (10th gen) Thinkbook 13 14 15.

<hr>

![img](https://img.shields.io/badge/macOS%20Support-Ventura--latest-blue)![img](https://img.shields.io/badge/OpenCore%20Version-0.8.9-red)

- These are the builts from me.  You might get the future updates for this machine.
 Report me If you find the bugs or any issues. And do not hope any update from me, I am a Newbie.
- With every EFI update you retrieve from here please remember to go through the **post install guide**(Below)

# :diamond_shape_with_a_dot_inside: buy my books :  :diamond_shape_with_a_dot_inside:

if you feel helped, please consider buy my books, even you cant read it because written in bahasa indonesia. It mean a lot for me

https://play.google.com/store/books/details?id=KEmkEAAAQBAJ&pli=1

https://play.google.com/store/books/details/Novianta_Kuswandi_Coaching_Handbook?id=yQJbDwAAQBAJ

https://play.google.com/store/books/details/Novianta_Kuswandi_People_Development_Handbook?id=6KxaDwAAQBAJ

 <details><summary>DISCLAIMER</summary>
 
**Disclaimer**
- The Laptop model and Processor generation is the most important thing on Hackintosh. if you have same model but different processor model. please skip. I am not responsible for bricked devices, dead devices, or you getting fired because your system failed. Please do some research if you have any concerns about hackintoshing before you proceed.

 </details>
 
## Introduction

**This EFI Only for Single boot users. not for multi-boot users.**

# _Device Information_                    

 `Tested Devices`: i3 i5 comet lake-> Thinkbook 14 15.
 
 `Tested CPUs`: **i3-10110 i5-10210U**
 
 `Integrated Graphics`:   **Intel UHD Graphic 620**
 
 `Wireless Cards Tested`: **Realtek 8822ce**
 (wireless via Tether)
 `Ethernet` : Realtek RTL8111

 If anyone tested, Let me know!
<hr>

## Status : 
<details>
 <summary><strong> What's working ✅ </strong></summary>
 </br>
 
- :heavy_check_mark: Wifi
- :heavy_check_mark: iMessage, FaceTime, App Store, iTunes Store `Please generate your own SMBIOS`read my post install which is below the installation.
- :heavy_check_mark: OnBoard Audio(Input/ Output)
- :heavy_check_mark: USB ports
- :heavy_check_mark: Wired headphones
- :heavy_check_mark: Trackpad 
- :heavy_check_mark: brightness keys default key
- :heavy_check_mark: Wake / Shutdown
- :heavy_check_mark: Short sleep, Long sleep
- :heavy_check_mark: Tether via Android Phone

</details>
<details>
 <summary><strong>What's not working ⚠️</strong></summary>
 </br>
 
* :heavy_exclamation_mark: Bluetooth
* :heavy_exclamation_mark: Wifi
* :heavy_exclamation_mark: HDMI
</details>

 <hr>
 

## INSTALLATION

## Start with bios.

<details>
 <summary><strong> Setting Up with Bios</strong></summary>
 
  Note:Some of these options may not be present in your Bios. If you didn't find some bios, leave it and don't worry about it.
  
<details>
<summary><strong>Disable:</strong></summary>
 
- `SGX` 
- Secure Boot
- all type wake up on xxx
- `VT-d` 
 </details>
 
 
<details>
 <summary><strong>Enable:</strong></summary>
- `Intel Virtualization Technology`.
</details>

After setting these settings in bios, save it and exit.
</details>

**This is a simple and quick summary of the online install USB creation.**

### macOS Monterey Installer with Windows And Mac Users:
<details>
 <summary><strong>MacOS Monterey Online Installer from Windows, linux and macOS:</strong></summary>
 
  -  **`For Windows users`**
 
     	 1. Download [rufus](https://rufus.ie/en/) to format the sdcard to fat32.
     	 2. Select the desired flash drive or Sdcard you would like to put the installer on under the device option
     	 3. Open rufus and Select `non-bootable` as the `boot selection` (REQUIRED)
     	 4. Select `FAT-32` or `Large FAT-32` as the partition scheme. Hit start(by doing this the sdcard formats so you will lose the all the data in sdcard).
     	 5. If in windows,Open up the usb partition in file explorer and delete all the files created by rufus manually.

  -  **`For mac users`**

         1. Launch `Disk Utility`
         2. `Select View` > `Show all devices` at the top left
         3. Select your flash drive (root usb device)and format it as `MS-DOS (FAT)` or `FAT-32`.
         4. change `guid patition table`-> `Master Boot Record Partiton`.
         5. hit start(by doing this the sdcard formats so you will lose the all the data in sdcard).
       
  -  **`For Linux users`**
  
  		    1. Install `gparted` and format the usb to `Fat32` and `MBR` OR `MASTER BOOT RECORD PARTITION.
  	    	2. DONE.
  		
7. Now, Install Python from Microsoft store or Download manually for MAC,linux and Windows users here -> [python](https://www.python.org/downloads/) (Make sure you select add python x.x to path to environmet variables for windows users.)
8. Download and extract the [OpenCore Package](https://github.com/acidanthera/OpenCorePkg/releases).
9. Select the "macrecovery" folder in the "opencorepkg" folder at `/Utilities/macrecovery/`.
10. Copy the path of the "macrecovery" folder in file manager or finder.
11. Fire up command prompt or Terminal and type `cd` and hit spacebar and paste the path of the macrecovery folder.
12.If you cannot run this command, add `python` or `python3` to the beginning of this code -Run the command: `macrecovery.py -b Mac-E43C1C25D4880AD6 -m 00000000000000000 download`
13. This will download some files in the macrecovery folder but we only need "BaseSystem.dmg" and "BaseSystem.chunklist" for Downloading the Macos installer.
14. Create a folder in USB or pendrive or flash drive named `com.apple.recovery.boot`.
15. Paste both of those files in the `com.apple.recovery.boot` folder in your flash drive partiton or sdcard or pendrive.
16. Download the latest EFI created here.
17. Copy the folder named `EFI` and paste it in your USB partiton.

**Note: If you need to edit Config.plist, Use OpenCore configurator , use PlistEdit pro, PropperTree, or Xcode.**

`Note: Make sure to apply the correct bios settings before continuing (provided above)`

 18. Shutdown your laptop
 19. hit `reset`button go to bios settings.
 20. Shutdown your laptop
 21. hit `reset`button go to boot option. choose your flashdisk.
 22. Now in the OpenCore menu select the name of your USB partiton.
 23. go to disk utility, delete Partition in harddisk, and create APFS one. how to do that, see instruction below! 
 24. you can connect internet via RJ45/Ethernet/LAN or via Tether android. you can take internet access from wifi then passthrough USB port 
 25. Great! Now install and set up macOS Monterey
 26. the system reboots for once or twice so, when rebooting choose the usb everytime until you see your Macos Partition name in boot menu.
 27. After booting into OS, You need to download opencore configurator and mount the system drive, Then paste the efi to the mounted efi from the USB or drive. then reboot and remove usb.
 </details>

<details >
 
<summary><strong>After booting in to the *Macos Recovery*</strong></summary>
 

        - 1. open `Disk Utiliy` -> Select `View` which is at the top left -> choose `Show all devices` -> Select your root of your `SSD drive storage` which you want to install MacOS(root SSD drive device) -> Click `Erase` -> `Name` your drive as you like, Prefered to name as `Macintosh` OR `Macintosh HD` -> change `Format` to `APFS` -> `Scheme` to `Guid Patition Map` -> Click `Erase` .
        - 2. Click `done` and close `disk utility` window. 
        - 3. Select `Install MacOS <macos_version_here>` & click `continue` -> select your `SSD drive name` which you renamed before on Disk Utility and click `continue` .
        - 4. The installer takes 1-3 hours to install for online & offline process.


</details>

<hr>

# Post Install
Once you have verifed that your machine boots properly without any issues as described in the "What Works section", proceed to do the following

<details><summary><strong><ins>0. [Must] Boot os without usb or any drive</ins></strong></summary>
 
After booting into OS, you cannot boot without usb, because EFI is in USB. So, You need to downlaod opencore configurator [link](https://mackie100projects.altervista.org/opencore-configurator/) -> open `opencore-configurator` give permissions  in `system prefereneces` -> `security` -> `open anyway`. open `opencore-configurator` again -> mount the `EFI` and paste the `EFI<folder>` to the `EFI partition`.
 - Remove the USB and reboot. `RESET-NVRAM` once in opencore boot-menu and reboot

 
</details>

<details><summary><strong><ins>1.Disable the black screen texts on boot up</ins></strong></summary>

( Disabling the Verbose mode)A new hackintosh User uses this. To disable it, In Config.plist, navigate to 'NVRAM' ->  go to Add `7C436110-AB2A-4BBB-A880-FE41995C9F82` -> `boot-args` -> remove the `-v` argument. Save it and reboot. 
 </details>

<details><summary><strong><ins> 2. Disable ShowPicker</ins></strong></summary>
 
In the Config.plist, You can disable the boot picker screen so that you boot straight to th Apple logo by setting under `Misc` -> `Boot` -> `ShowPicker` False (NO)
Note: you can still see the boot picker with ShowPicker set to no/false by spamming Esc before the apple logo is displayed during boot.
</details>

<details><summary><strong><ins> 5. Add Device Properties for Serial number, MLB, ROM, Sytem-UUID.</ins></strong></summary>
 
Use `MacBookPro16,1` SMBios. Recommended : opencore configurator, Go to the  `PlatformInfo >SMBios`Tick the "Add to the section to config file" in `SMBIOS` and `DATAHUB -GENERIC- PLATFORMNVRAM` and continue your Adding your SMBIOS.
Follow this [Opencore guide](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#generate-a-new-serial) to set up serial number and the accompanying info to get iServices.
 </details>
 
 
<hr>

## My sincere thanks to**

- [Devboloji](https://github.com/devboloji) for readme Template
- [Dortania OC guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [CorpNewt's tools](https://github.com/corpnewt) for propertree
- [aamirswati](https://github.com/aamirswati/LenovoThinkbook15-IML-Hackintosh) , for initial EFI.
