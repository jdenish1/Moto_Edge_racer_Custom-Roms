# Motorola Edge 5G (racer) Custom Rom LineageOS Installation Instructions

![LineageOS Logo 5](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/1b03e692-e83c-43d4-9881-9723f8972ed3)


***

How to install LineageOS 20, based on Android 13, on the Motorola Edge 5G #XT2063-2.

***

## Prerequisites

Requirements for the software and other tools to build, test and push 
- [x] Must have ADB and Fastboot installed on PC
- [x] Developer mode enabled on device
- [x] USB Debugging Enabled on Device
- [x] Unlocked Bootloader
- [x] Boot Your Device with Stock FW Once and Check Every Functionality

***

### Files Required

- [x] [LineageOS 20]: (https://mirrorbits.lineageos.org/full/racer/20240620/lineage-20.0-20240620-nightly-racer-signed.zip)
- [x] [boot.img]: (https://mirrorbits.lineageos.org/full/racer/20240620/boot.img)
- [x] [dtbo.img]: (https://mirrorbits.lineageos.org/full/racer/20240620/dtbo.img)
- [x] [recovery.img]: (https://mirrorbits.lineageos.org/full/racer/20240620/recovery.img)
- [x] [super_empty.img]: (https://mirrorbits.lineageos.org/full/racer/20240620/super_empty.img)
- [x] [vbmeta.img]: (https://mirrorbits.lineageos.org/full/racer/20240620/vbmeta.img)
- [x] [copy-partitions-20220613-signed.zip]: (https://mirrorbits.lineageos.org/tools/copy-partitions-20220613-signed.zip)
- [x] 
- [x]

***

### Getting Started

1. Install Lineage Recovery via Fastboot

    1.  Connect device to PC
    
    2.  Run command

    ``` adb -d reboot bootloader ```

    3.  Once the device is in fastboot mode, verify your PC finds it by typing:

    ``` fastboot devices ```

    4.  Flash recovery onto device with command

    ``` fastboot flash recovery recovery.img ```

    5.  Reboot into recovery to verify installation.

        Use volume down button and select recovery, then hit power button to confirm and       reboot into recovery.

***

#### Installing

2.  Ensure all firmware partitions are consistent.

    - In some cases, the inactive slot can be unpopulated or contain much older firmware than the active slot, leading to         various issues including a potential hard-brick. We can ensure none of that will happen by copying the contents of          the active slot to the inactive slot.

    - To do this, sideload the copy-partitions-20220613-signed.zip package by doing the following:

        -  On the device, select “Apply Update”, then “Apply from ADB” to begin sideload.

        -  On the host machine, sideload the package using: 
        
        ``` adb -d sideload copy-partitions-20220613-signed.zip  ```

        - Now reboot to recovery by tapping “Advanced”, then “Reboot to recovery”.

3.  Install Lineage OS from Recovery

   - Download the LineageOS zip file that you would like to install or build the package yourself.

        - If you are not in recovery, reboot into recovery:

        - With the device powered off, hold Volume Down + Power, then select “Recovery mode” using Volume keys.

        - Now tap Factory Reset, then Format data / factory reset and continue with the formatting process. This will                 remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if           you have one).

        - Return to the main menu.

        - Sideload the LineageOS .zip package but do not reboot before you read/followed the rest of the instructions!

            On the device, select “Apply Update”, then “Apply from ADB” to begin sideload.
        
            On the host machine, sideload the package using:
    

            ``` adb -d sideload filename.zip ```

5.  Installing Add-Ons

    1.  Click Apply Update, then Apply from ADB, then 

        ``` adb -d sideload filename.zip ```

        - Repeat for all desired packages in sequence.


    2.  When presented with a screen that says Signature verification failed, click Continue. It is expected as add-ons             aren’t signed with LineageOS’s official key!

6.  All Set

    - Once you have installed everything successfully, you can now reboot your device into the OS for the first time!

        - Click the back arrow in the top left of the screen, then “Reboot system now”.
