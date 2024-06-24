# Motorola Edge 5G (racer) Custom Rom Havoc OS Installation

***

<p align="center"><img src="https://github.com/jdenish1/Moto_Edge_racer_Custom-Roms/assets/96416029/976d626e-f85e-4e73-b700-21616983931d" /></p>

***


How to install Havoc OS on the Motorola Edge 5G #XT2063-2.

Havoc-OS 4.x is based on AOSP, inspired by Google Pixel. It has a refined Material Design 2 UI crafted by @SKULSHADY. There are many useful features that will blow your mind. All you can dream of and all you'll ever need.

Just flash and enjoy...


***

## Prerequisites

Requirements for the software and other tools to build, test and push 
- [x] Must have ADB and Fastboot installed on PC
- [x] Developer mode enabled on device
- [x] Unlocked Bootloader

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

Download all files from links above and have them somewhere accessible on your PC.

***

#### Installing

Connect phone to PC 

    Give the example

And repeat

    until finished

End with an example of getting some data out of the system or using it
for a little demo


Instructions
01. Download the ROM, Firmware and GApps from the links above.
02. Use terminal to boot latest twrp.img "fastboot boot twrp.img"
03. Create backup. i.e. EFS / Persist and put somewhere safe.

## YOU ONLY NEED THIS STEP ONCE.. When updating Firmwares ##
04.At this point Flash "Copy Partitions Zip" In TWRP "SLOT A"

05. Flash the ROM and TWRP installer.
06. Choose Reboot -> Recovery
07. Install GApps & Magisk.
08. Reboot -> Bootloader
09. fastboot -w
10. Reboot and Enjoy.

*Note-1: Slots, ROMS install to opposite (inactive) slot
If you FLASHED ROM from "Slot A", then ROM is installed to "Slot B", If you Flashed ROM from "Slot B", then ROM is installed to "Slot A"


##### Updating the "Dirty" Way From an Older Version of HavocOS

*Note-3: Updating "Dirty Flash"
01. Flash ROM + TWRP installer.
02. Reboot -> Recovery
02. Install Gapps + Magisk
03. Reboot -> System
