# Motorola Edge 5G (racer) Custom Rom Havoc OS Installation

***

<p align="center"><img src="https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/d04150ed-f9dd-41f0-93ad-a5b0b32cc89a" /></p>

***

How to install Havoc OS on the Motorola Edge 5G #XT2063-2.

Havoc-OS 4.x is based on AOSP, inspired by Google Pixel. It has a refined Material Design 2 UI crafted by @SKULSHADY. There are many useful features that will blow your mind. All you can dream of and all you'll ever need.

Just flash and enjoy...

***

## Features of Havoc OS

- Face Unlock

- Enhanced QS Battery Estimation

- Font Customisation

- Dark Theme Support for AOSP apps

- Notification LED Settings

- Signature Spoofing

- Micro-G support

- Lockscreen charging animation

- Status Bar Customizations

- Ambient Display

- Screen Customizations

- Button Customizations

- Gestures

- Lockscreen customizations

- Notifications settings

- Animation

- Gaming Mode

- Battery saving tweaks

- Vibration & Haptics Customization

- LiveDisplay

- Notch Hide Settings

- Screen Refresh Rate (For Supported Devices)

- Always On Display

- Smart Charging

- Theming Customizations

- And many more.

***

## Prerequisites
 
- [x] Must have ADB and Fastboot installed on PC
- [x] Developer mode enabled on device
- [x] Unlocked Bootloader
- [x] SD Card large enough to hold all the downloaded files
- [x] Phone battery charged at least 70%

***

### Files Required

- [x] [HavocOS v6.0 + Google Apps](https://sourceforge.net/projects/havoc-os/files/racer/Havoc-OS-v6.0-20230715-racer-Official-GApps.zip/download)
- [x] [Official racer TWRP](https://twrp.me/motorola/motorolamotoedge.html)
- [x] [Open GApps 11 Pico - arm64](https://sourceforge.net/projects/opengapps/files/arm64/20220503/open_gapps-arm64-11.0-pico-20220503.zip/download)
- [x] [Magisk v27.apk](https://github.com/topjohnwu/Magisk/releases/download/v27.0/Magisk-v27.0.apk)
- [x] [Moto Edge racer Stock ROM](https://mirrors.lolinet.com/firmware/lenomola/racer/official/RETAIL/RACER_RETAIL_11_RPDS31.Q4U-39-26-14-13_subsidy-DEFAULT_regulatory-DEFAULT_CFC.xml.zip)
- [x] [Copy-Partitions-Peyton.zip](https://drive.usercontent.google.com/u/0/uc?id=1oiry9UfP2tf-5A6nQBF7pn2t2eSGKt0F&export=download)

***

### Getting Started

Make sure that your bootloader is unlocked and ready to install custom ROMs, as well as having USB Debugging enabled so your PC can communicate with your phone. 

Download all files from links above, transfer all the .zip files to your SD card, and also transfer ALL files to the platform-tools folder on your PC.

Next, open powershell window from the same platform-tools folder and we are ready to begin.

***

#### Installing

1.  Connect phone to pc. A dialog box should pop up asking you to enable USB Debugging with this device, asking you to trust the fingerprint. Check the box yes and hit OK.

![Allow USB Debugging and Trust PC](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/19cf9464-cb3e-49ca-a906-f5d6119c63e7)

Then run command:

``` adb reboot bootloader ```

This will get you into fastboot mode. Then run the command:

``` fastboot devices ```

Make sure you see your device and serial number in the terminal, along with "available". If so, proceed to next step.

2.  Use terminal to boot latest twrp.img by using command:

``` fastboot boot twrp.img ```

3.  *Optional* Create a backup of your device in case something goes wrong. i.e. EFS / Persist and save it somewhere safe.

4.  Next, flash copy-partitions-peyton.zip into TWRP "SLOT A".

Rename file to copy-partitions.zip inside the platform-tools folder.

In TWRP, go to Advanced > ADB Sideload > Swipe to perform a sideload.

Then run command:

``` adb sideload copy-partitions.zip ```

## YOU ONLY NEED THIS STEP ONCE.. When updating Firmwares ##

Once done it is recommended to reboot to recovery. In TWRP, go to Reboot > Recovery.

5.  Flash the TWRP installer.

Rename TWRP recovery file twrp-3.5.0_10-0-racer.img to recovery.img inside platform-tools folder.

Flash TWRP with command:

``` fastboot flash boot recovery.img ```

Reboot your phone to recovery again with command:

``` fastboot boot recovery.img ```

Then click on Wipe > Advanced Wipe. Then select System, data, cache, Dalvik cache partition and wipe it.

6.  Flash the HavocOS ROM

Inside TWRP click Install > HavocOS v6.0 + Google Apps.zip File > Swipe to confim flash.

![install-havoc-os](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/f49510ae-3e64-41bb-b65e-cd492c647207)

Wait until completed, then at the bottom you will se a button > Wipe Cache/Dalvik. Select it, then hit button > Reboot > To Recovery.

![wipe-cache-havoc](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/f7f052c1-9637-4586-bfc3-df663702b7e2)

*Note-1: Slots, ROMS install to opposite (inactive) slot. If you FLASHED ROM from "Slot A", then ROM is installed to "Slot B", If you Flashed ROM from "Slot B", then ROM is installed to "Slot A"*

7.  Install GApps.

Inside TWRP recovery, tap: Install > then select GApps.zip version you want to install > swipe to install. 

![havoc3 - open-gapps-install-1](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/4905e3f3-6be3-4c31-94f8-2800f7577e4c)

When done, Select > Wipe Cache/Dalvik.

Reboot > Bootloader

It might take a little while on first boot up, sometimes up to 15 minutes, but when done you will be greeted with the Havoc OS home screen.

8.  *Optional* Install Magisk

Copy Magisk App (.apk file) to the phone.

Change the extension of the file from “.apk” to “.zip”. This will make it flashable. 

![havoc4 - Rename-magisk](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/19da1560-4389-41d2-a129-031811617885)

Reboot back into recovery with command

``` adb reboot recovery ```

Inside TWRP Recovery tap: Install > Select Magisk.zip > Swipe to confirm install.

Wait for the process to complete, then Wipe Cache/Dalvik > Reboot to system.

![havoc5 - Flash-Magisk-Zip](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/3494d595-d0c8-440a-8fd0-1f47606858be)

Now go to app drawer and click on the Magisk app icon. If it says to download and install the full Magisk package, then go ahead and do that.

Once it’s done, you can click on the “Check SafetyNet” option in the Magisk app.

You should get a success message.

![havoc6 - check-safetynet-magisk](https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/790f3273-f01e-48b6-bac2-6b601e549559)

9.  *Troubleshoot:* If SafetyNet check fails, then download and flash [kdrag0n’s SafetyNet-fix](https://github.com/kdrag0n/safetynet-fix)


10. Use and enjoy your new ROM and customization features.

***

##### Updating the "Dirty" Way From an Older Version of HavocOS

01. Flash ROM + TWRP installer.

02. Reboot -> Recovery

03. Install Gapps + Magisk

04. Reboot -> System
